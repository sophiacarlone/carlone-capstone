# Logs

Scar — 02/06/2023 8:19 PM <br>
Hydra:<br>
Had to redo partitions (add filesystem then mount)<br>
Didn't work cause we were one letter off<br>
Then we created pools with zpools (had to write nothing to all partitions)

Scar — 02/07/2023 1:58 AM<br>
MAKE IT A VISUAL TREE <b>(an idea to demonstrate my capstone)</b><br>
Have the root be a network, and it's children the most important things for the network (dns, firewall, other) with their own branches (firewall -> ip tables)<br>
It can be an animation/program<br>
Aaah

Scar — 02/09/2023 2:21 PM<br>
someone cant talk to prometheus or red drawf<br>
I couldnt even ping with prometheus.cslabs.clarkson.edu

Scar — 02/10/2023 1:33 PM<br>
went down to COLO and OIT and talked to Joshua and another guy and saw that they have given us the connection <b>(to the internet)</b>

Scar — 02/13/2023 2:04 PM<br>
Red Dwarf and Prometheus were down. Went in to see that it might just be the ethernet connection causing it. I saw that the m3 and m2 switch cable were not connected to the private switch. I connected those and made sure the lights were going up on the switch. Now to try to ping

Scar — 02/13/2023 2:12 PM<br>
Another `Destination Host Unreachable`<br>
List of strategies:<br>
plug into my computer and use `nmap`` and find ip address<br>
hook up to monitor and "hack" in

Scar — 02/15/2023 1:38 PM<br>
back to red dwarf and m3 switch. Switch doesnt seem connected to the internet either<br>
learned how to test cables, which is usually the issue

Scar — 02/16/2023 1:38 PM<br>
Jonathan helped me find the ips of the switches, I realized it was on zones<br>
another email needing those servers <b>(red dwarf and prometheus since they are research servers)</b>

Scar — 02/16/2023 1:53 PM<br>
I remember what I can do, its the same thing as when I was working on Ziltoid:<br>
When it couldnt connect to the internet, but we needed to use a switch, we used a direct ethernet connection so we<br> didnt depend on other connections that it didnt have<br>
I can't get into m3 to check the vlans, but if I could just use a direct connection, then I should be able to ping and get onto the GUI in the browser<br>
I will have to try it out

Scar — 02/19/2023 2:19 PM<br>
talking to Jonathan about which vlans on m3 go where

Scar — 02/20/2023 2:11 PM<br>
getting the hardware for "wave 4" <b>(I was previously calling steps in the plan of this capstone waves. Wave 4 is for when all the hardware is in and we move the servers around)</b><br>
switch is not the right model<br>
got the transceiver modules <b>(these go on the end of cables to plug into our fiber switches)</b>

Scar — 02/20/2023 2:25 PM<br>
noticed book <b>(cosi documentation)</b> changes were never built in the docker

Scar — 02/20/2023 2:40 PM<br>
trying to get hydra vms back up, but the `ssh -X hydra virt-manager`<br>
 (virt-manager) keeps crashing

 Scar — 02/20/2023 2:54 PM<br>
IT WAS BECAUSE I WAS BACKSPACING TOO MANY TIMES <b>(I later found a better command to do to what I wanted)</b>

Scar — 02/23/2023 5:16 PM<br>
turns out it was the correct switch <b>(see above)</b>

Scar — 02/24/2023 3:42 PM<br>
got onto switch 3 config via ethernet to computer connection (was almost about to mess up switch 4)<br>
going to check out the vlans and see what is wrong <b>(in the config (If I remember correctly))</b>

Scar — 02/24/2023 4:57 PM<br>
Reorganizing the cables to make the port set up easier

Scar — 02/27/2023 8:09 PM<br>
Jonathan not giving me credit smh <b>(not a big deal. It was in reference to working on the research machines, but he did do the majority of it)</b>

Scar — 02/28/2023 1:43 PM<br>
someone wants to donate to COSI. He said it was an old machine, but still a beef boy. I directed him to our documentation for him to look at

Scar — 02/28/2023 6:09 PM<br>
looking at throughput<br>
I have this idea of an influxdb page for monitoring this type of data<br>
https://www.ittsystems.com/network-throughput/#wbounce-modal

Scar — 02/28/2023 6:36 PM<br>
doesnt seem like we can get an accurate measure of throughput until I am on the network, which the wifi is down rn