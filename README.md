<div align="center">
  <br>
  <img width="360" style="max-width:80%" src=".github/brand.svg" title="哪吒监控 Nezha Monitoring">
  <br>
  <small><i>LOGO designed by <a href="https://xio.ng" target="_blank">熊大</a> .</i></small>
  <br><br>
<img alt="GitHub release (with filter)" src="https://img.shields.io/github/v/release/nezhahq/nezha?color=brightgreen&style=for-the-badge&logo=github&label=Dashboard">&nbsp;<img src="https://img.shields.io/github/v/release/nezhahq/agent?color=brightgreen&label=Agent&style=for-the-badge&logo=github">&nbsp;<img src="https://img.shields.io/github/actions/workflow/status/nezhahq/agent/agent.yml?label=Agent%20CI&logo=github&style=for-the-badge">&nbsp;<a href="https://hosted.weblate.org/engage/nezha/"><img src="https://img.shields.io/weblate/progress/nezha?color=brightgreen&label=Translated&style=for-the-badge&logo=weblate" alt="Translation status" /></a>
  <br>
  <br>
  <p>:trollface: <b>Nezha Monitoring: Self-hostable, lightweight, servers and websites monitoring and O&M tool.</b></p>
  <p>Supports <b>monitoring</b> system status, HTTP (SSL certificate change, upcoming expiration, expired), TCP, Ping and supports <b>push alerts</b>, run scheduled tasks and <b>web terminal</b>.</p>
</div>

\>> Official Forum | 官方论坛: [有点意思](https://lajilao.com/c/nezha)<br>
\>> Telegram Channel: [哪吒监控（中文通知频道）](https://t.me/nezhanews)<br>

\>> [Use Cases | 我们的用户](https://www.google.com/search?q=%22%E5%93%AA%E5%90%92%E7%9B%91%E6%8E%A7+Nezha+Monitoring%22) (Google) <br>
<sub>\>> Telegram Group: [Nezha Monitoring Global (English Only)](https://t.me/nezhamonitoring_global), [哪吒监控（中文群组）](https://t.me/nezhamonitoring)</sub>


## User Guide

- [English](https://nezhahq.github.io/en_US/index.html)
- [中文文档](https://nezhahq.github.io/index.html)

## Instalation
**install Nezha Monitoring** di VPS (Ubuntu 20.04/22.04). Nezha adalah panel monitoring seperti uptime monitor (mirip dengan Uptime Kuma) yang menggunakan agen client-server.

---

## 🔧 Persiapan

1. Gunakan VPS dengan sistem operasi **Ubuntu 20.04 / 22.04**.
2. Akses root atau user dengan sudo.
3. Port yang harus terbuka:

   * **TCP 80 & 443** (web dashboard)
   * **TCP 5555** (default Nezha server port)
   * **UDP 443** (untuk agen komunikasi via QUIC)

---

## 🖥️ Install Nezha Server

### 1. Update & Install dependencies

```bash
sudo apt update && sudo apt install -y curl wget unzip socat
```

### 2. Install Docker & Docker Compose

```bash
curl -fsSL https://get.docker.com | bash
```

---

### 3. Jalankan Script Auto Install Server

Gunakan script resmi Nezha Server (dari GitHub):

```bash
bash <(curl -Ls https://raw.githubusercontent.com/heruhendri/nezhahq/main/script/install_server.sh)
```

Ikuti instruksi:

* Masukkan domain (wajib sudah mengarah ke IP VPS)
* Script akan mengatur SSL otomatis via `acme.sh`
* Setelah selesai, panel akan tersedia di `https://domain-anda`

---

## 🧾 Login Nezha Panel

Setelah berhasil, buka `https://domain-anda`
Login default:

* **Username:** `admin`
* **Password:** `admin`

Ganti password setelah login pertama.

---

## ⚙️ Install Nezha Agent (Di VPS/Server yang akan dimonitor)

Login ke dashboard → Tambah Agen → Salin perintah install agent.
Contoh perintah:

```bash
bash <(curl -Ls https://raw.githubusercontent.com/nezhahq/nezhahq/main/script/install_agent.sh) \
--server your-domain.com:443 --key AGENT-KEY
```

> Pastikan VPS agent bisa konek ke domain server Nezha (port 443 UDP terbuka).

---

## 🔁 Cek Status

* Setelah agent dijalankan, status server akan muncul di dashboard.
* Jika tidak muncul, pastikan port dan domain benar.

---

## 📌 Tips Tambahan

* Gunakan Cloudflare DNS untuk domain.
* Aktifkan firewall hanya jika port 80, 443, dan 5555 (TCP) serta 443 (UDP) dibuka.
* Untuk multi-server monitoring, cukup jalankan agent di tiap VPS.

---



## Contributing

### Translation

<a href="https://hosted.weblate.org/engage/nezha/">
<img src="https://hosted.weblate.org/widget/nezha/multi-blue.svg" alt="Translation status" />
</a>

Is Nezha not in your language, or the translation is incorrect or incomplete? Get involved in the translations on [Hosted Weblate](https://hosted.weblate.org/engage/nezha/).

## Screenshots

| 用户前台 [@hamster1963](https://github.com/hamster1963) | 管理后台 [@nezhahq](https://github.com/nezhahq) |
|---|---|
| ![user](.github/user-frontend.20241128.png)  | ![admin](.github/admin-frontend.20241220.jpg)  |
| [hamster1963/nezha-dash](https://github.com/hamster1963/nezha-dash)  | [nezhahq/admin-frontend](https://github.com/nezhahq/admin-frontend)  |

add your theme to [service/singleton/frontend-templates.yaml](service/singleton/frontend-templates.yaml)

## Contributors

<!--GAMFC_DELIMITER--><a href="https://github.com/naiba" title="naiba"><img src="https://avatars.githubusercontent.com/u/29243953?v=4" width="50;" alt="naiba"/></a>
<a href="https://github.com/uubulb" title="UUBulb"><img src="https://avatars.githubusercontent.com/u/35923940?v=4" width="50;" alt="UUBulb"/></a>
<a href="https://github.com/AkkiaS7" title="Akkia"><img src="https://avatars.githubusercontent.com/u/68485070?v=4" width="50;" alt="Akkia"/></a>
<a href="https://github.com/Erope" title="卖女孩的小火柴"><img src="https://avatars.githubusercontent.com/u/44471469?v=4" width="50;" alt="卖女孩的小火柴"/></a>
<a href="https://github.com/nap0o" title="nap0o"><img src="https://avatars.githubusercontent.com/u/144927971?v=4" width="50;" alt="nap0o"/></a>
<a href="https://github.com/dysf888" title="黑歌"><img src="https://avatars.githubusercontent.com/u/47450409?v=4" width="50;" alt="黑歌"/></a>
<a href="https://github.com/xykt" title="xykt"><img src="https://avatars.githubusercontent.com/u/152045469?v=4" width="50;" alt="xykt"/></a>
<a href="https://github.com/MikoyChinese" title="MikoyChinese"><img src="https://avatars.githubusercontent.com/u/22676744?v=4" width="50;" alt="MikoyChinese"/></a>
<a href="https://github.com/JackieSung4ev" title="JackieSung4ev"><img src="https://avatars.githubusercontent.com/u/24974735?v=4" width="50;" alt="JackieSung4ev"/></a>
<a href="https://github.com/weblate" title="Weblate (bot)"><img src="https://avatars.githubusercontent.com/u/1607653?v=4" width="50;" alt="Weblate (bot)"/></a>
<a href="https://github.com/cantoblanco" title="Kris"><img src="https://avatars.githubusercontent.com/u/116849421?v=4" width="50;" alt="Kris"/></a>
<a href="https://github.com/lemoeo" title="Lemoe"><img src="https://avatars.githubusercontent.com/u/18618627?v=4" width="50;" alt="Lemoe"/></a>
<a href="https://github.com/spiritLHLS" title="spiritlhl"><img src="https://avatars.githubusercontent.com/u/103393591?v=4" width="50;" alt="spiritlhl"/></a>
<a href="https://github.com/liuyanxi975" title="刘颜溪"><img src="https://avatars.githubusercontent.com/u/24417037?v=4" width="50;" alt="刘颜溪"/></a>
<a href="https://github.com/CosmosZ-code" title="CosmosZ-code"><img src="https://avatars.githubusercontent.com/u/81398224?v=4" width="50;" alt="CosmosZ-code"/></a>
<a href="https://github.com/lvgj-stack" title="Ko no dio"><img src="https://avatars.githubusercontent.com/u/38449861?v=4" width="50;" alt="Ko no dio"/></a>
<a href="https://github.com/hhhkkk520" title="Kris"><img src="https://avatars.githubusercontent.com/u/52115472?v=4" width="50;" alt="Kris"/></a>
<a href="https://github.com/Mmx233" title="Mmx233"><img src="https://avatars.githubusercontent.com/u/36563672?v=4" width="50;" alt="Mmx233"/></a>
<a href="https://github.com/rootmelo92118" title="rootmelo92118"><img src="https://avatars.githubusercontent.com/u/32770959?v=4" width="50;" alt="rootmelo92118"/></a>
<a href="https://github.com/Moraxyc" title="Moraxyc"><img src="https://avatars.githubusercontent.com/u/69713071?v=4" width="50;" alt="Moraxyc"/></a>
<a href="https://github.com/1ridic" title="1ridic"><img src="https://avatars.githubusercontent.com/u/88495501?v=4" width="50;" alt="1ridic"/></a>
<a href="https://github.com/hamster1963" title="仓鼠"><img src="https://avatars.githubusercontent.com/u/71394853?v=4" width="50;" alt="仓鼠"/></a>
<a href="https://github.com/zhucaidan" title="zhucaidan"><img src="https://avatars.githubusercontent.com/u/47970938?v=4" width="50;" alt="zhucaidan"/></a>
<a href="https://github.com/iilemon" title="Sean"><img src="https://avatars.githubusercontent.com/u/33201711?v=4" width="50;" alt="Sean"/></a>
<a href="https://github.com/lyj0309" title="lyj"><img src="https://avatars.githubusercontent.com/u/50474995?v=4" width="50;" alt="lyj"/></a>
<a href="https://github.com/fscarmen" title="fscarmen"><img src="https://avatars.githubusercontent.com/u/62703343?v=4" width="50;" alt="fscarmen"/></a>
<a href="https://github.com/ch8o" title="no-name-now"><img src="https://avatars.githubusercontent.com/u/9103372?v=4" width="50;" alt="no-name-now"/></a>
<a href="https://github.com/MemoryShadow" title="JSker9"><img src="https://avatars.githubusercontent.com/u/31596045?v=4" width="50;" alt="JSker9"/></a>
<a href="https://github.com/HsukqiLee" title="Hsukqi Lee"><img src="https://avatars.githubusercontent.com/u/79034142?v=4" width="50;" alt="Hsukqi Lee"/></a>
<a href="https://github.com/DarcJC" title="Darc Z."><img src="https://avatars.githubusercontent.com/u/53445798?v=4" width="50;" alt="Darc Z."/></a>
<a href="https://github.com/Creling" title="Creling"><img src="https://avatars.githubusercontent.com/u/43109504?v=4" width="50;" alt="Creling"/></a>
<a href="https://github.com/coreff" title="Core F"><img src="https://avatars.githubusercontent.com/u/38347122?v=4" width="50;" alt="Core F"/></a>
<a href="https://github.com/adminsama" title="adminsama"><img src="https://avatars.githubusercontent.com/u/60880076?v=4" width="50;" alt="adminsama"/></a>
<a href="https://github.com/acgpiano" title="Acgpiano"><img src="https://avatars.githubusercontent.com/u/15900800?v=4" width="50;" alt="Acgpiano"/></a>
<a href="https://github.com/eya46" title="eya46"><img src="https://avatars.githubusercontent.com/u/61458340?v=4" width="50;" alt="eya46"/></a>
<a href="https://github.com/guoyongchang" title="guoyongchang"><img src="https://avatars.githubusercontent.com/u/10484506?v=4" width="50;" alt="guoyongchang"/></a>
<a href="https://github.com/hiDandelion" title="hiDandelion"><img src="https://avatars.githubusercontent.com/u/77157418?v=4" width="50;" alt="hiDandelion"/></a>
<a href="https://github.com/yuanweize" title="I"><img src="https://avatars.githubusercontent.com/u/30067203?v=4" width="50;" alt="I"/></a>
<a href="https://github.com/igophper" title="igophper"><img src="https://avatars.githubusercontent.com/u/34326532?v=4" width="50;" alt="igophper"/></a>
<a href="https://github.com/lvyaoting" title="lvyaoting"><img src="https://avatars.githubusercontent.com/u/166296299?v=4" width="50;" alt="lvyaoting"/></a>
<a href="https://github.com/quanljh" title="quanljh"><img src="https://avatars.githubusercontent.com/u/38105306?v=4" width="50;" alt="quanljh"/></a>
<a href="https://github.com/unclezs" title="unclezs"><img src="https://avatars.githubusercontent.com/u/42318775?v=4" width="50;" alt="unclezs"/></a>
<a href="https://github.com/ysicing" title="缘生"><img src="https://avatars.githubusercontent.com/u/8605565?v=4" width="50;" alt="缘生"/></a>
<a href="https://github.com/yanhao98" title="严浩"><img src="https://avatars.githubusercontent.com/u/37316281?v=4" width="50;" alt="严浩"/></a>
<a href="https://github.com/arkylin" title="凌"><img src="https://avatars.githubusercontent.com/u/35104502?v=4" width="50;" alt="凌"/></a>
<a href="https://github.com/yumusb" title="榆木"><img src="https://avatars.githubusercontent.com/u/43062104?v=4" width="50;" alt="榆木"/></a>
<a href="https://github.com/colour93" title="93"><img src="https://avatars.githubusercontent.com/u/64313711?v=4" width="50;" alt="93"/></a>
<a href="https://github.com/hmsjy2017" title="Tony"><img src="https://avatars.githubusercontent.com/u/42692274?v=4" width="50;" alt="Tony"/></a>
<a href="https://github.com/TomyJan" title="TomyJan"><img src="https://avatars.githubusercontent.com/u/67973160?v=4" width="50;" alt="TomyJan"/></a>
<a href="https://github.com/nickfox-taterli" title="Tater Li"><img src="https://avatars.githubusercontent.com/u/19658596?v=4" width="50;" alt="Tater Li"/></a>
<a href="https://github.com/IamTaoChen" title="Tao Chen"><img src="https://avatars.githubusercontent.com/u/42793494?v=4" width="50;" alt="Tao Chen"/></a>
<a href="https://github.com/Septrum101" title="Spetrum"><img src="https://avatars.githubusercontent.com/u/11692994?v=4" width="50;" alt="Spetrum"/></a>
<a href="https://github.com/dreamingsleeping" title="Nanjing Hopefun Network Technology Co. Ltd."><img src="https://avatars.githubusercontent.com/u/13828658?v=4" width="50;" alt="Nanjing Hopefun Network Technology Co. Ltd."/></a>
<a href="https://github.com/silver-ymz" title="Mingzhuo Yin"><img src="https://avatars.githubusercontent.com/u/78400701?v=4" width="50;" alt="Mingzhuo Yin"/></a>
<a href="https://github.com/MartijnLindeman" title="Martijn Lindeman"><img src="https://avatars.githubusercontent.com/u/78365708?v=4" width="50;" alt="Martijn Lindeman"/></a>
<a href="https://github.com/funnyzak" title="Leon"><img src="https://avatars.githubusercontent.com/u/2562087?v=4" width="50;" alt="Leon"/></a>
<a href="https://github.com/KorenKrita" title="KorenKrita"><img src="https://avatars.githubusercontent.com/u/22239339?v=4" width="50;" alt="KorenKrita"/></a>
<a href="https://github.com/techotaku" title="Ian Li"><img src="https://avatars.githubusercontent.com/u/1948179?v=4" width="50;" alt="Ian Li"/></a>
<a href="https://github.com/GreenTeodoro839" title="GreenTeodoro839"><img src="https://avatars.githubusercontent.com/u/77104800?v=4" width="50;" alt="GreenTeodoro839"/></a>
<a href="https://github.com/Es-dese" title="Esdese"><img src="https://avatars.githubusercontent.com/u/71542548?v=4" width="50;" alt="Esdese"/></a>
<a href="https://github.com/wwng2333" title=":D"><img src="https://avatars.githubusercontent.com/u/17147265?v=4" width="50;" alt=":D"/></a>
<a href="https://github.com/wellcoming" title="Coming"><img src="https://avatars.githubusercontent.com/u/74850890?v=4" width="50;" alt="Coming"/></a><!--GAMFC_DELIMITER_END-->

## Special Thanks
- [IPInfo](https://ipinfo.io/) for providing an accurate GeoIP Database.

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=nezhahq/nezha&type=Timeline)](https://star-history.com/#nezhahq/nezha&Timeline)
