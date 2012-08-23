[![build status](https://secure.travis-ci.org/unbalanced/grunt-simple-watch.png)](http://travis-ci.org/unbalanced/grunt-simple-watch)
grunt-simple-watch
==================

grunt task to watch files without using fs.watch or fs.watchFile

<h1>WHY?</h1>
Having all sort of weird issues with grunt watch?

This is because it currently uses an unstable node.js functionality - <a href="http://nodejs.org/api/fs.html#fs_fs_watch_filename_options_listener">fs.watch()</a>

<h1>What happend on my case</h1>
Im using grunt on a virtualbox dev server with Ubuntu 11.10 and Node 0.6.19.
My host system is Windows 7. 

My project files are on a shared folder between the host and server
When i update files on the shared folder it does not trigger the fs.watch 

<h1>The solution</h1>
DO NOT USE fs.watch

but solve it simply by polling for changes in the most basic/simple way.

This might be more CPU intensive, and might not work in high loads with many watched files.
But im not sure if the original watch task would do the job as well on this case. i just did not check.

<h1>Getting Started</h1>
Install this grunt plugin next to your project's [grunt.js gruntfile][getting_started] with: `npm install grunt-`

Then add this line to your project's `grunt.js` gruntfile:

```javascript
grunt.loadNpmTasks('grunt-simple-watch');
```

[grunt]: https://github.com/cowboy/grunt
[getting_started]: https://github.com/cowboy/grunt/blob/master/docs/getting_started.md

(or simple place the task file simple_watch.js in your grunt/tasks directory..)

use the command: <b>grunt simple-watch<b> (instead of: grunt watch)

<b>NO NEED TO CHANGE grunt.js configurations</b> (your gruntfile)!

as it keeps on using the "watch" config.


<h1>License</h1>
Copyright (c) 2012 Amir Souchami
Licensed under the MIT license.
