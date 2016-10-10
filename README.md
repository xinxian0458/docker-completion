# docker-completion
command line completion for docker, docker-machine, docker-compose.
scripts under bin folder is support for docker-1.12.1, docker-machine-0.8.1, docker-compose-1.8.0

# How to use in Bash
1. Make sure bash completion is installed. 
If you use a current Linux in a non-minimal installation, bash completion should be available. Otherwise, install it with `sudo yum install bash-completion`. On a Mac, install with `brew install bash-completion`

2. Place the completion scripts under `bin` in `/etc/bash_completion.d/` (`$(brew --prefix)/etc/bash_completion.d/` on a Mac)

For docker, execute with:
```bash
curl -L https://raw.githubusercontent.com/docker/docker/master/contrib/completion/bash/docker > /etc/bash_completion.d/docker
```

For docker-machine, execute with:
```bash
files=(docker-machine docker-machine-wrapper docker-machine-prompt)
for f in "${files[@]}"; do
  curl -L https://raw.githubusercontent.com/docker/machine/v$(docker-machine --version | tr -ds ',' ' ' | awk 'NR==1{print $(3)}')/contrib/completion/bash/$f.bash > /etc/bash_completion.d/$f
done
```

For docker-compose, execute with:
```bash
curl -L https://raw.githubusercontent.com/docker/compose/$(docker-compose version --short)/contrib/completion/bash/docker-compose > /etc/bash_completion.d/docker-compose
```
Completion will be available upon next login.
