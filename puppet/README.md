# kitchen puppet

kitchen-puppet-example for testing puppet using [test kitchen][kitchen] and [Inspec][inspec].

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

This will return a list of the instances you can test on using test-kitchen if everything is correctly installed. You can use test-kitchen to create an instance, converge it with puppet, and test that puppet configured the instance properly using Inspec:

```
bundle exec kitchen create default-ubuntu-1604
bundle exec kitchen converge default-ubuntu-1604
bundle exec kitchen verify default-ubuntu-1604
```

The `kitchen test` command does this all, then destroys the instance:

```
bundle exec kitchen test default-ubuntu-1604
```

[kitchen]: http://kitchen.ci
[inspec]: http://github.com/chef/inspec

# notes

This uses https://github.com/chef/inspec/tree/master/examples/kitchen-puppet mostly unmodified (once https://github.com/chef/inspec/pull/2972 gets merged)
