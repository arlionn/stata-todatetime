Description
-----------

Convert Stata strings to date-time. I have to do this fairly often and this is a convenient wrapper for the built-in `clock, date, dofc` functions.

Requirements
------------

I only have access to Stata 13.1, so I impose that to be the minimum. The command is really simple, however, so I would not be surprised if it worked with earlier versions.

Installation
------------

```stata
net install todatetime, from(https://raw.githubusercontent.com/mcaceresb/stata-todatetime/master/)
```

Examples
---------

```stata
sysuse gnp96
tostring date, format(%td_NN/DD/CCYY) gen(datestr) force
todatetime datestr, gen(dateback) datefmt(MDY)
assert date == dateback
```
