# ✨ iitz4i4a-dotfiles

Мои персональные конфигурации для терминала и разработки.

## 📦 Состав

### [`nvim/`](./nvim/) — Neovim
Editor с [LazyVim](https://github.com/LazyVim/LazyVim) + [lazy.nvim](https://github.com/folke/lazy.nvim).

| Компонент | Описание |
|-----------|----------|
| **Colorscheme** | [solarized-osaka](https://github.com/raphamorim/solarized-osaka) |
| **Форматирование** | ESLint + Prettier |
| **Языки** | TypeScript, JSON, Rust, Tailwind |
| **Утилиты** | mini-hipatterns |

Кастомные плагины — [`nvim/lua/plugins/`](./nvim/lua/plugins/):

- `coding.lua` — настройки кодинга
- `colorscheme.lua` — тема
- `treesitter.lua` — подсветка синтаксиса
- `editor.lua` — редактор
- `lsp.lua` — LSP
- `ui.lua` — UI
- `vim-tmux-navigator.lua` — навигация Neovim ↔ Tmux

### [`.tmux.conf`](./.tmux.conf) — Tmux
Терминальный мультиплексор с [TPM](https://github.com/tmux-plugins/tpm).

| Плагин | Назначение |
|--------|------------|
| [tmux-sensible](https://github.com/tmux-plugins/tmux-sensible) | Базовые улучшения |
| [vim-tmux-navigator](https://github.com/christoomey/vim-tmux-navigator) | Единая навигация с Neovim |
| [tmux-themepack](https://github.com/jimeh/tmux-themepack) | Тема `powerline/default/purple` |
| [tmux-resurrect](https://github.com/tmux-plugins/tmux-resurrect) | Сохранение/восстановление сессий |
| [tmux-continuum](https://github.com/tmux-plugins/tmux-continuum) | Автосохранение сессий |
| [tmux-sessionist](https://github.com/tmux-plugins/tmux-sessionist) | Управление сессиями |

**Предустановки:**
- Префикс: `Ctrl+t`
- Разделение: `Ctrl+t |` / `Ctrl+t -`
- Мышь: включена
- Режим навигации: `vi`

### [`yazi/`](./yazi/) — Yazi
Файловый менеджер с отображением скрытых файлов (`show_hidden = true`).

## 🚀 Установка

### Neovim

```bash
# Удалить старую конфигурацию (если есть)
rm -rf ~/.config/nvim ~/.local/share/nvim

# Клонировать репозиторий
git clone --sparse https://github.com/iiTz4i4a/iitz4i4a-dotfiles.git ~/.config/nvim
cd ~/.config/nvim
git sparse-checkout set nvim
git checkout

# Собрать плагины
nvim --headless "+Lazy! sync" +qa
```

### Tmux

```bash
# Скопировать конфигурацию
cp ~/.config/nvim/.tmux.conf ~/.tmux.conf

# Загрузить плагины
tmux server-stop
tmux server-start  # TPM загрузит плагины при старте
```

### Yazi

```bash
mkdir -p ~/.config/yazi
cp -r ~/.config/nvim/yazi/* ~/.config/yazi/
```
