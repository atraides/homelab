# How to setup the desktop

```
sudo apt install nala
sudo nala upgrade
gpg --import /media/atraides/20380fc2-0fb8-4511-8076-abcf210e5f31/*.asc
export KEYID=7869009790BB9080
gpg --command-fd=0 --pinentry-mode=loopback --edit-key "$KEYID" <<EOF
uid *
trust
5
y
save
EOF
gpg -k
cd
cp /media/atraides/20380fc2-0fb8-4511-8076-abcf210e5f31/*.asc ./
ls -ltr
umount /media/atraides/20380fc2-0fb8-4511-8076-abcf210e5f31 
ssh-add -L
gpg -k
gpg --card-status
cd ~/.gnupg
touch scdaemon.conf
echo "disable-ccid" >>scdaemon.conf
sudo nala fetch
sudo nala install -y gnupg gnupg-agent scdaemon pcscd
gpg --card-status
echo -e "\ntest message string" |   gpg --encrypt --armor       --recipient $KEYID --output encrypted.txt
ls -ltr
file encrypted.txt 
rm encrypted.txt 
cd
echo -e "\ntest message string" |   gpg --encrypt --armor       --recipient $KEYID --output encrypted.txt
gpg --decrypt --armor encrypted.txt
rm encrypted.txt 
ls -ltr
ssh-add -L
echo "test message string" | gpg --armor --clearsign > signed.txt
gpg --verify signed.txt
rm signed.txt 
cd ~/.gnupg
wget https://raw.githubusercontent.com/drduh/config/master/gpg-agent.conf
vi gpg-agent.conf 
gpg-connect-agent /bye
vi ~/.bashrc 
ssh-add -L
sudo nala install -y ca-certificates
sudo cp Downloads/ssnw-root.pem.crt /usr/local/share/ca-certificates
sudo update-ca-certificates
cat ~/7869009790BB9080-2025-03-08.asc 
sh -c "$(curl -fsLS get.chezmoi.io)" -- init --apply atraides
sudo nala install curl
sh -c "$(curl -fsLS get.chezmoi.io)" -- init --apply atraides
rm -rf ~/.local/share/chezmoi/
sh -c "$(curl -fsLS get.chezmoi.io)" -- init --apply atraides
ls -ltra
sudo nala install zsh
chsh
sudo nala install starship
curl -sS https://starship.rs/install.sh | sh
zsh
chezmoi update -rv
chezmoi update -Rv
sudo nala install git
chezmoi update -Rv
nitch
cat ~/.zshrc
k get
chezmoi edit ~/.zshrc
which starship
sudo rm /usr/local/bin/starship 
zsh
history
mkdir develop
cd develop/
git clone git@github.com:atraides/homelab.git ssnw-docs
```

```
chsh
which zsh
chsh /usr/bin/zsh
sudo chsh atraides  /usr/bin/zsh
sudo chsh atraides
history
bash
cd ~/.local/share/
cd chezmoi
ls -ltr
cd ..
rm -rf chezmoi
git clone git@github.com:atraides/dotfiles.git chezmoi
ssh-add -L
export GPG_TTY=$(tty)\nexport SSH_AUTH_SOCK=$(gpgconf --list-dirs agent-ssh-socket)\ngpgconf --launch gpg-agent\ngpg-connect-agent updatestartuptty /bye > /dev/null
ssh-add -L
git clone git@github.com:atraides/dotfiles.git chezmoi
cd
chezmoi edit ~/.zshrc
vi ~/.gitconfig
gpg -k
chezmoi update
chezmoi edit ~/.zshrc
chezmoi update
ssh-add -L
chezmoi add ~/.gnupg/gpg.conf
chezmoi add ~/.gnupg/gpg-agent.conf
gpg -k
sudo nala install install dconf-cli uuid-runtime
sudo nala install dconf-cli uuid-runtime
bash -c "$(wget -qO- https://git.io/vQgMr)"
ls -ltr
clear
gpg -k
export KEYID=7869009790BB9080
gpg --keyserver keys.gnupg.net --send-key $KEYID
gpg --send-key $KEYID | curl -T - https://keys.openpgp.org
gpg --card-edit
sudo cp -avir /media/atraides/20380fc2-0fb8-4511-8076-abcf210e5f31/.password-store ~/
umount /media/atraides/20380fc2-0fb8-4511-8076-abcf210e5f31 
pass
sudo nala install pass
pass
pass PGP/Yubikey/Work/Admin\ PIN
ls -ltr ~/.password-store
find ~/.password-store/
find ~/.password-store/ -ls
pass PGP/YubiKey/Master
pass PGP/YubiKey/Master/Admin\ PIN
gpg --card-edit
clear
pyenv 
pyenv list
pyenv versions
pyenv install
pyenv install -l
pyenv install 3.12.7
sudo nala install -y make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev python-openssl git
sudo nala install -y make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev git
sudo apt purge libncurses5
pyenv install 3.12.7
bash
pyenv global 3.12.7
sudo nala upgrade
cd develop/ssnw-docs/docs/guides
lazygit
cd
curl -LO https://github.com/jesseduffield/lazygit/releases/download/v0.48.0/lazygit_0.48.0_Linux_x86_64.tar.gz
rm lazygit_0.48.0_Linux_arm64.tar.gz
ls -ltr
rm README.md LICENSE
cd bin
tar -zxvf ../lazygit_0.48.0_Linux_x86_64.tar.gz
rm LICENSE README.md
ls -ltr
cd develop/ssnw-docs/docs/guides
lazygit
sudo nala install pipx
pipx ensurepath
sudo pipx ensurepath --global # optional to allow pipx actions with --global argument\n
sudo pipx ensurepath --global
sudo pipx ensurepath 
pipx ensurepath 
pipx install commitizen
cd develop/ssnw-docs/docs/
cd ..
vi .github/workflows/gh-pages.yml
cz
cz init
cz
cz c
ga
gaa
cz
cz c
cz bump
cz push
gpsup
```
