# Logs
Scar — 10/05/2023 4:46 PM
Creating a new topology
we need to try getting a new fiber cable to colo and see if that is the issue
turns out fiber cables can get damaged pretty easily, which makes sense cause they are made of glass
Try 1
<image src="../media/topov1.jpg"  controls></image>
Version 2
<image src="../media/topov2.jpg"  controls></image>

Scar — 10/05/2023 5:31 PM
Cary was working in the server room with others to make that test mirror.
A discord bot revealed that MIRROR was down. I asked if this was on purpose and it was not
There were no lights to mirror AND the internet was down
so we looked and ziltoid and talos were not getting power at all
then they did after Cary flipped some breaker switches
But then I noticed nothing was coming in from OIT
but then packets did come in after a minute
everything is fine now but it seems like there was just a power outage for a second

Scar — 10/13/2023 3:42 PM
A couple things that happened in the last week:
Cary broke the network connection when we were trying to get colo connection running. The problem was with the transceiver
On Wednesday, I presented my topology to the group. I got feedback and answered questions
<image src="../media/finaltopo.jpg"  controls></image>
hydra might be moved to colo and we are going to change all ssh ports to not 22. It is based on a fun fact and because ssh hackers aim for the default port 22
I did have a very long discussion (that got a bit heated) about the accessibility decline of ziltoid if something bad happened to it.
I was talking to Cary last night and he mentioned something called "KVM over IP" that may allow us to have a kvm to everything in colo with out having to go down there or use an internet connection (but using a direct connection)

Scar — 10/13/2023 3:55 PM
https://www.tomshardware.com/how-to/kvm-over-ip-raspberry-pi
https://www.intel.com/content/www/us/en/business/enterprise-computers/resources/kvm-over-ip.html

Scar — 10/20/2023 2:56 PM
We fucked up a NAS by taking a hard drive out. It was in raid. If it is in raid one, thats a bit better
https://www.prepressure.com/library/technology/raid#raid-0
learn about `mdadm` which can check for raid configurations iff <b>(if and only if)</b> that was the packaged used to make the raid configurations in the first place
Cary just would look using `lsblk``
https://www.cyberciti.biz/faq/how-to-check-raid-configuration-in-linux/
https://raid.wiki.kernel.org/index.php/A_guide_to_mdadm
