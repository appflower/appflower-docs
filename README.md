# AppFlower Documentation

For the current documentation visit the online book at http://appflower.com/doc. We are moving the existing documentation to be placed on github, for easier contribution. You should still checkout the online docs, for commenting. 

## ContributingThe most easy contribution you can make is reporting issues: a typo, a grammar mistake, a bug in code example, a missing explanation, and so on. The documentation is hosted on [github](https://github.com/appflower/appflower-docs).

**Ways of contributing**

 * [Submit a bug](https://github.com/appflower/appflower-docs/issues/new)
 * Submit a patch, through github
 * Translating appFlower documentation

## Fork > Clone > Pull-Request
To contribute to the AppFlower Documentation, you need to:

 * [fork](http://help.github.com/fork-a-repo/) the appflower-docs repository
 * make a git clone `git clone git://github.com/YOURUSERNAME/appflower-docs.git`
 * 

### A few notes on Committing Changes
Your changes should be based on the 1.2 branch instead of the master branch. To do this checkout the 1.2 branch before the next step:

 $ git checkout 1.2

Next, create a dedicated branch for your changes (for organization):

 $ git checkout -b improving_foo_and_bar

You can now make your changes directly to this branch and commit them. When you're done, push this branch to your GitHub fork and initiate a pull request. The pull request will be between your improving_foo_and_bar branch and the symfony-docs master branch.
 
If you have made your changes based on the 1.2 branch then you need to follow the change commit link and change the base branch to be @1.2:

GitHub covers the topic of [pull requests](http://help.github.com/pull-requests/) in detail.

  
## License
The AppFlower documentation is licensed under a Creative Commons Attribution-Share Alike 3.0 Unported [License](http://symfony.com/doc/current/contributing/documentation/license.html).


