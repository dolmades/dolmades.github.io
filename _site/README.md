# dolmades.github.io

This is the source of the official "Dolmades" Project Page.
Follow these instructions to setup an environment to make changes and test them locally

## Setup Jekyll container
```
udocker pull ubuntu:18.04
udocker create --name="Jekyll" ubuntu:18.04
udocker run --user=root Jekyll sh -c 'apt-get update && apt-get -y install ruby ruby-dev build-essential && apt-get clean'
udocker run --user=$(whoami) --bindhome --hostauth --hostenv Jekyll bash -c 'gem install jekyll bundler'
```

## Serve locally to develop the web page
```
udocker run --user=$(whoami) --bindhome --hostauth --hostenv Jekyll bash -c 'cd '$PWD' && jekyll serve'
```
Now develop and test your changes on http://localhost:4000
When you're happy push your changes. Wheee... :)
