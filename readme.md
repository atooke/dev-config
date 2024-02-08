# Overview:	

Setup of dev tools for quick(er) migration to new PC/build.  This repo contains:

1) Setup instructions - see below
2) .dotfiles/Config files for each apply to easy replicate on other systems.
   

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

* cheatsheet:
  *  CMD+D = split vertical
  *  CMD+SHIFT + <- or -> = switch betwen panes



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
* brew install npm (needed to setup pyright LSP for python autocomplete in helix)
* 
* LLVM setup:
  * run hx --health optional add language you want to check.  Chances are you are missing
the llvm setup.  to fix:
  * For rust:
    *  install rus analyzer  &  llvm
        * brew install rust-analyzer
        * brew install llvm
  * for python:
    *  npm install pyright -g
    *  pip install ruff-lsp
    *  pip install 



    * setup env variable in .zshrc so that they can be found
    `export PATH=/usr/local/opt/llvm/bin:$PATH`
    `export PATH=/usr/local/bin/rust-analyzer:$PATH`

    * see .config/helix for config.toml & language.toml
* font - uses terminal default, change there
* Theme - monokai_pro_octagon
* Key shortcuts:

   * find/replace all occurances at once (CMD+D in sublime code):
     * Press % to select all text or x to select block of text
     * Press s to enter search term & press enter
     * Enter new text, all will be changed at once
     * , to remove multi cursor
     * press n or b to go back/from
   
   * multi-line cursor = SHIFT+C
   * u = undo
   * y copy
   * space y or Y = copy to system clipboard
   * space p or P - paste
   * space f = open file
   * space b = open buffer (see currently open files)
   * shift + ~ = uppercase /lower case toggle, need to select word first

   *gg - from of file
   *ge - end of file
   * gl - goto end of line
   * gh - goto start of line

   *CTRL+Z - put helix in background/go back to CLI
   * bg - get back into helix


## Lazygit:
  * brew install lazygit
  * `c` to start commit / bring up commit window
  * `q`= quit
  * `a` = add all
  * ' ' / space when on file in files section - stage 1 file
  * `P` = push
  * `p` = pull

## Worktree
  * git worktree flow:
  * https://github.com/jesseduffield/lazygit?tab=readme-ov-file#tutorials
