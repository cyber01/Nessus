# Nessus_Pro_Cracked
Nessus is one of the many vulnerability scanners used during vulnerability assessments and penetration testing engagements, including malicious attacks. To install the crack, we need to download the regular version of Nessus (in my case, this is a *debian package), write in terminal:

    wget https://www.tenable.com/downloads/nessus/nessus*.deb && sudo dpkg -i nessus*.deb && sudo systemctl start nessusd.service

Go to https://127.0.01:8834/ and select when installing the managed scanner and select "enable"tenable.SK, and then set the login and password of the admin:admin. next we will start downloading the Nessus plugin, then we will start downloading the systemctl plugin to stop nessusd.service
to do this, we will write the following command-something more incomprehensible, so that we are not in shodan / population census / fifa / zoomeye, for this we will write the following command:

    sudo -s && /opt/nessus/sbin/nessus clipfix --setxmlrpc_listen_port=11111

    wget https://plugins.nessus.org/v2/nessus.php?f=all-2.0.tar.gz&u=4e2abfd83a40e2012ebf6537ade2f207&p=29a34e24fc12d3f5fdfbb1ae948972c6

To download plugins to Nessus and updates, you need to register the following, and then we have to create a plugins_feed_info.inc file with the following contents:

    sudo /opt/nessus/sbin/nessuscli update all-2.0.tar.gz

We put this text in a file:
PLUGIN_SET = "202206211520";
PLUGIN_FEED = "ProfessionalFeed (Direct)";
PLUGIN_FEED_TRANSPORT = "Tenable Network Security Lightning";

    cp /opt/nessus/var/nessus/plugin_feed_info.inc /opt/nessus/lib/nessus/plugins/plugin_feed_info.inc

    cp /opt/nessus/var/nessus/plugin_feed_info.inc /opt/nessus/var/nessus/.plugin_feed_info.inc

    chattr +i /opt/nessus/var/nessus/plugin_feed_info.inc /opt/nessus/var/nessus/.plugin_feed_info.inc

    chattr +i -R /opt/nessus/lib/nessus/plugins

    chattr -i /opt/nessus/lib/nessus/plugins/plugin_feed_info.inc

    chattr -i /opt/nessus/lib/nessus/plugins

![image](https://user-images.githubusercontent.com/108927927/194062073-3896e9f1-f64b-42eb-9bbf-0aa016073ad9.png)
After we start the sudo systemctl start nessusd.service service, after we open Nessus on the host that we installed, well, actually here:
![image](https://user-images.githubusercontent.com/108927927/194062157-1985ce41-9445-422c-8337-2b8322f10bc2.png)
![image](https://user-images.githubusercontent.com/108927927/194062193-6a3ee6ab-8550-451a-aebe-6223c5db2cab.png)


First download the latest version of Nessus (Windows or Linux) - https://www.tenable....ownloads/nessus

[For Linux]
1. Install nessus - sudo dpkg -i Nessus-8.10.1-debian6_amd64.deb
2. Start the Nessus service - service nessusd start
3. Open your browser and go to https://localhost:8834
4. At the prompts - Select Managed Scanner -> Managed by Tenable.sc
5. Create your account & password
6. Now we need get the latest plugins set (all the checkers and exploits) - Go to https://plugins.ness.../v2/plugins.php in order to get the latest checksum (date) of the plugins set.
7. Go to https://www.tenable....ssus-essentials and register a FREE Essentials account. Don't use the key sent to you on your email yet.
8. Now we need to generate our Offline Key - Execute "nessuscli fetch --challenge" in your console/shell.
9. Go to https://plugins.nessus.org/offline.php and copy the Offline key in the first prompt and enter your Free Essentials Account KEY (in your mailbox) in the second one.
10. Download the nessus-fetch.rc file and put it in /opt/nessus/etc/nessus/ directory.
11. Edit the file plugin_feed_info.inc OR create a new one in the following directories:
/opt/nessus/lib/nessus/plugins/
/opt/nessus/var/nessus/

with the following content:

PLUGIN_SET = "202007032004";
PLUGIN_FEED = "ProfessionalFeed (Direct)";

PLUGIN_FEED_TRANSPORT = "Tenable Network Security Lightning";

(You can change the PLUGIN_SET with the most updated one.)

12. Now you need to download all the plugins and manually install them in the system - Go to https://plugins.ness...-ESSENTIALS-KEY (Here you can use the Offline KEY and Essentials Account KEY) to download the latest zip file.)

13. Go to the console/shell and execute "/opt/nessus/sbin/nessuscli update all-2.0.tar.gz"
13. You can now restart the service - service nessusd restart

[IMPORTANT] If your license is not corrently updated after you login, repeat step 11. [IMPORTANT]


[FOR WINDOWS]

Repeat all the steps to 7.

8. Execute the offline key fetch - Open CMD and paste "D:\Nessus\nessuscli.exe fetch --challenge" (If Nessus is installed in D:\Nessus)
9. Go to https://plugins.nessus.org/offline.php and copy the Offline key in the first prompt and enter your Free Essentials Account KEY (in your mailbox) in the second one.
10. Download the nessus-fetch.rc file and put it in C:\ProgramData\Tenable\Nessus\conf\ directory.
11. Edit the file plugin_feed_info.inc OR create a new one in the following directories:
C:\ProgramData\Tenable\Nessus\nessus\
C:\ProgramData\Tenable\Nessus\nessus\plugins\

with the following content:

PLUGIN_SET = "202007032004";
PLUGIN_FEED = "ProfessionalFeed (Direct)";

PLUGIN_FEED_TRANSPORT = "Tenable Network Security Lightning";

(You can change the PLUGIN_SET with the most updated one from https://plugins.ness...v2/plugins.php)

12. Now you need to download all the plugins and manually install them in the system - Go to https://plugins.ness...-ESSENTIALS-KEY (Here you can use the Offline KEY and Essentials Account KEY) to download the zip file.)
13. Go to the console/shell and execute "D:\Nessus\nessuscli.exe update C:\Path\To\The\Downloaded-file\all-2.0.tar.gz"
14. You can now restart the service - execute net stop "Tenable Nessus" && net start "Tenable Nessus" --- Or simply just go to Services -> Restart the Tenable Nessus service.

[IMPORTANT] If your license is not corrently updated after you login, repeat step 11. [IMPORTANT]
