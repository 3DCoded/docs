# Klipper iMacros

Flexible Interpreted Macros

### Why?

This project was created as an experiment. What could happen if Klipper macros were fully interpreted, not rendered? This is _not_ intended as a finished product for your printer (at least not yet). The thinking behind interpreted macros is that they can receive updates mid-run, do more complex logic, and allow for faster testing of macros or parts of Klippy extras.

!!! info "More info on macro [rendering](../DynamicMacros/features/rendering/) and [variable updates](../DynamicMacros/features/receivingvariables/)"

### Installation

Run the following commands in SSH:

```
cd ~
git clone https://github.com/3DCoded/iMacros
cd iMacros
ln -f imacro.py ~/klipper/klippy/extras/imacro.py
sudo service klipper restart
```

### Usage

iMacros can be defined with the following configuration options:

```ini
[imacro name]
#script:
#  A Python script using the special functions listed below.
#path:
#  The path to a Python script on the local filesystem. Either this
#  parameter or "script" must be provided.
#absolute_path: False
#  Ignored if "script" is set. If this is set to True, the path will
#  reference an absolute path. If set to false, the path will be
#  relative to the printer configuration folder.
#description: iMacro
#  This will add a short description used at the HTLP command or while
#  using the auto completion feature. Default "iMacro"
```

To run an iMacro, simply use the command that's the name of your macro.

### Updating Macros

You can update file-based iMacros without restarting Klipper. However, iMacros directly declared within the printer configuration cannot be updated without restarting Klipper. This makes file-based iMacros more suitable for the majority of use-cases.

### Python Utilities

iMacros includes extra Python utilities to make writing iMacros simpler and more powerful.

- `printer`
  This is just like the `printer` object in a standard `gcode_macro`. For example, you can use `printer.toolhead.homed_axes` to get a string of the currently homed axes.
- `params`
  This is just like the `params` object in a standard `gcode_macro`. For example, you can use `params.NAME` to get the value of the parameter called `NAME`. If the parameter does not exist, `None` is returned.
- `rawparams`
  This is just like the `rawparams` object in a standard `gcode_macro`. This is a string representing all the parameters passed to the macro.
- `cmd`
  Unique to iMacros. This allows for executing G-code commands with a custom syntax. For example, `cmd.G1(x=100)` runs `G1 X100`. A combination of positional and keyword arguments can be passed. For example, `cmd.G1('X100', 'Y150', F=6000)` will run `G1 X100 Y150 F6000`. You can also pass full commands to `cmd` by calling it. For example, `cmd('G1 X100 Y150 F6000')` will run the same G-code as the previous example.
- `respond`
  Prints information in the printer console. By default, this is HTML-escaped, but to disable the escaping, `unsafe=True` can be passed to the function.