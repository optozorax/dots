# Основа

Использовать Pop!\_OS, потому что там из коробки поддерживаются дрова NVIDIA, и всё плавно работает.

# Установить через центр приложений:

* Spotify
* Sublime Merge
* Telegram

# Rust

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

```bash
cargo install bat ripgrep starship
```

* `bat` - `cat` с подсветкой синтаксиса
* `ripgrep` - очень быстрый `grep`
* `starship` - отображение текущей ветки и прочего в консоли без установки всякого ZSH

# gnome-tweaks

```bash
sudo apt install gnome-tweaks
```

* Tweaks -> Fonts, Scaling Factor = 1.5 (так как у меня 4к экран, и нвидия, это лучший способ сделать такое, fractional scaling в обыпчных настройках не будет работать)
* Настроить переключение клавиатуры на CapsLock

# Проги

```bash
sudo apt install flameshot blueman
```

* flameshot - для снятия скриншотов
* blueman - для работы блютуз наушников

# Либы для программирования

```bash
sudo apt install libssl-dev libxcb-randr0-dev libxcb-xtest0-dev libxcb-xinerama0-dev libxcb-shape0-dev libxcb-xkb-dev libxcb-xfixes0-dev libgl1-mesa-dev libxi-dev
```

# Sublime Text

```bash
wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
sudo apt update
sudo apt install sublime-text
```

* Установить `Preferences` из папки `sublime-text`
* Установить `Key Bindings` из папки `sublime-text`
* Установить `Package Control`
* Установить пакеты `Rust Enhanced`, `TOML`, `PlainTasks`

# git

```bash
git config --global credential.helper store
```

# JetBrains Mono font

```bash
mkdir JetBrains
cd JetBrains
wget https://github.com/JetBrains/JetBrainsMono/releases/download/v2.002/JetBrainsMono-2.002.zip
unzip JetBrainsMono-2.002.zip
mkdir ~/.local/share/fonts
mv ttf/JetBrainsMono-*.ttf ~/.local/share/fonts/
fc-cache -f -v
cd ..
rm -rf JetBrains
```

# Terminal

* Установить шрифт `JetBrainsMono`
* Настроить копипаст на `Ctrl+C`, `Ctrl+V`
* `stty intr ^J` - теперь `Ctrl+C` не будет выключать приложение, а это будет работать через `Ctrl+J`

`~/.bashrc` настроить:
* `HISTSIZE=-1`
* `HISTFILESIZE=-1`
* `eval "$(starship init bash)"`

## Starship

* `mkdir -p ~/.config && touch ~/.config/starship.toml`
