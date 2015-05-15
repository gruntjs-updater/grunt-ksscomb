# grunt-Ksscomb 

Grunt plugin for sorting CSS properties in specific order with support for custom @includes.

## Getting Started

This plugin requires Grunt `0.4.x`.

If you haven't used [Grunt](http://gruntjs.com/) before, be sure to check out the [Getting Started](http://gruntjs.com/getting-started) guide, as it explains how to create a [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as install and use Grunt plugins. Once you're familiar with that process, you may install this plugin with this command:

```shell
npm install grunt-ksscomb --save-dev
```

Once the plugin has been installed, it may be enabled inside your Gruntfile with this line of JavaScript:

```js
grunt.loadNpmTasks('grunt-ksscomb');
```

## The "csscomb" task

### Overview
In your project's Gruntfile, add a section named `csscomb` to the data object passed into `grunt.initConfig()`.

```js
grunt.initConfig({
    csscomb: {
        options: {
            // Task-specific options go here.
        },
        your_target: {
            // Target-specific file lists and/or options go here.
        },
    }
});
```

### Options

#### options.config
Type: `String`
Default value: `null`

A string value that is used to specify custom-csscomb.json file path.

### Usage Examples

```js
  grunt.loadNpmTasks('grunt-ksscomb');

  // Define the configuration for all the tasks
  grunt.initConfig({

    ksscomb: {
      options: {
        config: '.ksscomb.json'
      },
      dynamic: {
        expand: true,
        cwd: 'styles/',
        src: ['**/*.scss'],
        dest: 'styles/',
        ext: '.scss'
      }
    },

  });

  grunt.registerTask('groupCSS', 'Group CSS into groups', function () {
    grunt.task.run([
      'ksscomb'
    ]);
  });
```
