# docker-completion
command line completion for docker, docker-machine, docker-compose

# How to use in Bash
1. Make sure bash completion is installed. 
If you use a current Linux in a non-minimal installation, bash completion should be available. Otherwise, install it with `sudo yum install bash-completion`. On a Mac, install with `brew install bash-completion`

2. Place the completion scripts under `bin` in `/etc/bash_completion.d/` (`$(brew --prefix)/etc/bash_completion.d/` on a Mac)
Completion will be available upon next login.
