# GreyScript Guestbook

Example guestbook. Keep in mind that there's no auth or anything implemented. This is purely a demo. You probably have to add a few things to make this secure.

# Requirements

### Compiler
* [Greybel](https://github.com/ayecue/greybel)

### Libraries
* [get-params](https://github.com/ayecue/greyscript-library/blob/main/scripts/library/get-param.src)
* [string](https://github.com/ayecue/greyscript-library/blob/main/scripts/library/string.src)
* [error](https://github.com/ayecue/greyscript-library/blob/main/scripts/library/error.src)
* [rlaunch](https://github.com/ayecue/greyscript-library/blob/main/scripts/rlaunch.src)
* [fs](https://github.com/ayecue/greyscript-library/blob/main/scripts/library/fs.src)
* [path](https://github.com/ayecue/greyscript-library/blob/main/scripts/library/path.src)

# Install
Try this first in singleplayer before you do anything in multiplayer.

* get [Greybel](https://github.com/ayecue/greybel)
* setup all the libraries. Best would be if you just install [greyscript-library](https://github.com/ayecue/greyscript-library) (I will add some more informations about this in the future)
* copy & paste all the files in `/src` into a directory
* setup the environment files `build.conf` and `local.conf`
* create a user named `clientuser` on your server (you can change that in the `/src/build.src` as well)
* compile the `/src/build.src` file `compile build.src --bin-folder /src/ --no-output --env-file /src/local.conf`
* execute the just compiled build binary
* if everything is setup correctly you got your own guestbook - if you got troubles contact me via [issues](https://github.com/ayecue/greyscript-guestbook/issues)

# API
It's pretty easy to use the `client-local` binary. There are three different endpoints implemented for now.
```
/healthcheck GET
/messages POST
/messages DELETE
```

### Make a healthcheck
```
client-local /healthcheck get
```

### Make a post
```
//you have to wrap your messages with "'", you're also allowed to use <br>
client-local /messages post username 'Hello world'
```

### Delete a post
```
//you gonna see the messageId on the guestbook
client-local /messages delete messageId
```

# How it looks like
![Guestbook](/images/demo.jpg)

# Future plans
* improve docs
* add features like auth