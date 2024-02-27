# Logs

Scar — 02/06/2023 8:19 PM
Hydra:
Had to redo partitions (add filesystem then mount)
Didn't work cause we were one letter off
Then we created pools with zpools (had to write nothing to all partitions)

Scar — 02/07/2023 1:58 AM
MAKE IT A VISUAL TREE
Have the root be a network, and it's children the most important things for the network (dns, firewall, other) with their own branches (firewall -> ip tables)
It can be an animation/program
Aaah

Scar — 02/09/2023 2:21 PM
someone cant talk to prometheus or red drawf
I couldnt even ping with prometheus.cslabs.clarkson.edu

Scar — 02/10/2023 1:33 PM
went down to COLO and OIT and talked to Joshua and another guy and saw that they have given us the connection

Scar — 02/13/2023 2:04 PM
Red Dwarf and Prometheus was down. Went in to see that it might just be the ethernet connection. I saw that the m3 and m2 switch cable were not connected to the private switch. connected those and made sure the lights were going up on the switch. Now to try to ping

Scar — 02/13/2023 2:12 PM
Another Destination Host Unreachable
List of strategies:
plug into my computer and just nmap and find ip address
hook up to monitor and hack in

Scar — 02/15/2023 1:38 PM
back to red dwarf and m3 switch. Switch doesnt seem connected to the internet either
learned how to test cables, which is usually the issue

Scar — 02/16/2023 1:38 PM
Jonathan helped me find the ips of the switches, I realized it was on zones
another email needing those servers

Scar — 02/16/2023 1:53 PM
I remember what I can do, its the same thing as when I was working on Ziltoid:
When it couldnt connect to the internet, but we needed to use a switch, we used a direct ethernet connection so we didnt depend on other connections that it didnt have
I cant get into m3 to check the vlans, but if I could just use a direct connection, then I should be able to ping and get onto the gui in the browser
I will have to try it out

Scar — 02/19/2023 2:19 PM
talking to Jonathan about which vlans on m3 go where

Scar — 02/20/2023 2:11 PM
getting the hardware for wave 4
switch is not the right model
got the transciever modules

Scar — 02/20/2023 2:25 PM
noticed book changes were never built in the docker

Scar — 02/20/2023 2:40 PM
trying to get hydra vms back up, but the ssh -X hydra virt-manager
 (virt-manager) keeps crashing

 Scar — 02/20/2023 2:54 PM
IT WAS BECAUSE I WAS BACKSPACING TOO MANY TIMES

Scar — 02/23/2023 5:16 PM
turns out it was the correct switch

Scar — 02/24/2023 3:42 PM
got onto switch 3 config via ethernet to computer connection (was almost about to mess up switch 4)
going to check out the vlans and see what is wrong

Scar — 02/24/2023 4:57 PM
Reorganizing the cables to make the port set up easier

Scar — 02/27/2023 8:09 PM
Jonathan not giving me credit smh

Scar — 02/28/2023 1:43 PM
someone wants to donate to cosi. He said it was an old machine, but still a beef boy. I directed him to our documentation for him to look at

Scar — 02/28/2023 6:09 PM
looking at throughput
I have this idea of an influxdb page for monitoring this type of data
https://www.ittsystems.com/network-throughput/#wbounce-modal

Scar — 02/28/2023 6:36 PM
doesnt seem like we can get an accurate measure of thruput until I am on the network, which the wifi is down rn