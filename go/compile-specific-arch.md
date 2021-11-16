# Compile for a Specific Architecture

- To compile for a specific platform and architecture prefix `go build` with `GOOS` and `GOARCH` environment variables.
- Go can compile for a target platform regardless of the host platform (e.g. compile for Windows on macOS).

```shell
# Build for Windows 64 bit

env GOOS=windows GOARCH=amd64 go build -o my_program_win_amd64 .
```

-----------

**Refs**

- List out all platform and architecture combinations with `go tool dist list`
