# Open MSYS Here

This is a fork of Ziya SARIKAYA's
[open-conemu-here](https://github.com/ziyasal/atom-open-conemu-here) package. Since open-conemu-here does not provide a runtime choice of [ConEmu](https://conemu.github.io/) Tasks, it not convenient to change the task only via package setting (`extraArguments`) every time when you want to choose different tasks.

The open-msys-here is nothing but another open-conemu-here package, but with open msys within ConEmu as default, with the help of [`msys terminal connector`](https://conemu.github.io/en/CygwinMsysConnector.html).

## Install and Configure
1. Unzip the package to atom library.
2. Setup a `MSYS` Task in `ConEmu` as:
```shell
set CEMDIR=%ConEmuWorkDir% & cmd /k C:\msys\bin\conemu-msys-32.exe
```
3. Change the `cd "$HOME"` of `MSYS`'s profile as
```
if [ -n "$CEMDIR" ]; then
  CEMDIR1=$(echo "$CEMDIR" | sed -e 's/\\/\//g' -e 's/://')
  cd "/$CEMDIR1"
else
  cd "$HOME"
fi
```

Note that we can not change the startup dir of `MSYS` by default, so we introduce the macro `"$CEMDIR"`.

## Bugs
If you encounter a bug, performance issue, or malfunction, please add an [Issue](https://github.com/econwang/atom-open-msys-here/issues) with steps on how to reproduce the problem.

## License

Code and documentation are available according to the *MIT* License.
