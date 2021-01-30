# Ambiente-macOS
Minhas configuração do ambiente macOS

1 - Instalar o gerenciador de pacotes HOMEBREW
  ~ comando: /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
__________________________________________________________________________________________________________________________
2 - Instalar o editor de texto VSCODE
  ~ comando: brew cask install visual-studio-code
  
  Plugins:
  
  ~ ColorHighlight – Esse plugin mostra a cor exata de todos RGB’s ou HEX em seu código, muito útil para quem trabalha com CSS ou SASS;
  
  DotEnv – Plugin que utilizo para ter suporte à sintaxe .env, muito útil para quem trabalha com NodeJS, ReactJS ou qualquer outro tipo de projeto web;
  
  ~ Dracula Official – Tema que utilizo no meu VSCode e em todos outros editores/terminais, pra mim foi o tema que mais me agradou durante mais tempo e olha que já usei muitos;
  
  ~ EditorConfig – Plugin utilizado para padronizar quebra de linha, indentação, espaços e tabs entre desenvolvedores de um mesmo projeto;
  
  ~ ESLint – Plugin utilizado para padronizar código entre desenvolvedores como utilização de pontos e vírgulas, tamanho máximo de caracteres em linhas e todo outro tipo de padronização. Recomendo muito a utilização desse plugin junto aos guias de estilo do AirBnB;
  
  ~ Markdown All in One – Plugin que utilizo para escrever e ler Markdown dentro do VSCode, muito útil para documentações o README’s do Github;
  
  ~ Material Icon Theme – Utilizo para exibir os ícones de acordo com a linguagem utilizada na minha sidebar. Fica muito legal mesmo pois esse plugin identifica a grande parte de libs e ferramentas.
  
  ~ Configurações do settings.json:
  
      {
      "workbench.colorTheme": "Dracula",

      "workbench.iconTheme": "material-icon-theme",

      "terminal.integrated.shell.osx": "/bin/zsh",

      "workbench.startupEditor": "newUntitledFile",

      // Configura tamanho e família da fonte

      "editor.tabSize": 2,

      "editor.fontSize": 18,

      "editor.lineHeight":24,

      "editor.fontFamily":"Fira Code",

      "editor.fontLigatures":false,

      "explorer.compactFolders": true,

      "workbench.editor.labelFormat": "short",

      "extensions.ignoreRecommendations": true,

      // Aplica linhas verticais para lembrar de quebrar linha em códigos muito grandes

      "editor.rulers": [

      80,

      120

      ],

      "breadcrumbs.enabled": true,

      // Aplica um sinal visual na esquerda da linha selecionada

      "editor.renderLineHighlight":"gutter",

      // Aumenta a fonte do terminal

      "terminal.integrated.fontSize":14,

      // Define o tema dos ícones na sidebar

      }  
      
    --Em breve link de repositorio das configurações do VSCODE--
___________________________________________________________________________________________________________________________


3 - Instalar o NODE
  ~ comando: brew install node
  

4 - Instalar o GIT
  ~ comando: brew install git  
  
  Configurações no arquivo .gitconfig:
  
        [color]
        ui = true

      [color"status"]
        added = green
        changed = yellow
        untranked = red

      [color"branch"]
        current = white
        remote = red

      [color"diff"]
        meta = yellow
        old = red
        new = green

      [alias]
        ci = commit
        co = checkout
        cm = checkout master
        cb = checkout -b
        st = status -sb
        sf = show --name-only
        lg = log --pretty=format:'%Cred%h%Creset %C(bold)%cr%Creset %Cgreen<%an>%Creset %s' --max-count=30
        incoming = !(git fetch --quiet && git log --pretty=format:'%C(yellow)%h %C(white)- %C(red)%an %C(white)- %C(cyan)%d%Creset %s %C(white)- %ar%Creset' ..@{u})
        outgoing = !(git fetch --quiet && git log --pretty=format:'%C(yellow)%h %C(white)- %C(red)%an %C(white)- %C(cyan)%d%Creset %s %C(white)- %ar%Creset' @{u}..)
        unstage = reset HEAD --
        undo = checkout --
        rollback = reset --soft HEAD~1  
   --Em breve criarei repositório das configurações do meu git--
  ______________________________________________________________________________________________________________________

4 - Instalar o terminal Oh-My-Zsh
  ~ comando: sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
  
  
  4.1 - Instalar o theme spaceship para o terminal zsh
  ~ comando: git clone https://github.com/denysdovhan/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt"  
  ~ comando: npm install -g spaceship-prompt  
  ~ comando: ln -s " $ ZSH_CUSTOM /themes/spaceship-prompt/spaceship.zsh-theme "  " $ ZSH_CUSTOM /themes/spaceship.zsh-theme " 
  ~ comando: sudo chown -R $USER /usr/local/lib/node_modules (Caso haja um erro de permissão nas na etapa de NPM)
  
  4.2 Liberar o comando .code no VSCODE em Shell Command: Install 'code' command in PATH
  
  4.3 - Utilizar o comando code para editar o arquivo .zshrc com: code. ~/.zshrc
  
  4.5 - Colar as configurações no terminal para o arquivo .zshrc:
  
    
      export ZSH="/home/isaac/.oh-my-zsh" 
      export ZSH="/Users/isaac/.oh-my-zsh"
      export PATH="$PATH:/usr/local/bin"
      export PATH="$HOME/.fastlane/bin:$PATH"
      # Set name of the theme to load --- if set to "random", it will

      # load a random theme each time oh-my-zsh is loaded, in which case,

      # to know which specific one was loaded, run: echo $RANDOM_THEME

      # See https://github.com/ohmyzsh/ohmyzsh/wiki/Themes

      # Set list of themes to pick from when loading at random

      # Setting this variable when ZSH_THEME=random will cause zsh to load

      # a theme from this variable instead of looking in $ZSH/themes/

      # If set to an empty array, this variable will have no effect.

      # ZSH_THEME_RANDOM_CANDIDATES=( "robbyrussell" "agnoster" )

      ZSH_THEME="spaceship"

      # Uncomment the following line to use case-sensitive completion.

      # CASE_SENSITIVE="true"

      # Uncomment the following line to use hyphen-insensitive completion.

      # Case-sensitive completion must be off. _ and - will be interchangeable.

      # HYPHEN_INSENSITIVE="true"

      # Uncomment the following line to disable bi-weekly auto-update checks.

      # DISABLE_AUTO_UPDATE="true"

      # Uncomment the following line to automatically update without prompting.

      # DISABLE_UPDATE_PROMPT="true"

      # Uncomment the following line to change how often to auto-update (in days).

      # export UPDATE_ZSH_DAYS=13

      # Uncomment the following line if pasting URLs and other text is messed up.

      # DISABLE_MAGIC_FUNCTIONS="true"

      # Uncomment the following line to disable colors in ls.

      # DISABLE_LS_COLORS="true"

      # Uncomment the following line to disable auto-setting terminal title.

      # DISABLE_AUTO_TITLE="true"

      # Uncomment the following line to enable command auto-correction.

      # ENABLE_CORRECTION="true"

      # Uncomment the following line to display red dots whilst waiting for completion.

      # COMPLETION_WAITING_DOTS="true"

      # Uncomment the following line if you want to disable marking untracked files

      # under VCS as dirty. This makes repository status check for large repositories

      # much, much faster.

      # DISABLE_UNTRACKED_FILES_DIRTY="true"

      # Uncomment the following line if you want to change the command execution time

      # stamp shown in the history command output.

      # You can set one of the optional three formats:

      # "mm/dd/yyyy"|"dd.mm.yyyy"|"yyyy-mm-dd"

      # or set a custom format using the strftime function format specifications,

      # see 'man strftime' for details.

      # HIST_STAMPS="mm/dd/yyyy"

      # Would you like to use another custom folder than $ZSH/custom?

      # ZSH_CUSTOM=/path/to/new-custom-folder

      # Which plugins would you like to load?

      # Standard plugins can be found in $ZSH/plugins/

      # Custom plugins may be added to $ZSH_CUSTOM/plugins/

      # Example format: plugins=(rails git textmate ruby lighthouse)

      # Add wisely, as too many plugins slow down shell startup.

      plugins=(git)

      source $ZSH/oh-my-zsh.sh

      #zinit light zdharma/fast-syntax-highlighting

      #zinit light zsh-users/zsh-autosuggestions

      #zinit light zsh-users/zsh-completions

      # User configuration

      # export MANPATH="/usr/local/man:$MANPATH"

      # You may need to manually set your language environment

      # export LANG=en_US.UTF-8

      # Preferred editor for local and remote sessions

      # if [[ -n $SSH_CONNECTION ]]; then

      # export EDITOR='vim'

      # else

      # export EDITOR='mvim'

      # fi

      # Compilation flags

      # export ARCHFLAGS="-arch x86_64"

      # Set personal aliases, overriding those provided by oh-my-zsh libs,

      # plugins, and themes. Aliases can be placed here, though oh-my-zsh

      # users are encouraged to define aliases within the ZSH_CUSTOM folder.

      # For a full list of active aliases, run `alias`.

      #

      # Example aliases

      # alias zshconfig="mate ~/.zshrc"

      # alias ohmyzsh="mate ~/.oh-my-zsh"

      SPACESHIP_PROMPT_ORDER=(

      user # Username section

      dir # Current directory section

      host # Hostname section

      git # Git section (git_branch + git_status)

      hg # Mercurial section (hg_branch + hg_status)

      exec_time # Execution time

      line_sep # Line break

      vi_mode # Vi-mode indicator

      jobs # Background jobs indicator

      exit_code # Exit code section

      char # Prompt character

      )

      SPACESHIP_USER_SHOW=always

      SPACESHIP_PROMPT_ADD_NEWLINE=false

      SPACESHIP_CHAR_SYMBOL="❯"

      SPACESHIP_CHAR_SUFFIX=" "


      pasteinit() {
        OLD_SELF_INSERT=${${(s.:.)widgets[self-insert]}[2,3]}
        zle -N self-insert url-quote-magic # I wonder if you'd need `.url-quote-magic`?
      }

      pastefinish() {
        zle -N self-insert $OLD_SELF_INSERT
      }
      zstyle :bracketed-paste-magic paste-init pasteinit
      zstyle :bracketed-paste-magic paste-finish pastefinish
      ### Added by Zinit's installer
      if [[ ! -f $HOME/.zinit/bin/zinit.zsh ]]; then
          print -P "%F{33}▓▒░ %F{220}Installing %F{33}DHARMA%F{220} Initiative Plugin Manager (%F{33}zdharma/zinit%F{220})…%f"
          command mkdir -p "$HOME/.zinit" && command chmod g-rwX "$HOME/.zinit"
          command git clone https://github.com/zdharma/zinit "$HOME/.zinit/bin" && \
              print -P "%F{33}▓▒░ %F{34}Installation successful.%f%b" || \
              print -P "%F{160}▓▒░ The clone has failed.%f%b"
      fi

      source "$HOME/.zinit/bin/zinit.zsh"
      autoload -Uz _zinit
      (( ${+_comps} )) && _comps[zinit]=_zinit

      # Load a few important annexes, without Turbo
      # (this is currently required for annexes)
      zinit light-mode for \
          zinit-zsh/z-a-rust \
          zinit-zsh/z-a-as-monitor \
          zinit-zsh/z-a-patch-dl \
          zinit-zsh/z-a-bin-gem-node

      zinit light zdharma/fast-syntax-highlighting
      zinit light zsh-users/zsh-autosuggestions
      zinit light zsh-users/zsh-completions
      ### End of Zinit's installer chunk
    
    --Em breve o criarei um repositório para as configurações do terminal--
 __________________________________________________________________________________________________________
   
5 - Instalar a consulta de documentações DevDocs
  ~ comando: brew install --cask devdocs
  
6 - Instalar o Notion
  ~ comando: brew install --cask notion      
  
7 - Extensões do chrome:
   ~ JSON viewer
   ~ React developer tools
   ~ Octotree
    
8 - Ferramentas:
   ~ Whimsical #UX
   ~ Insominia #API
