Added `pn add @types/node -E -D` b/c seeing error in tsconfig.json,

```
Cannot find type definition file for 'node'.
  The file is in the program because:
    Entry point of type library 'node' specified in compilerOptions
```

However installing this dependency did not fix the error.

**Q?>** Should all package installation commands be run with `ns`?

Something like `ns install <package>`.

> You will have to use `--shamefully-hoist` flag if you call `pnpm` on your own.

I belive this applies to NativeScript plugins only. Other packages can be installed normally.

TODO: add Android Emulator

# Build errors

> WARNING: You should add "svelte" to the "resolve.conditionNames" array in your webpack config. See https://github.com/sveltejs/svelte-loader#resolveconditionnames for more information

https://github.com/sveltejs/svelte-loader#resolveconditionnames

> BUG! exception in phase 'semantic analysis' in source unit '_BuildScript_' Unsupported class file major version 63

- https://github.com/NativeScript/NativeScript/issues/10174
- https://github.com/NativeScript/NativeScript/issues/10174#issuecomment-1732274777

```
Downloading https://services.gradle.org/distributions/gradle-7.5-bin.zip
```

https://askubuntu.com/a/1393645

```
apt purge --autoremove
```

https://askubuntu.com/questions/104126/can-i-purge-configuration-files-after-ive-removed-the-package

```bash
apt purge ?config-files
```

# Icons

https://icon.kitchen/
