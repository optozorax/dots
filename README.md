# Основа

Использовать [Pop!\_OS](https://pop.system76.com/), потому что там из коробки поддерживаются дрова NVIDIA, и всё плавно работает.

# Установить через центр приложений:

* Spotify
* Sublime Merge
* Telegram

# Установить

* https://www.maartenbaert.be/simplescreenrecorder/ `sudo apt install simplescreenrecorder`

* https://github.com/mikf/gallery-dl - для массового скачивания картинок с сайтов с ними

* youtube-dl - для скачивания ютуб видео

* geeqie - для поиска одинаковых изображений, `sudo apt install geeqie`

* obsidian.md - для ведения локальной базы данных и мыслей

* qimgv - просмотрщик изображений
```
sudo add-apt-repository ppa:easymodo/qimgv
sudo apt-get update
sudo apt install qimgv
```

# Rust

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

```bash
cargo install 
	bat  # улучшенный cat
	ripgrep  # улучшенный grep
	fd-find # улучшенный find
	exa # улучшенный ls
	bottom # улучшенный top
	jql # улучшенный jq
	git-delta # # улучшенный diff
	# --- --- ---  --- --- ---  --- --- ---  
	starship # консолньая оболочка
	du-dust # просмотр что сколько памяти занимает
	simple-http-server # для локального хостинга веб-страниц
```

* `bat` - `cat` с подсветкой синтаксиса
* `ripgrep` - очень быстрый `grep`
* `starship` - отображение текущей ветки и прочего в консоли без установки всякого ZSH

# wasm

```bash
rustup target add wasm32-unknown-unknown
```

Установить [wasm-strip](https://github.com/WebAssembly/wabt/) (бинарники есть в секции releases).

# git 

В `subl ~/.gitconfig` вставить:
```gitconfig
[credential]
	helper = store

[user]
	name = ilya sheprut
	email = optozorax@gmail.com

[pager]
	diff = delta
	log = delta
	reflog = delta
	show = delta

[delta]
	plus-style = "syntax #012800"
	minus-style = "syntax #340001"
	syntax-theme = Monokai Extended
	navigate = true

[interactive]
	diffFilter = delta --color-only
```

# gnome-tweaks

```bash
sudo apt install gnome-tweaks
```

* Tweaks -> Fonts, Scaling Factor = 1.45 (так как у меня 4к экран, и нвидия, это лучший способ сделать такое, fractional scaling в обычных настройках не будет работать)
* Настроить переключение клавиатуры на CapsLock

# Проги

```bash
sudo apt install flameshot blueman xzoom
```

* flameshot - для снятия скриншотов
* blueman - для работы блютуз наушников
* xzoom - увеличительное стекло

# Либы для программирования

```bash
sudo apt install libssl-dev libxcb-randr0-dev libxcb-xtest0-dev libxcb-xinerama0-dev libxcb-shape0-dev libxcb-xkb-dev libxcb-xfixes0-dev libgl1-mesa-dev libxi-dev pkg-config libx11-dev libxi-dev libgl1-mesa-dev libasound2-dev
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
	"font_size": 10.5,
	"gpu_window_buffer": true,
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
		110
	],
	"show_definitions": false,
	"show_encoding": true,
	"show_panel_on_build": false,
	"sublime_merge_path": "Q:/Program/Portable/SublimeMerge/sublime_merge.exe",
	"theme": "Default.sublime-theme",
	"word_separators": "./\\()\"'-:,.;<>~!@#$%^&*|+=[]{}`~?«»",
	"word_wrap": true,
	"wrap_width": 110
}
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

`~/.bashrc` настроить:
* История команд. Соханение после каждой команды нужно потому что иногда с несколькими окнами терминала история убивается. [Источник.](https://stackoverflow.com/a/19533853)
  	```
  	# Eternal bash history.
	# ---------------------
	# Undocumented feature which sets the size to "unlimited".
	# http://stackoverflow.com/questions/9457233/unlimited-bash-history
	export HISTFILESIZE=
	export HISTSIZE=
	export HISTTIMEFORMAT="[%F %T] "
	# Change the file location because certain bash sessions truncate .bash_history file upon close.
	# http://superuser.com/questions/575479/bash-history-truncated-to-500-lines-on-each-login
	export HISTFILE=~/.bash_eternal_history
	# Force prompt to write history after every command.
	# http://superuser.com/questions/20900/bash-history-loss
	PROMPT_COMMAND="history -a; $PROMPT_COMMAND"
	```
* `eval "$(starship init bash)"` - чтобы работала консолька `starship`
* `stty intr ^J` - теперь `Ctrl+C` не будет выключать приложение, а это будет работать через `Ctrl+J`
* `stty werase '^H'` - Ctrl+Backspace будет стирать слова.
* Возможность делать консольку цветной (для определения множества окон консоли при выборе различных приложений):
```bash
alias color_normal='echo -e "\033]11;#333333\007"'
alias color_blue='echo -e "\033]11;#2d2f39\007"'
alias color_red='echo -e "\033]11;#363030\007"'
alias color_miku='echo -e "\033]11;#2f3737\007"'
```
* alias ubit_nahui="jobs -p | xargs kill -KILL" - для завершения программ, которые были остановлены через Ctrl+Z

## Starship

`mkdir -p ~/.config && touch ~/.config/starship.toml`

Вставить в этот файл:
```toml
[directory]
truncate_to_repo = false
truncation_length = -1

[git_status]
conflicted = "≠"
diverged = "∇"
untracked = "U"
stashed = "S"
modified = "M"
staged.value = "++"
staged.style = "green"
staged_count.enabled = true
staged_count.style = "green"
renamed = "R"
deleted = "D"
show_sync_count = true

[memory_usage]
disabled = true
show_percentage = true
show_swap = false
threshold = -1
```

# Gnome

* Установить [NoAnnoyance](https://extensions.gnome.org/extension/1236/noannoyance/) - не показывается уведомление "Window is Ready", а нужное окно сразу открывается.
* `sudo apt install wmctrl xdotool` - для управления окнами
* Поместить в `$PATH` скрипт [jumpapp](https://github.com/mkropat/jumpapp):
  ```
  curl https://raw.githubusercontent.com/mkropat/jumpapp/master/jumpapp > ~/.cargo/bin/jumpapp
  ```
* Поставить следующие хоткеи: (получено из `dconf dump /`)
```
[org/gnome/settings-daemon/plugins/media-keys]
custom-keybindings=['/org/gnome/settings-daemon/plugins/media-keys/custom-keybindings/custom0/','/org/gnome/settings-daemon/plugins/media-keys/custom-keybindings/custom1/','/org/gnome/settings-daemon/plugins/media-keys/custom-keybindings/custom2/','/org/gnome/settings-daemon/plugins/media-keys/custom-keybindings/custom3/','/org/gnome/settings-daemon/plugins/media-keys/custom-keybindings/custom4/','/org/gnome/settings-daemon/plugins/media-keys/custom-keybindings/custom5/','/org/gnome/settings-daemon/plugins/media-keys/custom-keybindings/custom6/','/org/gnome/settings-daemon/plugins/media-keys/custom-keybindings/custom7/','/org/gnome/settings-daemon/plugins/media-keys/custom-keybindings/custom8/']

[org/gnome/settings-daemon/plugins/media-keys/custom-keybindings/custom0]
binding='<Super>1'
command='jumpapp Telegram'
name='telegram'

[org/gnome/settings-daemon/plugins/media-keys/custom-keybindings/custom1]
binding='<Super>2'
command='jumpapp chrome'
name='firefox'

[org/gnome/settings-daemon/plugins/media-keys/custom-keybindings/custom2]
binding='<Super>3'
command='jumpapp sublime_text'
name='sublime text'

[org/gnome/settings-daemon/plugins/media-keys/custom-keybindings/custom3]
binding='<Super>4'
command='jumpapp nautilus'
name='files'

[org/gnome/settings-daemon/plugins/media-keys/custom-keybindings/custom4]
binding='<Primary><Shift>Print'
command='flameshot gui'
name='flameshot'

[org/gnome/settings-daemon/plugins/media-keys/custom-keybindings/custom5]
binding='<Super>6'
command='jumpapp gnome-terminal'
name='terminal'

[org/gnome/settings-daemon/plugins/media-keys/custom-keybindings/custom6]
binding='<Super>8'
command='jumpapp element'
name='spotify'

[org/gnome/settings-daemon/plugins/media-keys/custom-keybindings/custom7]
binding='<Super>9'
command='jumpapp sublime_merge'
name='merge'

[org/gnome/settings-daemon/plugins/media-keys/custom-keybindings/custom8]
binding='<Super>5'
command='jumpapp Discord'
name='discord'
```
* Добавить можно такой командой: `cat programs | dconf load /`
* Можно использовать `wmctrl -lx` для определения класса окна.
* Чтобы добавить какую-то программу в path, чтобы она запускалась jumpapp'ом, нужно для начала найти PID этой программы, а затем использовать: `ls -al /proc/<PID>/exe`, и можно узнать где она находится.

# Firefox

Зайти в `about:config`:
* Чтобы при копировании урла, не было процентов: `browser.urlbar.decodeURLsOnCopy` = `false`.


Настроить Stylish:
* Чтобы на всех сайтах символ таба был размером 4 пробела, а не идиотским 8:
```
* {
    -moz-tab-size : 4;
      -o-tab-size : 4;
         tab-size : 4;
}
```

# TODO

* [ ] Разобраться во всех хоткеях убунты, настроить их на себя, и засунуть в клаву
* [ ] Запретить Alt+Tab
* [ ] Сделать чтобы было настроено не меньше чем я настроил в своё время i3
