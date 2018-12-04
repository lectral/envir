##Envir - linux environment loader

Working with applications that get configuration from environment? This simple bash script should simplify dealing with loading them :).

### Installation

```bash
➜ sudo ./envir.sh install
```

This will install script in /usr/local/bin. From now on it will be accessible via envir command.

### Usage

####Adding variables to enviroments

All environments will be stored inside ```$HOME/.envir``` directory. Remeber to give your variables unique name your variables  as they will overwride when you load another environment.

```bash
➜ envir test_app.DEBUG=1
➜ envir test_app.HOST="https://myhost"
➜ envir test_app.HOST="https://notmyhost" # this will HOST inside test_app
➜ envir test_app_2.APP_HOST="https://myhost"
```

####Listing enviroments

```bash
➜ envir list
test_app test_app_2
```

#### Loading variables

To load variables all you need to do is source envir script and then chain command that you want to use that environment. In the example ```npm start``` will have access to all enviroment variables defined in ```$HOME/.envir/test_app```

```bash
➜ envir test_app npm start
➜ source envir env
```
