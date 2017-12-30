# py3http

This Zsh service-plugin will serve given directory (plugin's directory by
default) using Python's 3 HTTP server.

## [Zplugin](https://github.com/zdharma/zplugin)

A service-plugin needs a plugin manager that supports loading single plugin instance
per all active Zsh sessions, in background. Zplugin supports this, just add:

```
zplugin ice service'py3http'
zplugin light zservices/py3http
```

to `~/.zshrc`.

## Explanation of Zsh-spawned services

First Zsh instance that will gain a lock will spawn the service. Other Zsh instances will
wait. When you close the initial Zsh session, another Zsh will gain lock and resume the
service.
