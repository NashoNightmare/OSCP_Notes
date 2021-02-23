# 6.0 Passive Information Gathering.
We could stage out the five phases of hacking as defined in the image below. The first step of the phases is Passive Information Gathereing. AKA OSINT (Open Source Intelligence). And we should maintain high level of secrecy about our actions and intentions.

Passive Information Gathering is the process of collecting openly available information about the target, Generally without any direct interaction with the target.

**The five phases of hacking**
![alt text](https://github.com/NashoNightmare/OSCP-Notes/blob/master/five-phases.png)

## 6.1 Taking Notes
Most important thing to do in a passive recon is taking notes in well detailed format, despite the fact the information seems advantageous or disadvantageous.

## 6.2 Website Recon
If the client has a website, we can gather basic information by simply browsing the website. Website may contain subdomains it is lot more convenient if we have a eye on those subdomains for more information. And we can look on the employee or company related person's social media information. 

Special note by Nasho : We could possibly enhance our OSINT skill by taking random ctf challenges and wargames.

## 6.3 WhoIs Enumeration
Database tool that can provide information about a domain name, such as the name server and registrar. This information is often public since registrars charge a fee for provate registration.

> `whois <domain_name>`

## 6.4 Google Hacking
> `site:<example.com>` - Shows only the results from the address. Also shows subdomains and pages.

> `site:<example.com> filetype:<file_type>` - Shows the results only corresponding to the file type and website.

> `site:<example.com> -filetype:<file_type>` - Shows the results only corresponding to the website while excluding corresponding filetype.

> `intitle:"<title>" "words"` - To find pages that contain "title" in the title and the words "words". Most useful instance is word "parent directory".

The GHDB (Google Hacking Databse) contains multitudes of creative searches that demonstrate the power of creative searching with combined operators.

Link (GHDB) :- [https://www.exploit-db.com/google-hacking-database](https://www.exploit-db.com/google-hacking-database)

## 6.4 Netcraft
Offers site reports.
Link : [https://searchdns.netcraft.com/](https://searchdns.netcraft.com/)

## 6.5 Recon-ng
Recon-ng is a module based framework for web-based information gathering. Recon-ng displays the results of a module to the terminal but it also stores them in databse.

`recon-ng`

Creating Workspace - Very useful when inheriting different module results.

![alt text](https://github.com/NashoNightmare/OSCP-Notes/blob/master/recon-ng0.png)

Searching and installing modules

![alt text](https://github.com/NashoNightmare/OSCP-Notes/blob/master/recon-ng1.png)

Loading and executing modules

![alt text](https://github.com/NashoNightmare/OSCP-Notes/blob/master/recon-ng2.png)

To view stored data

![alt text](https://github.com/NashoNightmare/OSCP-Notes/blob/master/recon-ng3.png)

![alt text](https://github.com/NashoNightmare/OSCP-Notes/blob/master/recon-ng4.png)

## 6.6 Open Source Code
Looking up for the openly available source codes in specific companies. 

- GitHub
- GitLab
- SourceForge

## 6.7 Shodan
Is a search engine that crawls devices connected to internet including but not limited to the World Wide Web. This includes the servers that run websites but also devices like routers and IoT devices.

Link : [www.shodan.io](https://www.shodan.io/)

## 6.8 Security Header Scanner
There are several other specialty websites that we can use to gather information about a website or domain’s security posture. Some of these sites blur the line between passive and active information gathering, but the key point for our purposes is that a third-party is initiating any scans or checks.

Link : [https://securityheaders.com/](https://securityheaders.com/)

## 6.9 SSL Server Test
This tool analyzes a server’s SSL/TLS configuration and compares it against current best practices.

Link : [https://www.ssllabs.com/ssltest/](https://www.ssllabs.com/ssltest/)

## 6.10 Pastebin
A pastebin or text storage site is a type of online content hosting service where users can store plain text, e.g. to source code snippets for code review.

Link : [https://pastebin.com/](https://pastebin.com/)

## 6.11 Email Harvesting
Gathers emails, names, subdomains, IPs, and URLs from multiple public data sources.

> `theHarvester -d <domain> -b google` - `-d`:Domain, `-b`:Data source to search

## 6.12 Social Searcher

Link : [https://www.social-searcher.com/](https://www.social-searcher.com/)

## 6.13 Use Forums
We can use forums and developer bases like Quora, StackOverFlow, Dev.to to tackle down employees by Social engineering them.

## 6.14 Information Gathering Frameworks
- OSINT Framework - Online available well-ordered OSINT tools and resources collection.
	Link : [https://osintframework.com/](https://osintframework.com/)
- Maltego - Combination of searching tools and strategies.
	Available with kali linux and freely available community edition that needs registration.

## 6.15 WiGLE (Wireless Geogrphic Logging Engine)
WiGLE is a website for collecting information abou the different wireless hotspots around the world. Users can register on the website and upload hotspot data like GPS coordinates, SSID, MAC(BSSID) and the encryption type used on the hotspots discovered.

Link : [https://wigle.net/](https://wigle.net/)

## 6.15 Wayback Machine
The Wayback Machine is a digital archive of the World Wide Web, founded by the Internet Archive, a nonprofit library based in San Francisco. It allows the user to go “back in time” and see what websites looked like in the past.

Link: [https://archive.org/web/](https://archive.org/web/)
