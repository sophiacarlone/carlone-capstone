# February 2024 - Logs

Scar — 02/01/2024 1:05 PM<br>
adjustments to the ping bot:<br>
specific channel<br>
say that an ip was pinged<br>
less over night
```
channel = client.get_channel(12324234183172)
await channel.send('hello')
```
https://discordpy.readthedocs.io/en/stable/faq.html#how-do-i-send-a-message-to-a-specific-channel<br>
128.153.221.225

Scar — 02/02/2024 1:13 AM<br>
My bot is spamming<br>
I was able to get it into a certain channel<br>
I'll move it to my own and see why it doesnt ping ip addresses

Scar — 02/08/2024 1:30 PM<br>
There are still problems with the purchasing for COSI. Specifically, COSI wants to get some universal rails in order to mount everything, but we don't know who can even put in the orders<br>
the new lab directors are going to email OIT and get internet access moved to COLO. We want to keep the momentum of those who want to make the big move

Scar — 02/12/2024 4:19 PM<br>
<b>(feedback for the capstone paper)</b><br>
Add a paragraph about COSI<br>
Talk a bit about the surge and talk more about what I did and why I choose to do that<br>
Make an executive summary<br>
talk about the ping bot<br>
in challenges, show how I had to be more flexible<br>
give myself more credit, this is my "legacy"<br>
explain more on topology and say how the power outages recently did not stop us

Scar — 02/14/2024 4:29 PM<br>
Using mdbook for the first time for my logs

Scar — 02/15/2024 3:57 PM<br>
Orange-blue direct link to 144 net

Scar — 02/15/2024 4:07 PM<br>
Green brown sc 

Scar — 02/15/2024 4:41 PM<br>
So, what was said above was for documentation purposes. it shows which link goes where, either to the 144 net (and the internet) or to the hill<br>
Juno was at OIT help desk when they told him that COSI got the link. He asked everyone in cosi at the time if they wanted to go, and only he and I went.<br>
We got down there and we were having trouble because even with a new transceiver and fiber cable, nothing was working. No blinky lights, so Juno called OIT.<br>
They came down there, and we debugged. It was OIT's transceiver that was broken. Oh well<br>
we got blinky lights and everything is ready for the great move besides getting rails<br>
which, by the way, we are trying to figure out the best time, but havent found it yet. Especially since my capstone is due march 1st<br>
Also, I got mdbook in a container on tiamat to host my logs online.<br>
there was some diffculty with the working directory in the Dockerfile, but I stole the one from the cosi book and it worked. I could not recreate the error to learn from it

Scar — 02/16/2024 9:33 PM<br>
too much rebooting on taldos when I was trying to test my pingbot <b>(it freaked out on boot and someone had to manually turn it back on)</b>

Scar — 02/18/2024 5:43 PM<br>
We unplugged our internet link in the server room and went down to colo to plug in the net link there.<br>
We got blinky lights on both the uplink to sc and from the connection oit provided to us, and we were able to confirm mirror was up, that means we are ready to move<br>
<image src="../media/FCOLO.jpg"  controls></image>

Scar — 02/20/2024 5:28 PM<br>
The great cosi move of 2024 has started<br>
7 people are helping<br>
We took out mirror, kasper, and taldos. We noticed that cables were mislabelled<br>
I personally am going to move things to colo

Scar — 02/20/2024 6:45 PM<br>
Going smoothly till we couldnt ping mirror<br>
"Copper" appearently means ethernet<br>
Cat8 is gold plated

Scar — 02/20/2024 9:30 PM<br>
Here is the summary of what went down now that the move is over for tonight<br>
The colo team got mirror, a kvm, taldos and kasper in physically. (with the right connections?) We knew we needed to make sure things are connected, and to make sure the switch->kasper fiber cables were in the right ports for the bridge <br>
There was some issue where mirror can be pinged but there was no ssh connection from Cary's laptop<br>
I did not bring my laptop, so I did not remember the password <b>(for the switch)</b>, and when we did get it, it did not seem to work for some reason<br>
we tried the management port, switching the fibers in kasper, the different vlans, and there was difficulty connecting to the switch<br>
My team then came back from colo. The people in the server room reorganized cables, but did not reorganize the servers
When Juno went down there for the second time, it seemed that taldos made a mistake on boot because ITS SUPER OLD
now there may be issues with kasper firewalls, and what can be pinged changes depending if the firewall is on or off, and colo might not recongize ipv6

Scar — 02/20/2024 9:37 PM<br>
what needs to be done is:<br>
- get mirror, taldos, and kasper in ship-shop shape
- get the other servers in the servery moved around to our liking (it wont be the same as on the diagram because of issues of square vs circle holds for the racks)
- get the ping bot down there with a server and possibly that kvm over ip
we will have to schedule another day to continue
but then again, the work in cosi should never really ever be done
<image src="../media/move1.jpg"  controls></image>
<image src="../media/move2.jpg"  controls></image>

Scar — 02/21/2024 1:28 PM<br>
Juno went down to colo. They switched the fibers on kasper on the config and rebooted taldos so that it didn't get stuck. Everything is good now 

Scar — 02/22/2024 2:28 PM<br>
Took out ziltoid

Scar — 02/25/2024 10:19 PM<br>
I didn't get a chance to put this all down in writing. This all happened on the 22nd and 23rd<br>
It's a break weekend and I wanted to finish moving around the servers to complete THE GREAT COSI MOVE OF 2024
Going to complain a bit here, the person who said they would help me (because some of those servers are heavy) didn't show up on the first day. My other friend showed up later and they helped out. When I was alone, I had to resort to stacking books to help me hold things in place <b>(reminds me of January 2023 and I had to put Talos back into the rack alone)</b><br>
over the two days, I (a good amount by myself, but I should say and the friend on the first day, and the late person on the second day) moved the servers around<br>
the research machines were on the bottom. The student machines were on the top.<br>
The big thing to learn are the different types of rails, and also how different racks have different holds that can be used with different rails. ie. square holds/holes can be used with one type of rail, and there were two other holds that were both circles, but of different sizes. That is something to look for when moving things, because this did switch the initial plan

Scar — 02/25/2024 10:26 PM<br>
today, I just got the docker for my website to host this all on built in docker and I pulled it on zones so that it would be on taldos. I would go on terminator and make it real, but I do not have the password on me and I have way to little energy to find it.

Scar — 02/26/2024 11:06 AM<br>
going though my capstone paper, I learned that conditioned power means to supply a proper voltage (as well as other characteristics)

Scar — Today at 12:09 AM<br>
Heck yeah I got a fist bump from Jeanna