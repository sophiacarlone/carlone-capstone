# March 2023 - Logs

Scar — 03/02/2023 8:48 PM<br>
I wanna make a bot in the cosi server so that when something becomes unpingable it lets people know
and an influxdb site<br>
also, a lot of shit happened with the firewall going down, but I couldnt bring myself to help after I learned of a death in the family <b>(good job to the others)</b>

Scar — 03/07/2023 9:10 PM<br>
organize servers <b>(idea)</b>

Scar — 03/08/2023 1:09 PM<br>
reading for literature review. I will be focused on network configurations and measurement based on the Jones - IT article<br>
cleaned out some of the server room a bit<br>
https://en.wikipedia.org/wiki/Simple_Network_Management_Protocol<br>
https://www.netreo.com/blog/network-telemetry-it-executive-guide/

Scar — 03/08/2023 1:27 PM<br>
https://www.itjones.com/blogs/2022/1/8/network-management-best-practices-for-businesses - my first source for network management

Scar — 03/08/2023 1:39 PM<br>
https://www.dnsstuff.com/network-management

Scar — 03/08/2023 3:35 PM<br>
https://en.wikipedia.org/wiki/Simple_Network_Management_Protocol

Scar — 03/25/2023 9:25 PM<br>
ok, I just had this whole thing with making a vm for sc350 so let me recount <b>(I never  elaborated on this. This is briefly mentioned elsewhere in logs. There was two main issues, one was getting the vm connected to the internet, and the other was being able to `ssh` into the vm after it did receive internet connection. The first problem was with the brige configuration on hydra. At that point, Hydra was connected to both the private and public vlans, and this vm should only be on the private. The other problem stemmed from the UFW having port 22 for ssh closed)</b>

Scar — 03/27/2023 5:22 PM<br>
ssh outside cosi is broken

Scar — 03/29/2023 12:28 PM<br>
From nasa: how easy is it to go thru once you are in the network

Scar — 03/30/2023 4:50 PM<br>
the switches wont come for another 11 weeks