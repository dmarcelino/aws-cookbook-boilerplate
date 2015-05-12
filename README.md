# aws-cookbook-boilerplate
Cookbook repository boilerplate for AWS OpsWorks

A working custom cookbook repository to be used with AWS OpsWorks, based on 
[Deploying MongoDB with OpsWorks](http://blogs.aws.amazon.com/application-management/post/Tx1RB65XDMNVLUA/Deploying-MongoDB-with-OpsWorks). This repo adds a custom recipe to install MongoDB from https://supermarket.chef.io/cookbooks/mongodb.

## Updating Custom Cookbooks
AWS caches the custom cookbook repository locally. If you modify the custom cookbooks in the repository, you must ensure that the updated cookbooks are installed on your instances' local caches. You can do that by going to **Stack -> Run Command -> Update Custom Cookbooks**. More about this on [AWS: Updating Custom Cookbooks](http://docs.aws.amazon.com/opsworks/latest/userguide/workingcookbook-installingcustom-enable-update.html).

## References
* [AWS: Cookbook Repositories](http://docs.aws.amazon.com/opsworks/latest/userguide/workingcookbook-installingcustom-repo.html)
* [AWS: Installing Custom Cookbooks](http://docs.aws.amazon.com/opsworks/latest/userguide/workingcookbook-installingcustom-enable.html)
* [Deploying MongoDB with OpsWorks](http://blogs.aws.amazon.com/application-management/post/Tx1RB65XDMNVLUA/Deploying-MongoDB-with-OpsWorks)
* [CHEF Supermarket](https://supermarket.chef.io)
* [berkshelf.com](http://berkshelf.com)
