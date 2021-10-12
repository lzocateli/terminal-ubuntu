### Personalizando ZSH com posh-git + Oh My Posh

>Esse procedimento foi realizado no WSL2 com Ubuntu 20.04   
Tenha o VsCode já instalado   

#### 1. Instale o ZSH no Ubuntu ####   
**Abra o terminal Ubuntu**

```bash
sudo apt install zsh
```
- Torne o zsh seu shell padrão
```bash
chsh -s $(which zsh)
```
#### 2. Feche seu terminal e reabra novamente ####  
**Ao usar o zsh pela primeira vez, configure o arquivo ~/.zshrc**

![ZSH Primeiro acesso](https://github.com/lzocateli00/terminal-ubuntu/blob/1affdaa1cc0813380c7865aea4a9d443af73cc02/images/zsh-primeiro-acesso.jpg)

- Faça as configurações recomendadas:

![Configurações recomendadas](https://github.com/lzocateli00/terminal-ubuntu/blob/1affdaa1cc0813380c7865aea4a9d443af73cc02/images/Zsh-Main-menu-recommended.png)

![Salve as configurações feitas](https://github.com/lzocateli00/terminal-ubuntu/blob/1affdaa1cc0813380c7865aea4a9d443af73cc02/images/Zsh-Main-menu-recommended-save.png)

![Configure ou copie o conteudo do seu .bashrc para .zshrc](https://github.com/lzocateli00/terminal-ubuntu/blob/1affdaa1cc0813380c7865aea4a9d443af73cc02/images/Zsh-new-users.png)

- Caso necessite voltar ao menu do zsh digite:
```bash
autoload -Uz zsh-newuser-install
zsh-newuser-install -f
```

#### 3. Instale o oh-my-posh ####   

- Esse módulo permite a personalização de temas e fontes mais amigáveis.   
- Veja a documentação [aqui](https://ohmyposh.dev/docs/) para escolher seu tema preferido, caso o tema que sugiro não te agrade.   

```bash
sudo wget https://github.com/JanDeDobbeleer/oh-my-posh/releases/latest/download/posh-linux-amd64 -O /usr/local/bin/oh-my-posh
sudo chmod +x /usr/local/bin/oh-my-posh
```

#### 4. Instale os arquivos de configurações dos temas ###     
**Execute uma linha por vez**

- Instale o unzip, caso ainda não tenha
```bash
sudo apt install unzip
```

```bash
mkdir ~/.poshthemes
wget https://github.com/JanDeDobbeleer/oh-my-posh/releases/latest/download/themes.zip -O ~/.poshthemes/themes.zip
unzip ~/.poshthemes/themes.zip -d ~/.poshthemes
chmod u+rw ~/.poshthemes/*.json
rm ~/.poshthemes/themes.zip
```
#### 5. Copie o arquivo com o tema para sua pasta home ####  

```bash
cp ~/.poshthemes/slimfat.omp.json ~
```
- Adicione o comando abaixo no arquivo ~/.zshrc , substitua o arquivo json pelo que você escolher
```bash
eval "$(oh-my-posh --init --shell zsh --config ~/slimfat.omp.json)"
```
- Recarregue seu perfil com o seguinte comando
```bash
source ~/.zshrc
```
#### 6. Configure a fonte para o Windows Terminal (PowerShell) ####  

![Windows Start](https://github.com/lzocateli00/terminal-windows/blob/37631020d9abeac1802e29231de79cd14d17f561/images/WindowsTerminal.png)

![Windows Terminal-Settings](https://github.com/lzocateli00/terminal-windows/blob/37631020d9abeac1802e29231de79cd14d17f561/images/WindowsTerminal-Settings.png)

![Terminal-Font](https://github.com/lzocateli00/terminal-ubuntu/blob/5319c4f5e91429f5f37eb44687e88cd4ebc503bb/images/Terminal-font.jpg)

- Feche o Windows Terminal
- Abra o Windows Terminal, sua linha de comando, em uma pasta de projeto com git, com dotnet, deve ter essa aparencia:

![Linux Terminal](https://github.com/lzocateli00/terminal-ubuntu/blob/abd79735517366e4e06b1cae6487d54182aa8cf1/images/Terminal-final.jpg)

- Se quiser personalizar, abra o arquivo do tema que fica na pasta $HOME 
 
```bash
code ~/slimfat.omp.json 
```
Codigo Unicode para "seta" do prompt: ➠  ou \u27A0
 
 #### 7. Configure a fonte para o terminal do VsCode ####  

- Abra o VsCode, depois vá para as configurações do usuario ( CTRL + , )
- Configure a fonte para o terminal, copie no campo indicado: MesloLGM NF   

![VsCode Font](https://github.com/lzocateli00/terminal-windows/blob/37631020d9abeac1802e29231de79cd14d17f561/images/VsCode-Meslo.png)

- Pode fechar o vscode e abrir novamente, o terminal já estara com a nova configuração.


- Referencias: [Unicode Table](https://unicode-table.com/en)
