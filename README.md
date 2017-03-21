goenv
---

[goenv](https://github.com/wfarr/goenv) plugin support for the fish shell.

Install
---

With [fisherman](https://github.com/fisherman/fisherman)

```
fisher yamadayuki/goenv
```

Notes
---

This plugin replaces what status --is-interactive; and . (goenv init -|psub) does in a more fishy way. This brings the startup time of your shell down as we do not generate full completions every time the shell starts but only when goenv gets called.

On Fish 2.3.0 and later support was introduced that automatically loads snippets in conf.d. However, these snippets are evaluated before your config.fish. If you're setting GOENV_ROOT in your config.fish to relocate your goenv installation this will be evaluated after our plugin gets loaded and hence have no effect. In order to fix this you should drop a 000-env.fish file in your ~/.config/fish/conf.d folder which sets up your environment accordingly.

#### For example...

In `$HOME/.config/fish/conf.d/000-env.fish`
```
set -x GOENV_ROOT $HOME/.anyenv/envs/goenv
set -x GOPATH $HOME/dev
```
