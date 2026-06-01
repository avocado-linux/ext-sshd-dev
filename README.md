# ext-sshd-dev

SSH server that allows root login with no password. DO NOT USE IN PRODUCTION.

## Using this extension

`ext-sshd-dev` is an [Avocado](https://avocadolinux.org) extension — a reusable fragment of
build- and runtime-configuration that you compose into your own Avocado project. To use it,
declare it as a package-sourced extension in your `avocado.yaml` and add it to a runtime:

```yaml
extensions:
  avocado-ext-sshd-dev:
    source:
      type: package
      version: "*"        # or pin an exact version

runtimes:
  my-runtime:
    extensions:
      - avocado-ext-sshd-dev
```

Then `avocado build`. The extension's config is fetched from your target's package feed
and merged into your project at build time.
