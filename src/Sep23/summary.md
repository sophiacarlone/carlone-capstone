# September 2023

A lot happened this month, and I believe it is because the  new fiber switches that are needed for a COSI-COLO connection finally arrived about a week before the start of this new fall semester, about 6 months after COSI put the order in. I invited people to join me in setting up those switches. More people than I expected came and it was hard to fit in the server room and I didn’t know what to do with everyone who showed up.

This was most about interacting with the new switches:
- How to get a connection to them
- How to use RouterOS via GUI and some CLI
- Configuring them to the way COSI needed. 
- What servers need what VLANs to operate (mostly about which VLANs were necessary for Hydra right now)

I had some trial and error with the configuration of the new switch. It may have been due to the extra elements in VLAN configuration that I filled out, but now they seem to be unnecessary. Also, there was an error in the firewall for packets to go to this new device. After changing the IPtables used for our firewall, we actually took down more of the network, including our weekly meeting tool: talks.cosi.clarkson.edu. We also made sure that we were using the correct transceivers for each port/connection used. 

This is also the start of big hardware issues in the servers (besides the one that got us to this place). Talos could not detect its own memory, and that is why there is a new primary DNS server called TalDOS (I like the name ) and Talos being promoted to a secondary server.