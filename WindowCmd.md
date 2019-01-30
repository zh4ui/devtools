# Windows Command Line


## set proxy for chocolatey

```
choco config set proxy http://localhost:8888
choco config set proxyUser bob
choco config set proxyPassword 123Sup#rSecur3
choco config set proxyBypassList "'http://localhost,http://this.location/'" #0.10.4 required
choco config set proxyBypassOnLocal true #0.10.4 required
```

source: [Explicit Proxy Settings](https://github.com/chocolatey/choco/wiki/Proxy-Settings-for-Chocolatey#explicit-proxy-settings)