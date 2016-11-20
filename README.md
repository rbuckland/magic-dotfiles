# Ramon's old .dotfiles

1. Checkout this Repo to `~/.dotfiles`
2. Add to your .bashrc

  ```
  export DOTFILES_DIR=~/.dotfiles
  for f in ${DOTFILES_DIR}/*.function*; do . $f; done
  ```

3. Source the .bashrc `. ~/.bashrc`

4. `x-help`
