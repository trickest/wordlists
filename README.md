<h1 align="center">Wordlists <a href="https://twitter.com/intent/tweet?text=Wordlists%20-%20Real-world%20infosec%20wordlists%2C%20updated%20regularly%20by%20%40trick3st%0A%0Ahttps%3A%2F%2Fgithub.com%2Ftrickest%2Fwordlists&hashtags=bugbounty,bugbountytips,infosec"><img src="https://img.shields.io/badge/Tweet--lightgrey?logo=twitter&style=social" alt="Tweet" height="20"/></a></h1>
<h3 align="center">Real-world infosec wordlists, updated regularly</h3>

![Trickest Wordlists](images/cover.png "Trickest Wordlists")
## Current Wordlists
### Technologies
These wordlists are based on the source code of the CMSes/servers/frameworks listed [here](technology-repositories.json). The current wordlists include:
- Wordpress
- Joomla
- Drupal
- Magento
- Ghost
- Tomcat

There are 2 versions of each wordlist:
- Base (example [tomcat.txt](technologies/tomcat.txt)): Lists the full paths of each file in the repository
```
webapps/examples/WEB-INF/classes/websocket/echo/servers.json
```
- All levels (example [tomcat-all-levels.txt](technologies/tomcat-all-levels.txt)): Includes all directory levels of the files in the base wordlist - if you have tried [dsieve](https://github.com/trickest/dsieve), this is going to look familiar! This wordlist will be larger than the base wordlist but it accounts for cases where the directory structure of the repository isn't mapped perfectly on the target.
```
webapps/examples/WEB-INF/classes/websocket/echo/servers.json
examples/WEB-INF/classes/websocket/echo/servers.json
WEB-INF/classes/websocket/echo/servers.json
websocket/echo/servers.json
echo/servers.json
servers.json
```

### Robots
Inspired by Daniel Miessler's [RobotsDisallowed](https://github.com/danielmiessler/RobotsDisallowed) project, these wordlists contain the `robots.txt` `Allow` and `Disallow` paths in the top 100, top 1000, and top 10000 websites according to [Domcop's Open PageRank dataset](https://www.domcop.com/top-10-million-websites).

### Inventory Subdomains
This wordlist contains the subdomains found for each target on the [Inventory](https://github.com/trickest/inventory) project. It consists of 1.4 million words generated from the subdomains of over 50 public bug bounty programs.

### Cloud Subdomains
This wordlist contains the subdomains found through enumerating [cloud](https://github.com/trickest/cloud) assets. It consists of 940k words generated from the subdomains extracted from the `Common Name`s and `Subject Alternative Name`s of over 7 million SSL certificates.

And more wordlists to come!

## How it Works
### Technologies
A [Trickest](https://trickest.com) workflow clones the repositories in [technology-repositories.json](technology-repositories.json), lists the paths of all their files, removes non-interesting files, generates combinations, and pushes the wordlists to this repository.
![Trickest Workflow](images/technologies.png "Trickest Workflow - wordlists/technolgies")

### Robots
Another [Trickest](https://trickest.com) workflow gets the top 100, 1000, and 10000 websites from [Domcop's Open PageRank dataset](https://www.domcop.com/top-10-million-websites), uses [meg](https://github.com/tomnomnom/meg) to fetch their `robots.txt` files (Thanks, [@tomnomnom](https://github.com/tomnomnom)!), removes irrelevant entries, cleans up the paths, and pushes the wordlists to this repository.
![Trickest Workflow](images/robots.png "Trickest Workflow - wordlists/robots")

## Contribution
All contributions/suggestions/questions are welcome! Feel free to create a new ticket via [GitHub issues](https://github.com/trickest/wordlists/issues), tweet at us [@trick3st](https://twitter.com/trick3st), or join the conversation on [Discord](https://discord.gg/7HZmFYTGcQ).

## Build your own workflows!
We believe in the value of tinkering. Sign up for a demo on [trickest.com](https://trickest.com) to customize this workflow to your use case, get access to many more workflows, or build your own from scratch!

[<img src="./banner.png" />](https://trickest.io/auth/register)
