# Assignment 2
We want to gather some basic statistics for our security team. They want to know the top 8 IP addresses that hit our web servers.

Your task will be the following: Implement a script (use any language you want) to get the top 8 IP addresses out of an existing log file Save your script with no file extension It has to be an executable file there is no need for using arguments The output format will be the following:(8 lines - top saw IP addresses by the number of hits):

<ip_address><number_of_hits>

A real example output would look like this:

$ count

92.6.41.236 22

186.248.72.9 19

81.243.137.36 18

217.118.78.16 15

213.118.39.51 15

93.146.139.64 14

80.116.15.0 14

186.213.159.176 11

Logfile: Click here


# Please find the command to get the task done without using any argument.

cat /var/logfile/access.log | grep http://* | awk '{print $1}' | sort -n | uniq -c | sort -nr | head -n 8
