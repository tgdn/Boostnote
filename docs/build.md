# Build

## Development

We use Webpack HMR to develop Boostnote.
Running the following commands, at the top of the project directory, will start Boostnote with the default configurations.

Install the required packages using yarn.

```
$ yarn
```

Build and run.

```
$ yarn run dev-start
```

This command runs `yarn run webpack` and `yarn run hot` in parallel. It is the same as running these commands in two terminals.

The `webpack` will watch for code changes and then apply them automatically.

If the following error occurs: `Failed to load resource: net::ERR_CONNECTION_REFUSED`, please reload Boostnote.

![net::ERR_CONNECTION_REFUSED](https://cloud.githubusercontent.com/assets/11307908/24343004/081e66ae-1279-11e7-8d9e-7f478043d835.png)

> ### Notice
> There are some cases where you have to refresh the app manually.
> 1. When editing a constructor method of a component
> 2. When adding a new css class (similar to 1: the CSS class is re-written by each component. This process occurs at the Constructor method.)

## Deploy

We use Grunt to automate deployment.
You can build the program by using `grunt`. However, we don't recommend this because the default task includes codesign and authenticode.

So, we've prepared a separate script which just makes an executable file.

```
grunt pre-build
```

You will find the executable in the `dist` directory. Note, the auto updater won't work because the app isn't signed.

If you find it necessary, you can use codesign or authenticode with this executable.
