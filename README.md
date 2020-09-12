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

* Установить `Preferences`:
```json
{
	"always_show_minimap_viewport": true,
	"auto_complete": true,
	"auto_complete_commit_on_tab": true,
	"auto_complete_cycle": true,
	"auto_find_in_selection": true,
	"auto_match_enabled": false,
	"color_scheme": "Packages/Color Scheme - Default/Mariana.sublime-color-scheme",
	"drag_text": false,
	"draw_minimap_border": true,
	"fallback_encoding": "Cyrillic (Windows 1251)",
	"fold_buttons": false,
	"font_face": "JetBrains Mono",
	"font_size": 11,
	"highlight_line": true,
	"highlight_modified_tabs": true,
	"ignored_packages":
	[
		"Rust",
		"Vintage"
	],
	"margin": 0,
	"preview_on_click": false,
	"rulers":
	[
		120
	],
	"show_encoding": true,
	"show_panel_on_build": false,
	"sublime_merge_path": "Q:/Program/Portable/SublimeMerge/sublime_merge.exe",
	"theme": "Default.sublime-theme",
	"word_wrap": true,
	"wrap_width": 120
}

```
* Установить `Key Bindings`:
```json
[
	{ "keys": ["ctrl+tab"], "command": "next_view" },
	{ "keys": ["ctrl+shift+tab"], "command": "prev_view" },
]
```
* Установить `Package Control`
* Установить пакеты `Rust Enhanced`, `TOML`, `PlainTasks`
* Настроить `Rust Enhanced`:
```json
{
	"rust_syntax_checking_method": "clippy",
	"rust_message_theme": "solid"
}
```

# Sublime Merge

* Настроить `Diff`:
```json
{
	"auto_diff_style_min_chars": 80,
	"diff_style": "side-by-side",
	"word_wrap": true
}
```

* Настроить `Preferences`:
```json
{
	"font_face": "JetBrains Mono",
	"font_size": 8,
	"side_bar_layout": "tabs",
}
```

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
