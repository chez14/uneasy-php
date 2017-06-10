# Uneasy PHP (Still in development)
This project are ittended to challange myself to make a better
mechanism of security. This project are actually aplicable with
super minimalism requirement, such as PHP 7 (which is pretty
common now) and [Composer](https://getcomposer.com) (optional lah).

### Usefull Links:
- [Back Story](docs/backstory.en.md)
- [Requirements](#requirements)
- [Getting Started](#getting-started)
- [Strategy of this project](#strategy)
- [Proof of Concept](#concept-of-proof-and-proof-of-concept)
- [License](LICENSE)
- [Special Thanks](#special-thanks)

## Requirements
- PHP5.6 or PHP7 (Recomended PHP7)
- Composer (Optional, we'll just use the autoload and it's manager)
- A glass of coffe

## Getting Started
- Do this:
  ```shell
  $ composer install
  ```
  This will download and install required dependencies to your current
  working directory after create vendor directory. No need to worry,
  just easily delete your working directory if something gone bad.
- Then setting your apache vhost to your current working directory,
  or, use PHP Built-in Development Server
  ```shell
  $ php -S localhost:8081
  ```
- Access `http://localhost:8081/` to see the basic demo.

Most of the algorithms will be made into a meaningfull package, but currently it's still builted in onto this project.

# How is it work

## Strategy:
- Generate Payload
  
  Generation included:
  - Key for Cookie and it's value
  - Key to catch the Cookie value (to catch the server Cookie)

  Task should be returned (or generated) by the payload:
  - Generate Cookie
  - Generate a value for CSRF-like hidden form

- Build Payload Responser (for client)
- Minify the Payload Responser
- Do a trick to the minified Payload
- Pack it using [Packer](https://github.com/tholu/php-packer)
- Concat required liblary with the Packed payload

## Concept of Proof and Proof of Concept
The main idea is by making some ruckus with the javascript to 
test that it is accessed using browser and it's not a bot.
By doing such a thing, we will use most of the Browser API to
make sure the server recieves a good response from real human.

Browser test are including:
- Read / Set Cookie
- User Agent Test

To bypass this method, the required penetrator are need
to have following functions:
- Execute Js
- Have Browser API
- Synergy with both (Node.js might be a bad news for this)

# Misc
## Special Thanks
This project are basicly depends on [Dean Edwards' Packer](http://dean.edwards.name/packer/) Project, ported by [this repo](https://github.com/tholu/php-packer). Thanks to them.

## License
MIT, [here's a proof](LICENSE).