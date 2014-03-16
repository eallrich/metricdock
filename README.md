metricdock
==========

Receives metrics in JSON via HTTP and stores them in Whisper databases.

Running on Heroku
-----------------
Compile the slug using both python and redis buildpacks:
```shell
heroku config:set BUILDPACK_URL=https://github.com/ddollar/heroku-buildpack-multi.git
```

Tell the app about its publicly-reachable name:
```shell
heroku config:set PUBLIC_NAME=metrics1.example.com
```

Set the following based on your Swift endpoint:
```shell
heroku config:set SWIFT_API_KEY=0123456789ABCDEF
heroku config:set SWIFT_AUTHURL=https://objects.example.com/auth
heroku config:set SWIFT_CONTAINER=metrics1
heroku config:set SWIFT_USERNAME=metricdock:whisper
```

To enable redundancy, tell the app about other dock servers:
```shell
heroku config:set DOCKS=http://metrics2.example.com,http://metrics3.example.com
```
