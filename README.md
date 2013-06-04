grunt-simple-watch
==================

grunt task to watch files without using fs.watch or fs.watchFile


## Getting Started
_If you haven't used [grunt][] before, be sure to check out the [Getting Started][] guide._

From the same directory as your project's [Gruntfile][Getting Started] and [package.json][], install this plugin with the following command:

```bash
npm install grunt-simple-watch --save-dev
```

Once that's done, add this line to your project's Gruntfile:

```js
grunt.loadNpmTasks('grunt-simple-watch');
```

If the plugin has been installed correctly, running `grunt --help` at the command line should list the newly-installed plugin's task or tasks. In addition, the plugin should be listed in package.json as a `devDependency`, which ensures that it will be installed whenever the `npm install` command is run.

[grunt]: http://gruntjs.com/
[Getting Started]: https://github.com/gruntjs/grunt/blob/devel/docs/getting_started.md
[package.json]: https://npmjs.org/doc/json.html

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

--

Developed at SupersonicAds R&D labs.

<h1>License</h1>
Copyright (c) 2012 Amir Souchami 
Licensed under the MIT license.
