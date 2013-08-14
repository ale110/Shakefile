`Shakefile`
===========

Installation
------------

### Local (per-user) ###
```bash
echo 'alias shake=./Shakefile.sh' >> ~/.bash_profile
```

### Global ###
```bash
wget 'https://raw.github.com/ale110/shakefile/master/bin/shake' -O/usr/bin/shake; chmod a+x /usr/bin/shake
```
You might need `sudo` for this one.

Usage
-----

### Writing a `Shakefile` ###

Take this one as a template:
```bash
#!/bin/sh

case "$1" in
  "install")
    if [ !-f bin/app ]; then
      shake build
    fi
    cp bin/app /usr/bin/
    chmod a+x
  
  "build")
    # whatever commands to build
    ;;
  
  "clean")
    rm -rf bin/*
    ;;
esac
```

### Running it ###
```bash
shake build && sudo shake install
```
