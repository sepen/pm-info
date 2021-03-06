# pm-info

Battery info from APM/ACPI files

**pm-info** is a tool that shows the status of our laptop battery. \
It supports both APM and ACPI methods, and allows several options to
customize the output result shown, which makes it perfect for use from
other scripts.

## Usage
```
$ pm-info [option(s)]

Where options are:
   -v           Print verbose info
   -k           Print kernel driver version
   -b           Print bios driver version
   -s           Print battery status
   -c           Print battery capacity
   -cf          Print battery capacity full
   -cw          Print battery capacity warning
   -cl          Print battery capacity low
   -mv          Print baterry voltage
   -mf          Print battery voltage full
   -p           Print battery charge percentage
   -t           Print battery charge time
   -u           Print units for battery charge time
   -e           Print end of line
   -C "STRING"  Print output in custom format
   -h           Print this help information
   -V           Print version information
```

## Examples

Examples which worked with APM/ACPI:
```
$ pm-info
$ pm-info -C "Batt: %s (%p)"
$ pm-info -v
```

Examples which only worked with APM:
```
$ pm-info -b
$ pm-info -t
$ pm-info -C "Battery Status: %p (%t%u), AC: %s"
$ pm-info -C "BIOS Version %b (Kernel Driver Version %k): %p"
```

Examples which only worked with ACPI:
```
$ pm-info -mv
$ pm-info -cw
$ pm-info -C "Batt: %s %p - Capacity: %c/%cf mAh - Voltage: %mv/%mf mV"
```