# test-kitchen integrations

This is the code for the 4 major configuration management systems with test-kitchen and inspec
around them.

## Directories

- [`ansible`](ansible/) - ansible demo
- [`chef`](chef/) - chef demo
- [`puppet`](puppet/) - puppet demo
- [`saltstack`](saltstack/) - salt demo

## Quick how to install ruby with rvm

[rvm][rvm] is method of managing ruby versions.

Import the gpg key from https://rvm.io

```
gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB
```

Run the installer script

```
\curl -sSL https://get.rvm.io | bash -s stable
```

Install and use ruby

```
rvm use --install --create 2.5.0@GEMSETNAME
```

and rvm will manage installing all of the required packages for managing ruby versions via rvm.

## License and Authors

- Author:: JJ Asghar <jjasghar@gmail.com>

```text
Copyright 2018 JJ Asghar

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```


[rvm]: https://rvm.io
