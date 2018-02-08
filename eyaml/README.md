# eyaml

Run the [hiera-eyaml](https://rubygems.org/gems/hiera-eyaml) gem to perform
encryption/decryption for eyaml key.

> Unfortunately `eyaml edit` is not supported yet - we need to find a way to get
vim to work with this

## Usage

Make sure to mount the key directory (which container `private_key.pkcs7.pem`
and `public_key.pkcs7.pem`) to `/keys`, otherwise you will have to make sure to
mount and specify the key with `eyaml` command

> Key directory should be mounted as read-only to avoid any mishaps

> From the standard eyaml command help

```bash
/ # eyaml -h
Welcome to eyaml 2.1.0

Usage:
eyaml subcommand [global-opts] [subcommand-opts]

Available subcommands:
     createkeys: create a set of keys with which to encrypt/decrypt eyaml data
        recrypt: recrypt an eyaml file
        encrypt: encrypt some data
           edit: edit an eyaml file
        version: show version information
        decrypt: decrypt some data

For more help on an individual command, use --help on that command

Installed Plugins:
```

## Example

```bash
docker run --rm -v $PWD/keys:/keys:ro nmtan/eyaml encrypt -s 'sample string'
```
