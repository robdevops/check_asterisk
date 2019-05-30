# check_asterisk
check_asterisk plugin for Nagios / Icinga. Warns if Asterisk isn't responding, or values are outside specified limits. Returns performance data.

## Description   

## Dependencies
* asterisk
* bash 3.2
* awk

## Usage

Must be run as root.

```
Usage: check_asterisk [ -c <minimum calls> ] [ -a <minimum channels> ] [ -p <minimum peers> ] [ -t <maximum capacity> ]
```

### Example output
```
sudo check_asterisk
OK: Calls: 23, Channels: 45, Peers: 90, Capacity: 23.00%. Last reload: 1 week, 20 hours, 38 minutes, 56 seconds |calls=23;;; channels=45;;; peers=90;;; capacity=23.00%;;; 
0
```

```
check_asterisk  -p 100 -t 10%
WARNING: Peers, Capacity outside specified threshold. Calls: 20, Channels: 40, Peers: 90, Capacity: 20.00%. Last reload: 1 week, 20 hours, 41 minutes, 14 seconds |calls=20;;; channels=40;;; peers=90;;; capacity=20.00%;;;
echo $?
1
```
