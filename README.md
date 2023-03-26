### 用Rust编写的Bitwarden服务器API的替代实现，并与上游Bitwarden客户端*兼容，非常适合自托管部署，其中运行官方资源繁重的服务可能并不理想。

📢 注：该项目被称为Bitwarden_RS，并已重新命名为与官方Bitwarden服务器分离，以避免混淆和商标/品牌问题。有关更多解释，请参阅[#1642](https://github.com/dani-garcia/vaultwarden/discussions/1642) for more explanation。

---
[![Build](https://github.com/dani-garcia/vaultwarden/actions/workflows/build.yml/badge.svg)](https://github.com/dani-garcia/vaultwarden/actions/workflows/build.yml)
[![ghcr.io](https://img.shields.io/badge/ghcr.io-download-blue)](https://github.com/dani-garcia/vaultwarden/pkgs/container/vaultwarden)
[![Docker Pulls](https://img.shields.io/docker/pulls/vaultwarden/server.svg)](https://hub.docker.com/r/vaultwarden/server)
[![Quay.io](https://img.shields.io/badge/Quay.io-download-blue)](https://quay.io/repository/vaultwarden/server)
[![Dependency Status](https://deps.rs/repo/github/dani-garcia/vaultwarden/status.svg)](https://deps.rs/repo/github/dani-garcia/vaultwarden)
[![GitHub Release](https://img.shields.io/github/release/dani-garcia/vaultwarden.svg)](https://github.com/dani-garcia/vaultwarden/releases/latest)
[![AGPL-3.0 Licensed](https://img.shields.io/github/license/dani-garcia/vaultwarden.svg)](https://github.com/dani-garcia/vaultwarden/blob/main/LICENSE.txt)
[![Matrix Chat](https://img.shields.io/matrix/vaultwarden:matrix.org.svg?logo=matrix)](https://matrix.to/#/#vaultwarden:matrix.org)

镜像基于[Rust implementation of Bitwarden API](https://github.com/dani-garcia/vaultwarden)实现。

**该项目与[Bitwarden](https://bitwarden.com/)项目或Bitwarden, Inc.无关。**

#### ⚠️重要⚠️：使用此服务器时，请直接向我们报告任何错误或建议（查看此页面底部的联系方式），无论您使用什么客户（移动、桌面、浏览器......）。不要使用官方支持渠道。

---

## 特点

基本上提供了Bitwarden API的完整实现，包括：
* 组织支持
* 附件和发送
* Vault API支持
* 为Vault界面提供静态文件
* 网站图标API
* 身份验证器和U2F支持
* Yubikey和Duo支持
* 紧急访问

## Installation
Pull the docker image and mount a volume from the host for persistent storage:

```sh
docker pull vaultwarden/server:latest
docker run -d --name vaultwarden -v /vw-data/:/data/ -p 80:80 vaultwarden/server:latest
```
This will preserve any persistent data under /vw-data/, you can adapt the path to whatever suits you.

**IMPORTANT**: Most modern web browsers, disallow the use of Web Crypto APIs in insecure contexts. In this case, you might get an error like `Cannot read property 'importKey'`. To solve this problem, you need to access the web vault via HTTPS or localhost.

This can be configured in [vaultwarden directly](https://github.com/dani-garcia/vaultwarden/wiki/Enabling-HTTPS) or using a third-party reverse proxy ([some examples](https://github.com/dani-garcia/vaultwarden/wiki/Proxy-examples)).

If you have an available domain name, you can get HTTPS certificates with [Let's Encrypt](https://letsencrypt.org/), or you can generate self-signed certificates with utilities like [mkcert](https://github.com/FiloSottile/mkcert). Some proxies automatically do this step, like Caddy (see examples linked above).

## Usage
See the [vaultwarden wiki](https://github.com/dani-garcia/vaultwarden/wiki) for more information on how to configure and run the vaultwarden server.

## Get in touch
To ask a question, offer suggestions or new features or to get help configuring or installing the software, please use [GitHub Discussions](https://github.com/dani-garcia/vaultwarden/discussions) or [the forum](https://vaultwarden.discourse.group/).

If you spot any bugs or crashes with vaultwarden itself, please [create an issue](https://github.com/dani-garcia/vaultwarden/issues/). Make sure you are on the latest version and there aren't any similar issues open, though!

If you prefer to chat, we're usually hanging around at [#vaultwarden:matrix.org](https://matrix.to/#/#vaultwarden:matrix.org) room on Matrix. Feel free to join us!

### Sponsors
Thanks for your contribution to the project!

<!--
<table>
  <tr>
    <td align="center">
      <a href="https://github.com/username">
        <img src="https://avatars.githubusercontent.com/u/725423?s=75&v=4" width="75px;" alt="username"/>
        <br />
        <sub><b>username</b></sub>
      </a>
  </td>
  </tr>
</table>

<br/>
-->

<table>
  <tr>
    <td align="center">
       <a href="https://github.com/themightychris" style="width: 75px">
        <sub><b>Chris Alfano</b></sub>
      </a>
    </td>
  </tr>
  <tr>
    <td align="center">
      <a href="https://github.com/numberly" style="width: 75px">
        <sub><b>Numberly</b></sub>
      </a>
    </td>
  </tr>
</table>
