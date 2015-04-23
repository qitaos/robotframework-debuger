#User Guide.

# Introduction #
RDB is a debuger of robotframework, It's implemented with RF listener. It supports keyword level debug.

# Installation #
## Python ##
RDB runs on Python >=2.5. It's not tested on other python version.

## Robot Framework ##
RDB is works with RobotFramework >= 2.1.

# Run pybot with debuger #
RDB is a listener of robot. It's can startup with "--listener" parameter in pybot. the listener is accepted a breakpoint as parameter. e.g.

```
D:\>pybot --listener "rdb.Listener:set*" "Demo.html"
==============================================================================
Large Log Demo
==============================================================================
Equals_demo
==============================================================================
Open 'http://127.0.0.1:2592' in browser to monitor robot status.
==============================================================================
```

Start pybot with debuger, It's puased at the keyword name like "set**" (e.g. set varaible).**

# Configure debuger with setting file #
RDB supports save the breakpoint list in setting file. and pause the test case
at any one of breakpoints.

```
D:\>pybot --listener "rdb.Listener:test.rdb" "Demo.html"
```

It's loading the debuger setting from test.rdb file. Note: the file extension name need ".rdb".

## Setting items in the rdb file: ##
  * BPS\_LIST -- the breakpoint list.
  * WATCHING\_LIST -- variable watching list
  * LOGGING\_FILE --
  * WEB\_PORT -- web debug port.

Example:
```
BPS_LIST=Log
BPS_LIST=Connect to host
WATCHING_LIST=${var1}
WATCHING_LIST=${var2}
WEB_PORT=8080
```