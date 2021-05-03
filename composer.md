# Title: Composer
Composer is a dependency manager for PHP. Composer is used in all modern PHP frameworks (Symfony, Laravel, ...) and is one of the most recommended tools that solves fundamental issues in the majority of web projects.
If it a key tool to become a good and productive PHP developer.

A great developer always reused proven packages and solutions instead of reinventing the wheel.

We are all standing on the shoulders of the people that went before us.  

## Dependencies?
You often hear developers talk about dependencies, which might sound like a complex subject - but is actually very easy.

Every time you download a script from the internet, or a libary, you now have a dependency.

You probably already used dependencies like Bootstrap and Jquery when you are working on the frontend!

Now why do you want to use a tool for this instead of just downloading the packages yourself? Well, lets look at a real life example:

Let’s say you want to install the OpenTok V2 PHP Library, you go ahead and download the OpenTok PHP library. However OpenTok requires guzzle and json-schema to work. Wow! Are you going to manually download guzzle and json-schema? Because guzzle also has dependencies, it needs symfony’s event-dispatcher in order to work. And the list goes on...

Composer handles dependency resolution automatically. When you install Tokbox, it will automatically install all the required dependencies.

## Ow, so it is like apt-get?
Exactly! While apt-get manages your packages for ubuntu composer does the same for the PHP ecosystem. Every language has its own package mananger, for example node.js has NPM and Ruby and Rails has RubyGems.

## Autoloading
Another benefit of using composer is autoloading. After installing any library, you have to read the documentation to see which file you should require and most libraries require calling an autoloading function. Modern PHP projects require several external packages, imagine having over 10 requires and 10 autoloading functions.. terrible!

Composer handles autoloading automatically, you just have to write the following line of code which will allow you to load all your referenced packages:

`require_once 'vendor/autoload.php'`

Make a habbit of always including this file in your PHP projects.

## Keeping your packages updated

## Installation
So does all this sound good to you?
Lets install this amazing tool.

### Windows installer:
Visit https://getcomposer.org/download/ and download the Composer-Setup.exe

### Linux & Mac:
curl -sS [https://getcomposer.org/installer](https://getcomposer.org/installer) | php

If you need more detailed instructions: https://www.ionos.com/community/hosting/php/install-and-use-php-composer-on-ubuntu-1604/

___Very important: do NOT commit the vendor directory composer will create for you. Create a [.gitignore file](https://git-scm.com/docs/gitignore) for the entire vendor file.___

You should however always commit the composer.lock and composer.json.
This way your other teammates will install all the depencies with the same versions as you.

### Installing packages
If you want to install a package you can run on the command line:

`composer require twig/twig`

This will modify your composer.json and download the package "twig/twig".

If you are working in a team and somebody else already created and installed some packages you can run `composer update` to install all your packages.

If your coworker did the right thing and also added a composer.lock file, you will have the same versions as him!

**Tip 1:** If you run `composer install` it ignores the composer.lock file, and you might get a different version than your fellow learner. Do not mix up install and update!

**Tip 2:** Many tutorials will instruct you to manually modify the composer.json file instead of using `composer require`. This is bad practice, always use the command line.
The reason for this is that the tutorial might be outdated and force you to install an outdated version of the package.

### keep your packages updated
All packages get new features added to them all of them, they get security fixes, ... all of this requires a lot of effort to keep up to date manually.
Problem is that with a security vulnerability you should never wait too long before updating or you risk your customer his data being stolen.

Luckely composer provides a single command to fetch the new versions of all your dependencies:
 
You can run `composer upgrade` to upgrade your dependencies to the latest version according to composer.json, and updates the composer.lock file.
Then commit the composer.lock file.