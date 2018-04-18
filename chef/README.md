# kitchen chef

kitchen chef for testing ansible using [test kitchen][kitchen] and [Inspec][inspec].

This demonstrates using test-kitchen, chef, and inspec to build and verify vim is installed.
  * Everything is done via ssh from the Chef/Inspec server.
  * In this demonstration both servers are centos running under virtual box on your workstation

## Workstation Software Installation

1. Have ruby installed, you'll need that.
2. Run the following commands:

```
gem install bundler
```

```
bundle
```

```
bundle exec kitchen list
```

This will return a list if everything is correctly installed.

There are 2 ways to run chef either locally or remotely. In the local option you just need one server and chef and the software you are configuring are all installed on the one server.
In the remote option you need at least 2 servers. One server will get chef installed on it and it will then use ssh to configure the second server remotely.

```
bundle exec kitchen create centos
bundle exec kitchen converge centos
bundle exec kitchen verify centos
```

On all in one command:

```
bundle exec kitchen test centos
```

[kitchen]: http://kitchen.ci
[inspec]: http://github.com/chef/inspec
