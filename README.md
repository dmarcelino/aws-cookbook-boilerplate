# aws-cookbook-boilerplate
Cookbook repository boilerplate for Amazon AWS OpsWorks

A working custom cookbook repository to be used with Amazon AWS OpsWorks, based on 
[Deploying MongoDB with OpsWorks](http://blogs.aws.amazon.com/application-management/post/Tx1RB65XDMNVLUA/Deploying-MongoDB-with-OpsWorks). This repo adds a custom recipe to install MongoDB from https://supermarket.chef.io/cookbooks/mongodb.

## Recipes

### mongodb-aws
In order to access MongoDB on your running instance you'll need to open up port 27017 (assuming you are using the default) by [setting a security group](http://docs.aws.amazon.com/gettingstarted/latest/wah/getting-started-application-server.html) through [Amazon EC2 console](https://console.aws.amazon.com/ec2/).

#### Known issues
* **No such file or directory - systemctl**: as reported in [edelight/chef-mongodb#358](https://github.com/edelight/chef-mongodb/issues/358), the first time you run your mongodb instance you may experience this error. Stopping and starting `mongod` service should fix the issue and next time you start the instance everything should be fine.

### opsworks_nodejs

The original OpsWorks Node.js layer is flawed as it discards the output of the app. In this boilerplate we
override it to output to `deploy[:deploy_to]/current/log/console.log` following 
[stackoverflow #28183395](http://stackoverflow.com/questions/28183395/node-js-opsworks-layer-console-logs)
example.

## Updating Custom Cookbooks
AWS caches the custom cookbook repository locally. If you modify the custom cookbooks in the repository, you must ensure that the updated cookbooks are installed on your instances' local caches. You can do that by going to **Stack -> Run Command -> Update Custom Cookbooks**. More about this on [AWS: Updating Custom Cookbooks](http://docs.aws.amazon.com/opsworks/latest/userguide/workingcookbook-installingcustom-enable-update.html).

## References
* [AWS: Cookbook Repositories](http://docs.aws.amazon.com/opsworks/latest/userguide/workingcookbook-installingcustom-repo.html)
* [AWS: Installing Custom Cookbooks](http://docs.aws.amazon.com/opsworks/latest/userguide/workingcookbook-installingcustom-enable.html)
* [Deploying MongoDB with OpsWorks](http://blogs.aws.amazon.com/application-management/post/Tx1RB65XDMNVLUA/Deploying-MongoDB-with-OpsWorks)
* [Overwrite templates in wrapper-cookbooks](https://raymii.org/s/articles/Chef_-_overwrite_templates_in_wrapper_cookbooks.html)
* [CHEF Supermarket](https://supermarket.chef.io)
* [berkshelf.com](http://berkshelf.com)
