# 🧾 Instalação do PlayOnLinux no Ubuntu 24.04 via Flatpak (Para versões recentes do Kubuntu que ainda não suportam o PlayOnLinux)

O **PlayOnLinux** é uma interface gráfica que facilita a instalação e o gerenciamento de softwares Windows no Linux utilizando o **Wine**.  
Abaixo está um passo a passo atualizado para instalar o PlayOnLinux via **Flatpak**, ideal para usuários do **Ubuntu 24.04 LTS**, incluindo variantes como **Kubuntu**.

---

## 📦 1. Instale o Flatpak (se ainda não estiver instalado)

```bash
sudo apt update
sudo apt install flatpak -y
```

---

## 🌐 2. Adicione o repositório Flathub (caso ainda não tenha)

O **Flathub** é a principal fonte de aplicativos Flatpak.

```bash
sudo flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

---

## 🧪 3. Instale o PlayOnLinux (versão antiga compatível) via Flatpak

A versão moderna do PlayOnLinux (`org.phoenicis.playonlinux`) não oferece suporte direto à Steam nem à instalação clássica de jogos como **Morrowind**.  
Por isso, usamos a **versão antiga (PlayOnLinux 4)**:

```bash
flatpak install flathub com.playonlinux.PlayOnLinux4 -y
```

---

## ▶️ 4. Execute o PlayOnLinux

Para abrir o programa:

```bash
flatpak run com.playonlinux.PlayOnLinux4
```

---

## 📍 5. Criar um atalho gráfico no menu do sistema

O atalho do PlayOnLinux 4 geralmente aparece no menu automaticamente.  
Se **não aparecer**, você pode criá-lo manualmente:

### Criar arquivo `.desktop`

```bash
nano ~/.local/share/applications/playonlinux.desktop
```

### Conteúdo do arquivo:

```ini
[Desktop Entry]
Name=PlayOnLinux 4
Comment=Instale e gerencie aplicativos do Windows com Wine
Exec=flatpak run com.playonlinux.PlayOnLinux4
Icon=com.playonlinux.PlayOnLinux4
Terminal=false
Type=Application
Categories=Utility;Game;
```

### Salve e feche o arquivo (`CTRL + O`, `ENTER`, `CTRL + X`)

### Torne o atalho executável:

```bash
chmod +x ~/.local/share/applications/playonlinux.desktop
```

---

## 📎 (Opcional) Criar um alias para terminal

```bash
echo "alias playonlinux='flatpak run com.playonlinux.PlayOnLinux4'" >> ~/.bashrc
source ~/.bashrc
```

---

## 🧽 (Opcional) Desinstalar o PlayOnLinux via Flatpak

```bash
flatpak uninstall com.playonlinux.PlayOnLinux4
```

---

## ✅ Conclusão

Usar o **PlayOnLinux 4 via Flatpak** é a melhor opção para quem quer rodar jogos e aplicativos antigos, como o **Morrowind via Steam**, mantendo compatibilidade e estabilidade mesmo nas versões mais recentes do Ubuntu/Kubuntu.

---
