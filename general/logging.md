# Logging

Tips and best practices on logging.

---

## DOs and DON'Ts

- DO log program output to `stderr` it's meant for errors AND _diagnostics_ of a program. Logs are diagnostics.
- DO log program output to `stderr` only, not to a file, not to a DB, not to a 3rd party service. It's not the job of the program to decide where to log besides `stderr`, other programs can pipe it to a file or scrape it and send it to an aggregator.
- ALWAYS log structured logs, JSON is preferred but [logfmt](https://brandur.org/logfmt) is OK for simple logs. Don't mix formats, pick one and stick to it.
- DO set the default log level to INFO in production and DEBUG in development.
- DO NOT log sensitive information, e.g. PII data, log IDs instead, e.g. user ID.
- DO NOT log and handle the error in the same operation. Either return the error to the caller function or handle the error. **Logging an error is _handling_ it.**

## Logging to stderr

No matter the log level, it should be streamed to `stderr`. From the docs on `stderr` it reads like this:

> Under normal circumstances every UNIX program has three streams opened for it when it starts up, one for input, one for output, and one for printing diagnostic or error messages. 

The key takeaway here is that `stderr` is for error messages **OR diagnostic messages**. Logs are a program's diagnostics and it's not necessarily meant to be consumed by the end user of the program.

Even though `stderr` has `err` in its name, it's meant to stream logs too. A lot of production systems do not adhere to this original POSIX standard though, and it's fine as long as the output stream used is consistent.

## Log Levels

A maximum of 3 logging levels is enough for 99% of projects, but most likely only 2 will be used:

- **DEBUG** - disabled in production, enabled in development, only enabled in production if nothing else helps. Usually, metrics and development events are logged on this level. If you need to enable this level in production make sure to use a package that supports log sampling, such as only 60% of log records are emitted for high-traffic apps.
- **INFO** - normal operation, not as robust as DEBUG and with enough metadata, e.g. user_id added record into a DB.
- **ERROR** - an error that cannot be recovered from, e.g. cannot insert data into the db.

### You don't need these log levels

- Warnings are basically INFO logs with a label attached to it.
- Notice, Fatal, Alert, Critical, etc. are just semantics of either INFO or ERROR where a label would suffice. E.g. INFO alert message alert=true

## How to write good logs

1. Can I reproduce the event from the logs?
2. Do I have enough metadata attached to the log that I know what happened?
3. Can I correlate multiple log lines? (multiple log lines vs. wide events). Always attach a trace or request ID to the log lines.
4. Can I reproduce the error just by reading the error logs?
5. Do I know when the log happened?

## Log lines vs wide events

- Generally, wide events are preferred for web projects or request/response-based apps; and log lines for CLI apps.
- Wide events are "enriched" logs that are logged at the end of the request cycle. Enriched means metadata are added to the log context along the path of the execution resulting in a single log record at the end of the request or execution path.
