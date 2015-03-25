# Mlmmj Simple Web Interface
A very simple web frontend in node for [mlmmj](http://mlmmj.org/).

> **Attention : run as `list`** :

> When you run the app, you have to run it as the `list` user if you want to have access to mlmmj's files :
```
sudo su list -c "node index.js"
```

## Structure

This is a Node.js app, that uses :

  * [Express](http://expressjs.com/) as a global framework, with sessions and flash messages
  * [Consolidate](https://github.com/tj/consolidate.js) & [Nunjucks](https://mozilla.github.io/nunjucks) as the template engine
  * [Passportjs](http://passportjs.org) for the authentification

And some local modules like `ConfigParser` (_cf. source code if you want to see more_)
  
## Configuration

Some options are available in the `config.json` file. Before launching the app,you must copy `config.json.dist` to `config.json` and change the desired settings : 

  * **Server**

    The settings allows you to change the port that the app use if you want to reverse-proxy it afterwards (_and you should_)

  * **App name**

    The app name is displayed in the navbar, on the left

  * **Mlmmj directory path**

    This path is the one that mlmmj uses to store all the content and parameters. Should be the default `/var/spool/mlmmj`  unless you manually changed it

## Authentification

The whole app needs authentication.

Authentification is managed by [passportjs](http://passportjs.org). The username and password of users are stored in the `config.json` file :

```json
{
    //...
    "users": [
        { "username": "admin", "password": "secret"},
        { "username": "jon", "password": "pass"}
    ],
    //...
}
```

## Licence

MIT ! See the [licence](https://github.com/tchapi/mlmmj-simple-web-interface/blob/master/LICENSE) file.

## To Do

  * Implement other functions such as :
      - i18n texts editing
  * Add a button to restart exim / postfix ?
  