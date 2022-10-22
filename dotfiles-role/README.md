# Dotfiles role

A simple role to install my [https://github.com/JonaVDM/dotfiles](Dotfiles) on a system.

## Requirements

Git needs to be installed on the system.

## Role Variables

```yml
dotfiles_repo: https://github.com/JonaVDM/dotfiles.git
```

The git repository where the dotfiles are stored. The machine needs to have access to these, either by settings the
repo to public or authenticating with keys.

```yml
dotfiles_folder: ~/.dotfiles
```

The folder where git is going to clone the repo to.

```yml
dotfiles_files:
  - src: .zshrc
    dest: ~/.zshrc
  - src: .p10k.zsh
    dest: ~/.p10k.zsh
  - src: .gitconfig
    dest: ~/.gitconfig
  - src: .tmux.conf
    dest: ~/.tmux.conf
  - src: kitty
    dest: ~/.config/kitty
```

The files in the repo and where they have to be linked to.

## Dependencies

None

## Example Playbook

```yml
- hosts: localhost
  roles:
    - { role: jonavdm.dotfiles }
```

## License

MIT
