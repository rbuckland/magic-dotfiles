# Ramon's old .dotfiles

1. Checkout this Repo to `~/.dotfiles`
2. Add to your .bashrc

  ```
  export DOTFILES_DIR=~/.dotfiles
  for f in ${DOTFILES_DIR}/*.function*; do . $f; done
  ```

3. Source the .bashrc `. ~/.bashrc`

4. `x-help` - will present the help of all your custom defined functions

  ```
  x-help from scripts in /Users/rbuckland/.dotfiles

  git-helpers.function
  	g-aliases                      : show the configured aliases in `~/.git/config
	p-git-clone                    : git clone to a repo - expects CWD to be <git-server>/

  little-helpers.functions
	web-server-here                : [<port>] expose documents in current directoy
	yaml2json                      : parse a yaml file to JSON (helpful for jq usage)
	glob-renamer                   : <directory> <fname-match> <sed-srch-repl>: eg '../adir IMG "s/_hires//g"

  osx.functions
	osx-show-hide-files            : toggle the Finder preferences for "showing" or "hiding" .dot files

  vm.functions
	vwf-collect-ip                 : <machine-name> - Vmware - Collect the Guest IP and put it into our /etc/hosts
	v-show-ip                      : <machine-name> show the IP of a given VirtualBox machine
	v-reset-network                : <machine-name> - VirtualBox - reset the network link :-) 

  x-help.functions
	x-help                         : this "help" output
  ```

## Writing your own functions

1. Create a `*.function[s]` in your `~/.dotfiles`  directory
   Group like functions together. This way help is "helpful".

2. Ensure you add a `# help: .. help text` at the top of your function.

  e.g. 

  ```
  # help: [<port>] expose documents in current directoy
  function web-server-here {
    local port=${1:-80}
    sudo ruby -run -ehttpd . -p${port}
  }
  ```
