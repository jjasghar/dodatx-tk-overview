# kitchen saltstack

kitchen-saltstack-example for testing saltstack using [test kitchen][kitchen] and [Inspec][inspec].

This demonstration sets up an SSH server on a [Vagrant](https://www.vagrantup.com/) instance running on your local machine.

## Workstation Software Installation

1. Have ruby installed, you'll need that - see the main README for RVM instructions.
2. Have [vagrant](https://www.vagrantup.com/downloads.html) installed and in the PATH.
3. Have [virtualbox](https://www.virtualbox.org/wiki/Downloads) installed.
2. Run the following commands:

```
gem install bundler
bundle
bundle exec kitchen list
```

This will return a list of the instances you can test on using test-kitchen if everything is correctly installed. You can use test-kitchen to create an instance, converge it with saltstack, and test that saltstack configured the instance properly using InSpec:

```
bundle exec kitchen create default-centos-72
bundle exec kitchen converge default-centos-72
bundle exec kitchen verify default-centos-72
```

The `kitchen test` command does this all, then destroys the instance:

```
bundle exec kitchen test default-centos-72
```

[kitchen]: http://kitchen.ci
[inspec]: http://github.com/chef/inspec

# Notes on the saltstack demo

This uses https://github.com/saltstack-formulas/openssh-formula almost entirely unmodified.
