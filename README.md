# Основа

Использовать Pop!\_OS, потому что там из коробки поддерживаются дрова NVIDIA, и всё плавно работает.

# Установить через центр приложений:

* Spotify
* Sublime Text
* Sublime Merge
* Telegram

# Установить Rust:

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

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
