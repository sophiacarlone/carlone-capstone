# Logs
Scar — 09/15/2023 7:59 PM
getting switches together
harder when people won't react
keep it minimum next time
learned command `ip address add 192.168.88.2/24 broadcast + dev enp0s13f0u3` to add ip on a certain connection

Scar — 09/15/2023 10:11 PM
Learned very little, but still something about terminal switch stuff, like add and move directories
I can't make a direct vlan with multiple ports, so I have to make a bridge over the section of ports I want and go from there

Scar — 09/18/2023 5:45 PM
<image src="../media/FHILL.jpg"  controls></image>

Scar — 09/19/2023 6:47 PM
Yesterday, it the switch config work. Specifically, it wouldnt hit hydra
Learning about routerOS
I tried again today, and placed everything back where it was
this was actually the third time, with yesterday being a bust as well
today, I tried to additionally look at the firewall to see if that is where things are going wrong
I did end up changing the firewall iptables config in order to reflect the new ip address, later realized that the mask was also an issue
It is still not getting up
we tried looking at the modules to make sure that they were spf+ instead of qpf+ <b>(up to 10Gbps connection vs a 40Gbps connection)</b>.
no dice, and so we put everything back and talks is not going up

Scar — 09/21/2023 4:44 PM
What happened last night is that I made the config all over again on the other new fiber switch that we had. Everything then worked besides hydra.

Things that were changed from before:
no PVIDs were set
The IP was set to 128.153.145.21 because we the switch last in use (F2) had that ip.

I have a feeling the PVID or something else in the configuration (a small detail) was the only thing wrong
Today I looked at hydra, because that was the only thing that wasnt connected
I remembered that hydra not only was on multiple vlans, but I created a bridge for it a while back in "wave one", so I went to look at it.
Right now it is set on the private vlan. I asked if there was any point on it being on the public and/or other vlans (it was on all of them) and it seemed to be for the vms that COULD run on it.

Since no vms needed that help then, I commented out the bridge in the file in /etc/netplan/ and placed the regular config for a static ip. It now works.
works as in it can ping everything. There is a problem with a vm webservice that is used in COSI. I asked the last person who made and set the vm if there was a command I forgot that launches a vm. Will write command here if I learn about it, or what might be wrong

Scar — 09/28/2023 3:28 PM
Talos went down, memory stick issue
https://www.amazon.com/DDR3-1600MHz-PC3-12800-Unbuffered-Memory-Workstation/dp/B07D3YMPTV/ref=mp_s_a_1_3?crid=3BSZMR8RD97OS&keywords=ddr3%2Bram%2Becc%2Budimm&qid=1695929544&sprefix=ddr3%2Bram%2Becc%2Budimm%2B%2Caps%2C86&sr=8-3&th=1&psc=1

Scar — 09/29/2023 3:10 PM
We decided that hardware is degrading too much. We also don't have anything in the budget for a whole new server
This was all yesterday btw
I named the new server that we got from an alumni "talDOS" to put dhcp and both dns on
this hardware was from 2011. It didnt recognize ubuntu 22.04 because the kernel was too old, but it allowed me to poke in a grub shell for a bit before I made an ubuntu 20.04 bootable stick
there was no network, at first, but then someone later just switched the port and it was fine. I gave it a new ip address (I originally gave it talos which was still connected, which why it may have been confused)
then I just pointed them (Juno) in the right direction. I have done stuff like this before, and I was busy, and he wanted to learn

today, we are going to colo to finally establish connection
rn, I just took off everything I did to the switch (since this was the first one I used and failed) so that everything is more smooth and can start from scratch