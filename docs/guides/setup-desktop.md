# How to setup the desktop

```
    1  sudo apt install nala
    2  sudo nala upgrade
    3  cd $GNUPGHOME
    4  cd $GNUPGHOME
    5  wget https://raw.githubusercontent.com/drduh/config/master/gpg.conf
    6  pwd
    7  rm gpg.conf 
    8  echo $GNUPGHOME
    9  gpg
   10  gpg -k
   11  echo $GNUPGHOME
   12  mkdir ~/.gnupg
   13  cd ~/.gnupg/
   14  wget https://raw.githubusercontent.com/drduh/config/master/gpg.conf
   15  grep -ve "^#" $GNUPGHOME/gpg.conf
   16  export GNUPGHOME=~/.gnupg/
   17  grep -ve "^#" $GNUPGHOME/gpg.conf
   18  gpg --import /media/atraides/20380fc2-0fb8-4511-8076-abcf210e5f31/*.asc
   19  gpg -K
   20  gpg -k
   21  gpg --delete-keys F8AFF395491002AD C145CF402E7AD349 AF294F634C704603
   22  gpg -k
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
