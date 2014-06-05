# Packer Command Provisioner

[Shell Provisioner](http://www.packer.io/docs/provisioners/shell.html) makes a script file locally and send the file via SCP before executing commands.But Command Provisioner runs command directly via SSH.So you don't need scp command in the target host.

----

## Install

```
$ go build -o $GOPATH/bin/provisioner-command  plugin/provisioner-command/main.go
```

----

## Basic Example

```json
{
  "provisioners": [
    {
      "type": "command",
      "command": "echo foo"
    }
  ]
}
```

You can also multiple commands by `commands` with an array of commands.

```json
{
  "provisioners": [
    {
      "type": "command",
      "commands": [
        "echo foo",
        "echo bar",
        "echo baz"
      ]
    }
  ]
}
```
