# Reminder: Misuse may cause the account to be BAN! ! !

### Server

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://dashboard.heroku.com/new?template=https://github.com/editomw/linux8188) 


```bash
* Client download：https://github.com/2dust/v2rayN/releases
* Proxy protocol：vless or vmess
* Address：xxx.herokuapp.com
* Port：443
* Default UUID：24b4b1e1-7a89-45f6-858c-242cf53b5bdb
* vmess alter ID：0
* encryption：none
* transmission protocol：ws
* camouflage type：none
* camouflage domain name：xxx.workers.dev ((CF Workers url)
* path：/24b4b1e1-7a89-45f6-858c-242cf53b5bdb-vless // default - vless (/custom UUID-vless), if you wanna use vmess (/custom UUID-vmess)
* Underlying transmission security：tls
* allow inscure：false
```
</details>

<details>
<summary>Trojan-Go</summary>

```bash
* Client download: https://github.com/p4gefau1t/trojan-go/releases
{
    "run_type": "client",
    "local_addr": "127.0.0.1",
    "local_port": 1080,
    "remote_addr": "xxx.herokuapp.com",
    "remote_port": 443,
    "password": [
        "24b4b1e1-7a89-45f6-858c-242cf53b5bdb"
    ],
    "websocket": {
        "enabled": true,
        "path": "/24b4b1e1-7a89-45f6-858c-242cf53b5bdb-trojan",
        "host": "xxx.herokuapp.com"
    }
}
```
</details>

<details>
<summary>Shadowsocks</summary>

```bash
* Client download：https://github.com/shadowsocks/shadowsocks-windows/releases/
* Server address: xxx.herokuapp.com
* Port: 443
* Password：24b4b1e1-7a89-45f6-858c-242cf53b5bdb
* Encryption：chacha20-ietf-poly1305
* Plug-in：xray-plugin_windows_amd64.exe  //You need to download and unzip the plugin - https://github.com/shadowsocks/xray-plugin/releases and place it in the same directory
* Plugin options: tls; host= xxx.herokuapp.com; path= /24b4b1e1-7a89-45f6-858c-242cf53b5bdb-ss // (/custom UUID-ss)
```
</details>

<details>
<summary>You can use Cloudflare Workers to transfer traffic, (supporting WS mode of VLESS\VMESS\Trojan-Go) is configured as:</summary>

```js
const SingleDay = 'xxx.herokuapp.com'
const DoubleDay = 'xxx.herokuapp.com'
addEventListener(
    "fetch",event => {
    
        let nd = new Date();
        if (nd.getDate()%2) {
            host = SingleDay
        } else {
            host = DoubleDay
        }
        
        let url=new URL(event.request.url);
        url.hostname=host;
        let request=new Request(url,event.request);
        event. respondWith(
            fetch(request)
        )
    }
)
```
</details>

## OpenWrt preferred IP script is automatically updated：

* [CloudflareST](https://github.com/Lbingyi/CloudflareST) `OpenWrt recommand -faster`
* [cf-autoupdate](https://github.com/Lbingyi/cf-autoupdate) `OpenWrt recommand`

## About Cloudflare SpeedTest

* [CloudflareSpeedTest](https://github.com/XIU2/CloudflareSpeedTest)
*  [better-cloudflare-ip](https://github.com/badafans/better-cloudflare-ip)

### Special thanks to:

* [mixool](https://github.com/mixool/)
* [bclswl0827](https://github.com/bclswl0827/v2ray-heroku)
* [yxhit](https://github.com/yxhit)
* [badafans](https://github.com/badafans/better-cloudflare-ip/tree/20201208)
