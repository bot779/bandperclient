files: bandperclient and webgraph

command:
bandperclient
=============

Ruckus Wireless "executive" reports:
Reads syslog information and produces these reports:
TX bandwidth per client
RX bandwidth per client
TX packets per client
RX packets per client
Packet retransmissions per client
All of the above are available broken-down per operating system.
(requires buildclientos.txt script from the ruckusconf "package")
and...
Client count per operating system

Bonus: Can create pie-charts and bar-charts
(by default, produces "inscrutable" text versions)

Usage:
======
bandperclient [OPTIONS] [</var/log/messages>]

 If the word 'stdin' is substituted for a /var/log/messages file:"
  bandperclient will expect to read syslog entries on standard input"

 Options:
 --noreport ;# suppress reporting. Only process syslog messages
 --quick    ;# don't read or process syslog messages. Just do reporting."
 --webgraph ;# build html reports (instead of the default text versions)"
 --txb      ;# report on transmitted bytes"
 --txp      ;# report on transmitted packets"
 --rxb      ;# report on received bytes"
 --rxp      ;# report on received packets"
 --txr      ;# report on transmit retry packets"
 --count    ;# number of associated clients per OS"
 --roam     ;# roaming events"
 --roamnophone ;# roaming events excluding iOS or Android devices"
 --top <n>  ;# report on the top <n> devices"
 
 
command:
webgraph
========
 
Uses google Charts to make a pie chart.
Reads 2 columns of data from stdin
(Label and Value columns)
Generates html files.
The html code renders the charts in-browser
 
Usage:
======
webgraph [OPTIONS]

 Options:
 --filename <filename> ;# filename can be special name "stdout"
 --title <Chart Title>
 --type [pie|bar|column]
