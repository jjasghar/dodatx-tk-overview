# kitchen ansible

kitchen-ansible-example for testing ansible using [test kitchen][kitchen] and [Inspec][inspec].

This demonstrates using test-kitchen, ansible and inspec to build and verify a tomcat server.
  * Everything is done via ssh from the Ansible/Inspec server so nothing is installed on the tomcat server apart from Java and Tomcat.
  * In this demonstration both servers are centos under virtual box on your workstation, however the Tomcat server
could be anywhere like Amazon EC2, or a Docker Container.
  * You can take an image of the server after it is build and no comfiguration software is install on the Tomcat Server.
  * this is using ansible in ssh connection mode to do remote configuration.

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

There are 2 ways to run ansible either locally or remotely. In the local option you just need one server and ansible and the software you are configuring are all installed on the one server.
In the remote option you need at least 2 servers. One server will get ansible installed on it and it will then use ssh to configure the second server remotely.

When using rename spec/spec_helper_local.rb to spec/spec_helper.rb and a separate tomcat servers is not required.

```
bundle exec kitchen create centos
bundle exec kitchen converge centos
# Wait a min or two for Java to spin up
bundle exec kitchen verify centos
```

On all in one command:

```
bundle exec kitchen test centos
# You'll get a failure with InSpec about Java, wait about a minute
bundle exec kitchen verify centos
```

[kitchen]: http://kitchen.ci
[inspec]: http://github.com/chef/inspec
