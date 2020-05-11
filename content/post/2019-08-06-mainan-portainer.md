---
title: "Manage Docker lebih mudah dengan Portainer"
date: "2019-08-06T22:18:38+07:00"
read: "5 min"
tags: ["Docker", "Tools", "TipsAndTricks"]
categories: ["Docker", "Tools", "TipsAndTricks"]
draft: false
---

Halo Temans, bagi kalian yang suka ~~mainan~~ manage docker. Ada tools menarik nih biar mempermudah temans memanage docker. Dia adalah [Portainer](https://portainer.io). Selain open source alias gratis, Portainer ini menyediakan berbagai fitur mulai dari Dashboard, informasi Container, Docker images, App Templates, Docker Stacks, Networks, Volumes, Host Information, sampai melihat real-time dari Memory Usage, CPU Usage dari container. Banyak sekali fitur yang ada di Portainer ini. 

{{< img src="/images/2019-08-06_portainer_dashboard_keriwilan_com.png" title="Dashboard Portainer - Keriwilan.com" alt="Dashboard Portainer - Keriwilan.com">}}

Temans juga dapat melakukan exec ke console container dengan sangat mudah. Untuk dapat menggunakan Portainer ini, cukup mudah sekali. Pastikan workstation temans sudah terinstall Docker Engine yaa. 

Kalau belum, ikuti saja langkah instalasi yang ada di dokumentasi resminya si [Docker Docs](https://docs.docker.com/v17.12/cs-engine/1.13/). Pastikan sesuai dengan OS temans. 

{{< img src="/images/2019-08-06_portainer_console_keriwilan_com.png" title="Run bash command in container - Keriwilan.com" alt="Exec in Container - Keriwilan.com">}}

Lalu ikuti steps dibawah ini yaa:

```bash
# untuk mendownload image portainer dari docker hub
$docker pull portainer/portainer 

# run docker & buka di browser localhost:9000
$docker run --rm -d -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer $
```


#### Bonus Tips
Buat temans yang menyukai gaya bekerja yang ~~males~~ efisien, temans bisa bikin nih alias di bash shell atau CLI temans. Cukup mudah untuk bash shell. 

```bash
$vi ~/.bash_profile #atau $nano ~/.bash_profile

# Tambahkan alias seperti di bawah ini di line terakhir file .bash_profile dan simpan
alias docker-port="docker run --rm -d -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer"

# Eksekusi script bash_profile
$source ~/.bash_profile
```

Nah alias sudah dibuat. Temans kalo mau run portainer, cukup panggil `docker-port` aja di terminal. Lalu buka `localhost:9000` di browser. Tadaa! Mudah bukan.

Bagi temans yang suka dengan CLI(*Command Line Interface*), temans bisa nih gunain si [Lazydocker](https://github.com/jesseduffield/lazydocker). Cuman dari fitur lebih banyak si Portainer yaa. Hahaaa

#### Sekilas
Dari lihat [roadmap Portainer](https://github.com/portainer/portainer/projects/2) si Portainer ini. di versi 2.0 mereka akan support untuk `Kubernetes`. Menarik yaah. Kita tunggu sajaa temans :D. Eih kok tunggu, temans bisa contribute nih di [Github Portainer](https://github.com/portainer/portainer). Yuk kita dukung project open source temans. Contribute saja ke [Github Portainer](https://github.com/portainer/portainer) dan paling tidak relakan satu `star` temans untuk apresiasi kita :)

Kalau ada kesulitan atau ada hal-hal yang ingin didiskusikan. Komens temans ditunggu dibawah yaa! 