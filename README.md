[![Build Status](https://jenkins.asl.ethz.ch/buildStatus/icon?job=cuckoo_time_translator)](https://jenkins.asl.ethz.ch/job/cuckoo_time_translator/)

# CuckooTimeTranslator
### Algorithms for translating times emitted by other (cheap) clocks into local system time
The dominant application is translating hardware timestamps of a sensor into the system time of a receiving computer system.

[!["Point Grey Chameleon3 timing"](https://github.com/ethz-asl/cuckoo_time_translator/wiki/images/chameleon10kHz-with-legend.png "Point Grey Chameleon3 timing")](https://github.com/ethz-asl/cuckoo_time_translator/wiki#example-plot)


### Scope
Currently it covers on way communication based translation only.
I.e. the foreign clock does not answer to any delay estimation / synchronization messages.

Please note that typically this cannot be carried out perfectly.
There will be noise in the translation and an unknown bias (offset), such as the offset from the blue to the green points above.
In particular in the one way case.
However, in many applications it is possible to calibrate for the offset using additional information such at sensor measurements.
This step is beyond this repository.

### Why call it translation rather than synchronization? 
Because **synchronization** refers to what one does to clocks to make them run at the same speed and yield similar times when read at the same time (as for instance NTP and PTP do to computer clocks), whereas the algorithms in this repository are trying to only **translate** the time of one clock for a given event into the another clock's time for the *same* event and not touch the clocks at all.


### Examples for how to use it in a ROS sensor driver:
See [usage examples](https://github.com/ethz-asl/cuckoo_time_translator/wiki#usage-examples-ros-sensor-drivers).
