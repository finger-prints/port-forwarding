# Port Forwarding

## Context - IPv4
Port forwarding more or less exists because of the way IPv4 addresses work. IPv4
addresses are the ones you're probably used to seeing - `192.168.0.2`,
`8.8.8.8`, etc. An IPv4 address is composed of 4 bytes, with a byte being able
to store any number between 1-255. So the "first" IP address would be `0.0.0.0`,
and the "last" would be `255.255.255.255`.

Anyways, 4 bytes of address means that there are `256^4-1 = 4,294,967,295`
addresses total. However, there are reserved IP ranges, etc. that make the real
number less than that. 4 billion addresses is less than half the people on the
planet, so we need more IP addresses to allow for everyone having computers and
phones and iPads, etc (not to mention businesses like Amazon and Google having a
kajillion servers).

## NAT Routing
NAT (Network Address Table) routing is one of the solutions to this issue. The
idea is pretty simple: instead of giving every device one public IP address,
give a router a public IP address and all the 12 devices in a household will get
private IP addresses that only really matter inside the house.

![NAT Routing Diagram](https://wiki.teltonika-networks.com/view/Network_Address_Translation)

This is why addresses like `192.168.*.*` and `10.*.*.*` come up so often - these
are IP address spaces that are reserved for private use and usually used for
your household internet/wifi. `127.*.*.*` is also usually reserved for virtual
networking in your computer, with `127.0.0.1` being your computer.

So basically private addresses don't really mean anything outside of your
network. Everyone and their mother has the IP address `192.168.0.5`, so if
someone tries to connect to you with that address, they probably just tried to
connect to their own PC or smart TV.

## Port Forwarding
The "issue" with NAT routing is that now all the devices that want to talk to
your privately addressed PC can't - they can only talk to your router with a
public IP. So your router has to know that if it's getting connections on the
Minecraft port, those connections should be forwarded to your PC hosting a
Minecraft server.

## When to port forward
Any time you're hosting something that you want people outside of your network
(our WiFi) to connect to. The caveat is that a lot of times your
router/"gateway" is the one doing firewalling to make sure that random people
from who knows where aren't connecting to you.

### When not to port forward
Try not to port forward ports that you might not want random people
connecting to. If you download some random SIMS unlocker that wants you to
forward some ports, there's a good chance it's doing some real sketchy stuff.

Also it's just best practice to port forward as little as possible. If I forward
every router port to my PC, I'm letting anyone on the internet talk to anything
listening on my PC. AND then we can't port forward anything to anyone else's PC
because mine is getting all the traffic.

Ideally you port forward for your Minecraft server then un-port forward when
your server's not running.

## How to port forward
It depends entirely on your router/gateway. Generally nowadays your
AT&T/Xfinity/whatever routers are pretty standard, so you just connect to
`192.168.0.1` or `10.0.0.1` (whichever your router uses) on your browser and dig
around until you see an option for Port Forwarding. For us, it's a bit different
because I have my fancy network setup. I could probably make you an account,
which would make it basically the same if you want. But I have to look into
that. If you want specific things forwarded, I can do that ez pz. If you want an
account, lmk and I'll figure it out.
