# Updating packages in Go

- Execute the commands inside the Go project directory.
- `./...` will search in every `.go` file and extract the package URLs automatically.
- MAJOR versions needs to be updated manually with `go get` as Go considers these packages totally new "unrelated" packages.


## Update to latest PATCH version

```shell
go mod tidy
go get ./...
```

## Update to latest MINOR or PATCH version

```shell
go mod tidy
go get -u ./...
```

-----------

**Refs**

- https://pkg.go.dev/cmd/go#hdr-Add_dependencies_to_current_module_and_install_them
