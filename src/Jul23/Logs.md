# Logs
Scar — 07/24/2023 4:03 PM
Talos is breaking down over the summer. I have it rebooted physically then get the service back up

Scar — 07/24/2023 9:49 PM
Nsd.service is failing on boot. I learned about systemd options and it's config file for services and crontab

Scar — 07/29/2023 6:24 PM
The problem was the nsd.service was failing on boot with error saying it was "restarting too quickly" through some research of the problem in systemd, turns out that package has files in /etc/systemd/system/multi-user.target.wants in which you can adjust how systemd interacts with the service. Since it was being restarted too quickly, you can find that among all other commands allowed and not there by default, there is StartLimitBurst=x where x is an int that represents how many tries to restart the service, and StartLimitInterval=x where x is an int that sets how long in between each restart attempt.

Scar — 07/29/2023 6:59 PM
There was an error of network unreachable for some reason before it was fixed, the cause of it was not determined