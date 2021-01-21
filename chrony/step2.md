## Check Chrony Synchronization in Linux

To check if chrony is actually synchronized, we will use **chronyc**, which has 
the tracking option which will provide relevant information.

`chronyc tracking`{{execute}}

The listed files provide the following information:

* **Reference ID** – the reference ID and name to which the computer is currently synced.
* **Stratum** – number of hops to a computer with an attached reference clock.
* **Ref time** – this is the UTC time at which the last measurement from the reference source was made.
* **System time** – delay of system clock from synchronized server.
* **Last offset** – estimated offset of the last clock update.
* **RMS offset** – long term average of the offset value.
* **Frequency** – this is the rate by which the system’s clock would be wrong if chronyd is not correcting it. It is provided in ppm (parts per million).
* **Residual freq** – residual frequency indicated the difference between the measurements from reference source and the frequency currently being used.
* **Skew** – estimated error bound of the frequency.
* **Root delay** – total of the network path delays to the stratum computer, from which the computer is being synced.
* **Leap status** – this is the leap status which can have one of the following values – normal, insert second, delete second or not synchronized.

To check information about chrony’s sources, you can issue the below command.

`chronyc sources`{{execute}}

The columns are as follows:

* **M** -
    This indicates the mode of the source. `^` means a server, `=` means a peer and `#` indicates a locally connected reference clock. 
* **S** -
    This column indicates the state of the sources. "*" indicates the source to which `chronyd` is currently synchronized. "+" indicates acceptable sources which are combined with the selected source. "-" indicates acceptable sources which are excluded by the combining algorithm. "?" indicates sources to which connectivity has been lost or whose packets do not pass all tests. "x" indicates a clock which chronyd thinks is a falseticker (its time is inconsistent with a majority of other sources). "~" indicates a source whose time appears to have too much variability. The "?" condition is also shown at start-up, until at least 3 samples have been gathered from it. 
* **Name/IP address** -
    This shows the name or the `IP` address of the source, or reference `ID` for reference clock. 
* **Stratum** -
    This shows the stratum of the source, as reported in its most recently received sample. Stratum 1 indicates a computer with a locally attached reference clock. A computer that is synchronized to a stratum 1 computer is at stratum 2. A computer that is synchronized to a stratum 2 computer is at stratum 3, and so on. 
* **Poll** -
    This shows the rate at which the source is being polled, as a base-2 logarithm of the interval in seconds. Thus, a value of 6 would indicate that a measurement is being made every 64 seconds.
    `chronyd` automatically varies the polling rate in response to prevailing conditions. 
* **Reach** -
    This shows the source’s reach register printed as an octal number. The register has 8 bits and is updated on every received or missed packet from the source. A value of 377 indicates that a valid reply was received for all of the last eight transmissions. 
* **LastRx** -
    This column shows how long ago the last sample was received from the source. This is normally in seconds. The letters `m`, `h`, `d` or `y` indicate minutes, hours, days or years. A value of 10 years indicates there were no samples received from this source yet. 
* **Last sample** -
    This column shows the offset between the local clock and the source at the last measurement. The number in the square brackets shows the actual measured offset. This may be suffixed by `ns` (indicating nanoseconds), `us` (indicating microseconds), `ms` (indicating milliseconds), or `s` (indicating seconds). The number to the left of the square brackets shows the original measurement, adjusted to allow for any slews applied to the local clock since. The number following the `+/-` indicator shows the margin of error in the measurement. Positive offsets indicate that the local clock is ahead of the source. 
    
The sourcestats command displays information about the drift rate and offset estimation process for each of the sources currently being examined by `chronyd`.
The optional argument `-v` can be specified, meaning verbose. In this case, extra caption lines are shown as a reminder of the meanings of the columns.

`chronyc sourcestats`{{execute}}

 The columns are as follows:

* **Name/IP address** -
    This is the name or IP address of the NTP server (or peer) or reference ID of the reference clock to which the rest of the line relates. 
* **NP** -
    This is the number of sample points currently being retained for the server. The drift rate and current offset are estimated by performing a linear regression through these points. 
* **NR** -
    This is the number of runs of residuals having the same sign following the last regression. If this number starts to become too small relative to the number of samples, it indicates that a straight line is no longer a good fit to the data. If the number of runs is too low, chronyd discards older samples and re-runs the regression until the number of runs becomes acceptable. 
* **Span** -
    This is the interval between the oldest and newest samples. If no unit is shown the value is in seconds. In the example, the interval is 46 minutes. 
* **Frequency** -
    This is the estimated residual frequency for the server, in parts per million. In this case, the computer’s clock is estimated to be running 1 part in 109 slow relative to the server. 
* **Freq Skew** -
    This is the estimated error bounds on Freq (again in parts per million). 
* **Offset** -
    This is the estimated offset of the source. 
* **Std Dev** -
    This is the estimated sample standard deviation.
