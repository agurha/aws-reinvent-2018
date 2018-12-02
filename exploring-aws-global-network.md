# Behind the Scenes: Exploring the AWS Global Network

*this guy talked fast and monotone.. sleepy time*

- single-chip network platform
- simpler than large chassis devices
- all IP traffic so easy to debug
- Amazon contols OS deployed to routing units
- more devices causes more monitoring
- uniformity of devices paramount -- this allows ubiquitous monitoring
- uses geospatial attributes to enforce diverse pathing
- uses wavelength to send traffic at different frequences.. density bro
- "AWS GLobal Backbone" - 100GB fiber laid all around the world
- *all commercial traffic goes over backbone exception China*

# Edge POPs
- connect to the internet: transit centers, Edge POPs
- physically close to internet exchanges
- Direct Connect, Cloundfront, Route53, Shiled (DDoS protection) run INSIDE POP
- BGP = the internet control plane