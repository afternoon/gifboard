gifboard
========

Monitor your Jenkins build pipelines with animated GIFs.

![Example](http://i.giphy.com/l41m3JUjvS7UeJZQY.gif)

GIFs come from the wonderful [Giphy](http://giphy.com/).

Build Pipelines
---------------

gifboard displays the status of build pipelines created with the [Jenkins Build
Pipeline
Plugin](https://wiki.jenkins-ci.org/display/JENKINS/Build+Pipeline+Plugin). If
you're not using that, gifboard currently won't work. (Though it would be a
straightforward change to monitor jobs - hint hint.)

Usage
-----

- Clone the repo to `$JENKINS_HOME/userContent` on your Jenkins server (I
  recommend creating a job to do this)
- Open `http://your-jenkins/userContent/gifboard/index.html#/?pipeline=foo`

URL Parameters
--------------

### `pipeline`

```
pipeline=foo&pipeline=bar
```

Specify the pipelines you want to monitor. The number of pipelines is limited
only by screen space and your machine's ability to render loads of animated GIFs
at once.

### `pass`/`fail`

```
pass=dance
fail=facepalm
```

gifboard shows a random Giphy GIF matching a tag for each pipeline. Use `pass`
and `fail` to specify which tags to use for passing and failing pipelines.
Currently only GIFs rated PG-13 or below are shown.

### `jenkins`

```
jenkins=localhost
```

Specify the Jenkins host name. Defaults to the origin host from which gifboard was loaded.

### CORS

Jenkins doesn't send CORS headers by default, so your browser may object to you
trying to run gifboard on a different server from Jenkins.

You can use the [Cors Filter
Plugin](https://wiki.jenkins-ci.org/display/JENKINS/Cors+Filter+Plugin) to add
CORS headers to API requests.

Alternatively, you can serve gifboard from your Jenkins host by placing it in
the `$JENKINS_HOME/userContent` directory. See [User
Content](https://wiki.jenkins-ci.org/display/JENKINS/User+Content) for more
information.

Thanks
------

[Giphy](http://giphy.com/)!
