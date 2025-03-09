# How to setup the desktop

```
    1  sudo apt install nala
    2  sudo nala upgrade
   18  gpg --import /media/atraides/20380fc2-0fb8-4511-8076-abcf210e5f31/*.asc
   23  export KEYID=7869009790BB9080
   24  gpg --command-fd=0 --pinentry-mode=loopback --edit-key "$KEYID" <<EOF
   25  uid *
   26  trust
   27  5
   28  y
   29  save
   30  EOF
   31  gpg -k
   32  cd
   33  cp /media/atraides/20380fc2-0fb8-4511-8076-abcf210e5f31/*.asc ./
   34  ls -ltr
   35  umount /media/atraides/20380fc2-0fb8-4511-8076-abcf210e5f31 
   36  ssh-add -L
   37  gpg -k
   38  gpg --card-status
   39  cd ~/.gnupg
   40  touch scdaemon.conf
   41  echo "disable-ccid" >>scdaemon.conf
   42  sudo nala fetch
   43  sudo nala install -y gnupg gnupg-agent scdaemon pcscd
   44  gpg --card-status
   45  echo -e "\ntest message string" |   gpg --encrypt --armor       --recipient $KEYID --output encrypted.txt
   46  ls -ltr
   47  file encrypted.txt 
   48  rm encrypted.txt 
   49  cd
   50  echo -e "\ntest message string" |   gpg --encrypt --armor       --recipient $KEYID --output encrypted.txt
   51  gpg --decrypt --armor encrypted.txt
   52  rm encrypted.txt 
   53  ls -ltr
   54  ssh-add -L
   55  echo "test message string" | gpg --armor --clearsign > signed.txt
   56  gpg --verify signed.txt
   57  rm signed.txt 
   58  cd ~/.gnupg
   59  wget https://raw.githubusercontent.com/drduh/config/master/gpg-agent.conf
   60  vi gpg-agent.conf 
   61  gpg-connect-agent /bye
   62  vi ~/.bashrc 
   63  ssh-add -L
   64  sudo nala install -y ca-certificates
   65  sudo cp Downloads/ssnw-root.pem.crt /usr/local/share/ca-certificates
   66  sudo update-ca-certificates
   67  cat ~/7869009790BB9080-2025-03-08.asc 
   68  sh -c "$(curl -fsLS get.chezmoi.io)" -- init --apply atraides
   69  sudo nala install curl
   70  sh -c "$(curl -fsLS get.chezmoi.io)" -- init --apply atraides
   71  rm -rf ~/.local/share/chezmoi/
   72  sh -c "$(curl -fsLS get.chezmoi.io)" -- init --apply atraides
   73  ls -ltra
   74  sudo nala install zsh
   75  chsh
   76  sudo nala install starship
   77  curl -sS https://starship.rs/install.sh | sh
   78  zsh
   79  chezmoi update -rv
   80  chezmoi update -Rv
   81  sudo nala install git
   82  chezmoi update -Rv
   83  nitch
   84  cat ~/.zshrc
   85  k get
   86  chezmoi edit ~/.zshrc
   87  which starship
   88  sudo rm /usr/local/bin/starship 
   89  zsh
   90  history
   91  mkdir develop
   92  cd develop/
   93  git clone git@github.com:atraides/homelab.git ssnw-docs
```

```
   1  chsh
    2  which zsh
    3  chsh /usr/bin/zsh
    4  sudo chsh atraides  /usr/bin/zsh
    5  sudo chsh atraides
    6  history
    7  bash
    8  cd ~/.local/share/
    9  cd chezmoi
   10  ls -ltr
   11  cd ..
   12  rm -rf chezmoi
   13  git clone git@github.com:atraides/dotfiles.git chezmoi
   14  ssh-add -L
   15  export GPG_TTY=$(tty)\nexport SSH_AUTH_SOCK=$(gpgconf --list-dirs agent-ssh-socket)\ngpgconf --launch gpg-agent\ngpg-connect-agent updatestartuptty /bye > /dev/null
   16  ssh-add -L
   17  git clone git@github.com:atraides/dotfiles.git chezmoi
   18  cd
   19  chezmoi edit ~/.zshrc
   20  vi ~/.gitconfig
   21  gpg -k
   22  chezmoi update
   23  chezmoi edit ~/.zshrc
   24  chezmoi update
   25  ssh-add -L
   26  chezmoi add ~/.gnupg/gpg.conf
   27  chezmoi add ~/.gnupg/gpg-agent.conf
   28  gpg -k
   29  sudo nala install install dconf-cli uuid-runtime
   30  sudo nala install dconf-cli uuid-runtime
   31  bash -c "$(wget -qO- https://git.io/vQgMr)"
   32  ls -ltr
   33  clear
   34  gpg -k
   35  export KEYID=7869009790BB9080
   36  gpg --keyserver keys.gnupg.net --send-key $KEYID
   37  gpg --send-key $KEYID | curl -T - https://keys.openpgp.org
   38  gpg --card-edit
   39  sudo cp -avir /media/atraides/20380fc2-0fb8-4511-8076-abcf210e5f31/.password-store ~/
   40  umount /media/atraides/20380fc2-0fb8-4511-8076-abcf210e5f31 
   41  pass
   42  sudo nala install pass
   43  pass
   44  pass PGP/Yubikey/Work/Admin\ PIN
   45  ls -ltr ~/.password-store
   46  find ~/.password-store/
   47  find ~/.password-store/ -ls
   48  pass PGP/YubiKey/Master
   49  pass PGP/YubiKey/Master/Admin\ PIN
   50  gpg --card-edit
   51  clear
   52  pyenv 
   53  pyenv list
   54  pyenv versions
   55  pyenv install
   56  pyenv install -l
   57  pyenv install 3.12.7
   58  sudo nala install -y make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev python-openssl git
   59  sudo nala install -y make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev git
   60  sudo apt purge libncurses5
   61  pyenv install 3.12.7
   62  bash
   63  pyenv global 3.12.7
   64  sudo nala upgrade
   65  cd develop/ssnw-docs/docs/guides
   66  lazygit
   67  cd
   68  curl -LO https://github.com/jesseduffield/lazygit/releases/download/v0.48.0/lazygit_0.48.0_Linux_x86_64.tar.gz
   69  rm lazygit_0.48.0_Linux_arm64.tar.gz
   70  ls -ltr
   71  rm README.md LICENSE
   72  cd bin
   73  tar -zxvf ../lazygit_0.48.0_Linux_x86_64.tar.gz
   74  rm LICENSE README.md
   75  ls -ltr
   76  cd develop/ssnw-docs/docs/guides
   77  lazygit
   78  sudo nala install pipx
   79  pipx ensurepath
   80  sudo pipx ensurepath --global # optional to allow pipx actions with --global argument\n
   81  sudo pipx ensurepath --global
   82  sudo pipx ensurepath 
   83  pipx ensurepath 
   84  pipx install commitizen
   85  cd develop/ssnw-docs/docs/
   86  cd ..
   87  vi .github/workflows/gh-pages.yml
   88  cz
   89  cz init
   90  cz
   91  cz c
   92  ga
   93  gaa
   94  cz
   95  cz c
   96  cz bump
   97  cz push
   98  gpsup
```
