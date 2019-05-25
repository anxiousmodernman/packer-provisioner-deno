# packer-provisioner-deno

Run deno scripts to provision stuff with Packer.

This is a work in progress. Deno builds are only provided for a few systems, so
we are only testing on Ubuntu docker containers right now.

TODO

- [*] Install deno onto target system
- [*] Upload individual deno scripts
- [ ] Execute individual deno scripts
- [ ] Manually bundle scripts locally and upload those, instead. Or, [wait for this feature](https://github.com/denoland/deno/issues/2357).
- [ ] Add a DigitalOcean cloud builder test

## Installation

This provisioner is a Packer plugin. [See the docs for an overview](https://www.packer.io/docs/extending/plugins.html#installing-plugins).

Build or download this plugin and place in

```
$HOME/.packer.d/plugins
```

You may need to create the plugins directory.


## Development and Tests

You will need a non-ancient version of Go, and **$GOPATH/bin** should be on your
PATH. That's **$HOME/go/bin** by default, but can vary depending on your setup.

If you want to hack, make a symlink from **$GOPATH/bin/packer-provisioner-deno**
to the packer plugins directory. Something like this should work, after an
initial `go install`:

```
ln -s $GOPATH/bin/packer-provisioner-deno $HOME/.packer.d/plugins/packer-provisioner-deno
```

After that, run the test script

```
./test.sh
```

Local tests run in docker.


