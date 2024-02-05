# Overview:	

Setup of dev tools for quick(er) migration to new PC/build.  

# TODO: 
Leverage Anisble to build all of this


## Terminal setup
* install iterm
  * iterm setup:
    * use ALT-arrow keys to move between words: profile->keys->key mapping->presets-> select natural text editing
    * font - menlo   
* install oh my zsh via:
`-sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"`

* Note: it will update .zshrc if you are running iterm, copy any old settings that are
now in .zshrc.pre-oh-my-zsh  

## install FTF
* git clone --depth 1 https://github.com/junegunn/fzf.git ~/.fzf
* Example usage - find all python files and bring into fzf
  `find ~/repos -name "*.py" | fzf`

## TMUX
* install:brew install tmux
* cheatsheet:
  * `tmux new -s "name of session"` or `tmux new-session -s "$(basename "$(pwd)")"`
  * exit session but keep running `CTRL+B, let keys go, then press D to dettach but keep session`
  * tmux ls
  * tmux attach -t <sessions name>

## Helix setup
* brew install helix
* LLVM setup:
  * run hx --health optional add language you want to check.  Chances are you are missing
the llvm setup.  to fix:
  * For rust:
    *  install rus analyzer  &  llvm
        * brew install rust-analyzer
        * brew install llvm

    * setup env variable in .zshrc so that they can be found
    `export PATH=/usr/local/opt/llvm/bin:$PATH`
    `export PATH=/usr/local/bin/rust-analyzer:$PATH`

    * see .config/helix for config.toml & language.toml
* font - uses terminal default, change there
* Theme - monokai_pro_octagon
## Lazygit:
  * brew install lazygit
  * `c` to start commit / bring up commit window
  * `q`= quit
  * `a` = add 

## Worktree
  * git worktree flow:
  * https://github.com/jesseduffield/lazygit?tab=readme-ov-file#tutorials
