# April 2023 - Logs
Scar — 04/03/2023 4:46 PM<br>
I should reset all the passwords

Scar — 04/03/2023 4:47 PM<br>
Sadly, time got the better of me and I forgot somethings. What needs to happen is there needs to be a bridge <b>(over ethernet ports)</b> in the vm host for the vms to connect so you can `ssh` in. You can look at hydra if you need an example.
<br>
<b>(Notes to self)</b> You should also be able to ssh into the vm if you are already at the host<br>
create a vlan page on book

Scar — 04/04/2023 1:42 PM<br>
hydra wasnt down before. I probably was the one who broke it a couple of weeks ago

Scar — 04/12/2023 10:59 PM<br>
Couldn't get m3 <b>(management switch)</b> out for the life of me<br>
Tried for over an hour and with two guys for help<br>
Had to cut my loses and just have m4<b>(different management switch)</b>  unscrewed so I can make progress

Scar — 04/12/2023 11:17 PM<br>
I put in the switch<br>
I plugged in the switch<br>
I labelled private and plugged that in so it is going thru the private switch<br>
I put in red dwarf as well<br>
I can now ping red dwarf

Scar — 04/12/2023 11:26 PM<br>
ethernet uses rj-45, but is not rj-45

Scar — 04/12/2023 11:41 PM<br>
find usb port, copy name, <br>
`screen usb-port 38400`

Scar — 04/13/2023 12:19 AM<br>
Didn't work!

Scar — 04/13/2023 6:09 PM<br>
tried to just undo the bridge I made a while ago and it still not working<br>
its not the cable<br>
took out all comments, but that shouldnt work<br>
its so fucking slow<br>
it has a `destination host unreachable` result

Scar — 04/13/2023 9:33 PM<br>
Hydra has no route to jesabelle but one to google. It can download updates<br>
need to check if it is getting it <b>(packages)</b> from mirror, I suspect not tho because it could not reach mirror before<br>
I keep getting a connection time out

Scar — 04/13/2023 9:42 PM<br>
`ssh hydra`       <br> 
`ssh: connect to host 128.153.145.42 port 13699: Connection timed out` <br>
before, I went into the nftables for our firewall and saw that there was a hole poked, but for port 13699 on hydra, while hydra was still on the default of port 22
<br>
going to `man ssh` on hydra shows where the config files are and that is where you can see in the `sshd.config` what port is is set at

Scar — 04/13/2023 9:50 PM<br>
I upgraded hydra, it restarted some services<br>
I got `traceroute`` on hydra and it seemed to be able to connect to everything in one hop<br>
I was able to ssh into ziltoid from hydra<br>
lets see, next steps is to try and get to hydra again. if not, this might be a firewall problem afterall

Scar — 04/17/2023 6:37 PM<br>
`tail -f /var/log/syslog` <b>(A new comman learned to output the end of syslog and keep it refreshing)</b> 
so I looked at hydra again to see why I cant ssh<br>
i was with another lab member: Peter

Scar — 04/17/2023 6:45 PM<br>
he told me about syslog, and apparently tail has a option called -f that means to constantly refresh<br>
we saw there was something called UFW BLOCK that was blocking that port.<br>
UFW means uncontrolled firewall, and every ubuntu server has it and you need to add a hole for ssh into that fire wall. Now I can get in

Scar — 04/18/2023 5:57 PM<br>
I learned from yesterday and when my vm could not be pinged or ping anything I looked at UFW. There I saw it was disabled

Scar — 04/19/2023 1:35 PM<br>
https://www.comparitech.com/net-admin/open-source-network-monitoring-tools/

Scar — 04/23/2023 6:06 PM<br>
today I went to clean up the server room and do some cable management before an important guest arrives<br>
there should be no tripping hazards in the room<br>
mounted m4 in the correct place<br>
we had to unplug ziltoid and talos for a bit to make things cleaner. This left DNS messy<br>
I had to have others help while I made a phone call and got food<br>
but when I got back, it was still partly down. I got on talos and it was just because nsd was down