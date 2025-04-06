# 🧾 Instalação do PlayOnLinux no Ubuntu 24.04 via Flatpak (Para versões recentes do kubuntu que ainda não suportam o playonlinux)

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

## 🧪 3. Instale o PlayOnLinux via Flatpak

```bash
flatpak install flathub org.phoenicis.playonlinux -y
```

---

## ▶️ 4. Execute o PlayOnLinux

Para abrir o programa, execute o comando:

```bash
flatpak run org.phoenicis.playonlinux
```

---

## 📍 5. Criar um atalho gráfico no menu do sistema

Após a instalação via Flatpak, o atalho gráfico do PlayOnLinux geralmente **já aparece automaticamente no menu** do seu sistema, na categoria de **Jogos** ou **Acessórios**.

### ❗ Se não aparecer:

Você pode criar manualmente um atalho `.desktop` com os seguintes passos:

1. Crie o arquivo de atalho:

   ```bash
   nano ~/.local/share/applications/playonlinux.desktop
   ```

2. Cole o conteúdo abaixo no arquivo:

   ```ini
   [Desktop Entry]
   Name=PlayOnLinux
   Comment=Instale e gerencie aplicativos do Windows com Wine
   Exec=flatpak run org.phoenicis.playonlinux
   Icon=org.phoenicis.playonlinux
   Terminal=false
   Type=Application
   Categories=Utility;Game;
   ```

3. Salve com `CTRL + O`, depois `ENTER`, e saia com `CTRL + X`.

4. Torne o atalho executável:

   ```bash
   chmod +x ~/.local/share/applications/playonlinux.desktop
   ```

Agora o **PlayOnLinux aparecerá no menu de aplicativos**, como qualquer outro programa nativo.

---

## 📎 (Opcional) Criar um alias para facilitar a execução via terminal

```bash
echo "alias playonlinux='flatpak run org.phoenicis.playonlinux'" >> ~/.bashrc
source ~/.bashrc
```

---

## 🧽 (Opcional) Desinstalar o PlayOnLinux via Flatpak

```bash
flatpak uninstall org.phoenicis.playonlinux
```

---

## ✅ Conclusão

Utilizar o PlayOnLinux via Flatpak garante a **versão mais recente e estável**, com instalação simples e compatível com o Ubuntu 24.04.  
Com o atalho gráfico, você pode acessar o app de forma prática pelo menu do sistema.

---
