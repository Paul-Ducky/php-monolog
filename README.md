# Title: Using composer

- Repository: `php-composer-monolog`
- Type of Challenge: `Learning Challenge`
- Duration: `1 day`
- Deployment strategy : `NA`
- Team challenge : `solo`

## Learning objectives
- To be able to manage packages with composer
- Understand what composer does for you
- Work with monolog
- Get used to work with different handlers

## The Mission
We will use our first external PHP dependency today!
We are going to use a popular open source tool to log messages: [monolog](https://github.com/Seldaek/monolog).

To manage this external package we will use composer, be sure to first read [the documentation about composer](
composer.md) and install both composer and then Monolog.

You can find the instructions to install Monolog on it's webpage.

## Must-have features
Use the buttons.html page to submit log messages and write the message in a log file.

Write each color of buttons to a different file:
- info: info.log and send the messages to browser console using `BrowserConsoleHandler`
- warning: warning.log 
- danger: warning.log and email these messages using `NativeMailerHandler`
- dark: emergency.log and email these messages using `NativeMailerHandler`

**You do not need to use an if to get the messages written in different files**

## Nice to have features
Try to experiment with different Monolog features like different Handlers!

## Tips
Read the documentation to assign different handlers and handle priorities. 

The function `pushHandler` is the key for this mission!

