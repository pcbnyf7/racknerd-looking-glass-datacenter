# RackNerd Looking Glass: Which Datacenter Should You Test, What Ping Is Good Enough, and Which Plan Do You Buy Afterward? (Full Location List + Pricing Tables)

RackNerd's Looking Glass is a free web page running at each of its datacenters. You pick a location, run ping, traceroute or MTR against your own IP, and pull a 10MB, 100MB or 1GB test file to see how that facility actually reaches you. No account, no email, no checkout. Five minutes of testing two or three candidate locations is a better guide than a map, because carrier choice and peering regularly beat geography.

If you only test three, test **Los Angeles DC-02**, **San Jose**, and one East Coast site (Ashburn or New Jersey). Asia-Pacific traffic usually wins on the West Coast, European traffic usually lands better on the East Coast, and the numbers will tell you which one is true for your connection.

> **Short version:** Test first, then buy. For most side projects the **2 GB special at $35.99/yr** is the sensible default; a static page, a personal WireGuard tunnel or a monitoring agent runs fine on the **1 GB at $21.99/yr**. RackNerd does not offer refunds, so the five minutes you spend on the Looking Glass is the only real trial you get.
> 👉 [Open RackNerd and check what's currently in stock](https://bit.ly/RacKnerd)

## The plans, side by side

Two product lines: the annual specials, which are the cheap ones, and the standard KVM line billed monthly. Every plan below includes one dedicated IPv4, full root access, a 1Gbps port and a choice of locations.

**Annual KVM specials**

| Plan | SSD (RAID-10) | Monthly transfer | vCPU | Price | Order |
| --- | --- | --- | --- | --- | --- |
| 1 GB Special | 20 GB | 3 TB | 1 core | $21.99/yr | [ 1 GB special](https://bit.ly/RacKnerd) |
| 2 GB Special | 35 GB | 5 TB | 2 cores | $35.99/yr | [ 2 GB special](https://bit.ly/RacKnerd) |
| 4 GB Special | 60 GB | 7 TB | 3 cores | $59.99/yr | [ 4 GB special](https://bit.ly/RacKnerd) |
| 6 GB Special | 100 GB | 12 TB | 6 cores | $89.99/yr | [ 6 GB special](https://bit.ly/RacKnerd) |
| 8 GB Special | 150 GB | 20 TB | 7 cores | $119.99/yr | [ 8 GB special](https://bit.ly/RacKnerd) |

**Standard KVM line**

| Plan | SSD (RAID-10) | Monthly transfer | vCPU | Price | Order |
| --- | --- | --- | --- | --- | --- |
| 512 MB | 30 GB | 500 GB | 1 vCore | $26.99/yr (annual billing) | [ 512 MB plan](https://bit.ly/RacKnerd) |
| 1 GB | 50 GB | 1 TB | 2 vCores | $17.99/mo | [ 1 GB monthly](https://bit.ly/RacKnerd) |
| 2 GB | 75 GB | 2 TB | 3 vCores | $20.59/mo | [ 2 GB monthly](https://bit.ly/RacKnerd) |
| 4 GB | 130 GB | 3 TB | 4 vCores | $24.59/mo | [ 4 GB monthly](https://bit.ly/RacKnerd) |
| 6 GB | 170 GB | 4 TB | 5 vCores | $27.59/mo | [ 6 GB monthly](https://bit.ly/RacKnerd) |
| 8 GB | 220 GB | 5 TB | 6 vCores | $36.59/mo | [ 8 GB monthly](https://bit.ly/RacKnerd) |
| 12 GB | 300 GB | 6 TB | 7 vCores | $55.99/mo | [ 12 GB monthly](https://bit.ly/RacKnerd) |

Two things worth flagging in those tables. The 512 MB row is billed yearly despite sitting in the monthly lineup, so it is not the cheapest way in: the 1 GB special at $21.99/yr works out around $1.83 a month, less than the 512 MB at $26.99/yr. And the transfer column is a monthly quota, not an unlimited allowance; the plan pages don't spell out whether overages are billed or throttled, so ask if you expect to push serious traffic.

Prices move. Treat the number in the cart as the real one, and check it against the table above before you pay.

## What a Looking Glass gives you that a test IP does not

Most hosts hand out a test IP and maybe a test file. That measures one direction: you to the server. RackNerd's own explainer on the tool makes the distinction directly: *"With a Looking Glass, you can now test from both directions to get an accurate idea of latency, network routes/paths, and speeds."*

That matters because return paths are not always the mirror of outbound paths. A traceroute you run from your laptop shows how your packets get to the datacenter. A traceroute run from the panel shows how packets get back to you. On a badly peered route those two can diverge enough that a ping average alone hides the problem. Running both directions is how you catch it before you commit to a year of hosting.

The panel itself is plain. You get the server location, the test IPv4, three file sizes, a field that fills in your public IP, and ping / traceroute / MTR. A dropdown in the header switches datacenters, so you don't need to keep twenty tabs open.

## Five minutes, six steps

1. Open any location's Looking Glass page and start with the site you think is closest.
2. Click the button under the IP field to fill in your current public address. You can also paste any public IPv4 you want to test against.
3. Run **Ping** and note the average round trip in milliseconds.
4. Switch locations with the dropdown and repeat for two or three more sites. Write the averages down next to each other.
5. If a result is much worse than you expected, switch to **MTR**. It combines ping and traceroute into a live test and shows packet loss per hop, which points at the hop where things go wrong instead of just telling you they did.
6. Pull the **100MB** file from your best candidate and time it. 100 divided by the seconds gives you real throughput in MB/s. The 1GB file is only worth the wait on a fast connection.

## How to read the numbers

The thresholds below are rules of thumb, not anything RackNerd publishes as a guarantee:

- **Under 50ms** feels instant for interactive work.
- **50 to 100ms** is fine for most websites and non-interactive workloads.
- **Over 150ms** starts to feel sluggish when you're typing into a shell or clicking through a control panel.

Ignore small differences. Five milliseconds between two locations is invisible to anyone visiting your site. A 70ms difference is not, and that is the size of mistake the tool exists to prevent. Pick the lowest reasonable number, weigh price and whether the location has stock, and stop testing.

## All locations and their test IPs

The list below covers the 22 locations named in the most complete public reference for the tool. RackNerd's status page counts 20 data centres, so the total depends on how facilities are grouped. The location dropdown on any Looking Glass page is the live authority if a name here doesn't appear.

**North America**

| Location | Looking Glass | Test IPv4 |
| --- | --- | --- |
| Los Angeles, CA (DC-02) | lg-lax02.racknerd.com | 204.13.154.3 |
| Los Angeles, CA (DC-03) | lg-lax03.racknerd.com | — |
| Los Angeles, CA (DC-05) | lg-lax05.racknerd.com | 5.181.135.8 |
| San Jose, CA | lg-sj.racknerd.com | — |
| Seattle, WA | lg-sea.racknerd.com | 192.3.253.2 |
| Utah | lg-ut.racknerd.com | — |
| Dallas, TX | lg-dal.racknerd.com | — |
| Chicago, IL | lg-chi.racknerd.com | — |
| New York, NY | lg-ny.racknerd.com | — |
| New Jersey | lg-nj.racknerd.com | 192.3.165.30 |
| Ashburn, VA | lg-ash.racknerd.com | — |
| Atlanta, GA | lg-atl.racknerd.com | 107.173.164.160 |
| Tampa, FL | lg-tpa.racknerd.com | — |
| Miami, FL | lg-mia.racknerd.com | — |
| Montreal, QC | lg-mtl.racknerd.com | — |
| Toronto, ON | lg-tor.racknerd.com | — |

**Europe and Asia**

| Location | Looking Glass | Test IPv4 |
| --- | --- | --- |
| London, UK | lg-lon.racknerd.com | — |
| Amsterdam, NL | lg-ams.racknerd.com | — |
| Strasbourg, FR | lg-fr.racknerd.com | — |
| Frankfurt, DE | lg-fra.racknerd.com | — |
| Dublin, IE | lg-dub.racknerd.com | — |
| Singapore | lg-sg.racknerd.com | — |

Blank IPs mean the location is listed but its test address isn't published in the reference tables; open the page and read the address off it. This is also where most guides go stale. A 2020 RackNerd post advertises **Los Angeles DC-01**, which no longer appears on the current list, and several third-party tables leave Atlanta's IP empty even though the page has shown one for a while. If a list and the panel disagree, believe the panel.

## Which location for where you are

Once you have four ping numbers, a rough direction helps you choose which two to compare properly:

- **Southeast Asia buying a US VPS.** LA DC-02 and San Jose first. West Coast routing to Asia-Pacific is generally the strongest, and DC-02 has a long record of solid China-bound routes.
- **Europe buying a US VPS.** Ashburn, New York, New Jersey. Western Europe to the East Coast typically lands somewhere around 70 to 90ms on a decent path, which is workable for non-interactive workloads.
- **Australia or New Zealand.** Los Angeles or San Jose, and don't spend long on it. Both usually come in around 140 to 160ms, and the East Coast is worse.
- **US host serving European visitors.** Test Amsterdam, Dublin and Strasbourg. Dublin is the newest of the three and sometimes has better capacity.
- **China.** LA DC-02 is the conventional pick. Run MTR between 18:00 and 22:00 local time, because that's when the route actually matters and when a mediocre path shows itself.
- **Native IPv6 needed.** Los Angeles and the France location (Strasbourg) support it; up to 100 addresses are available on request via a support ticket after you order. Elsewhere, confirm before you buy.

## Three things the test cannot tell you

**How loaded your specific host will be.** The Looking Glass runs on the network edge of the datacenter. It says nothing about whether the physical machine your VPS lands on is oversubscribed. A perfect ping and a noisy neighbour can coexist.

**How traffic reaches a specific ISP.** It shows the path to the IP you typed in. If your audience is spread across a dozen networks, one test tells you about one of them.

**How IPv6 behaves.** The panel is IPv4-first. IPv6 is allocated on request in two locations, and you can only test that path after the VPS is live.

## Can you move to another datacenter after ordering?

Not from the control panel. You open a support ticket and ask for a migration, and it depends on capacity at the target location. There's no guarantee it will be approved. That is the whole argument for testing before checkout rather than planning to fix it afterwards.

## Matching the plan to what you're running

- **1 GB special, $21.99/yr.** A personal blog, a low-traffic static site, your own WireGuard endpoint, a bot, a monitoring agent. Not a WordPress install with caching plugins under real load.
- **2 GB special, $35.99/yr.** Small WordPress with caching, a Nextcloud instance for one person, a Minecraft server for a few friends, a lightweight Node app. The tier most people should start with.
- **4 GB special, $59.99/yr.** Where a lot of buyers end up staying. Three vCPUs make a visible difference once anything runs concurrently: a small business site, a game server past twenty players, a handful of Docker containers.
- **6 GB and 8 GB specials.** Multiple services on one box, multi-user VPN, a development environment.
- **Standard monthly, 6 GB and up.** Production workloads that want predictable headroom and no annual commitment.

A note on the control panel: older write-ups describe SolusVM. RackNerd's current VPS pages describe **ctrl**, which covers reboot, OS reinstall, an HTML5 VNC console, root password reset, firewall rules and one-click installs for things like Docker with Portainer, Coolify, n8n and Ollama. The instances are unmanaged, so root access and your own stack is the assumption.

👉 [Compare the annual specials against the monthly line](https://bit.ly/RacKnerd)

## FAQ

**Does it cost anything?** No. No account, no email, no card.

**Can I test an IP that isn't mine?** Yes. Paste any public IPv4, which is useful for checking a colleague's connection or a region where your users actually are.

**Do all locations have one?** Every active location has its own page, and the header dropdown lists them.

**Is IPv6 supported in the panel?** Mostly not. Test IPv4, and if you need IPv6, request it in Los Angeles or Strasbourg after deployment.

**How often should I retest?** Once a quarter is enough for most people. Routes change, and a path that was clean a year ago may not be.

**What if I don't like it?** RackNerd's knowledgebase states plainly that there are no refunds and no money-back guarantee. Assume the money is spent once you order.

**What can I pay with?** Major credit cards are confirmed; the knowledgebase lists the rest.

## Picking, in one line each

Static page or a tunnel: **1 GB special, $21.99/yr**. Small WordPress or personal cloud: **2 GB, $35.99/yr**. Anything with several moving parts or a handful of Docker containers: **4 GB, $59.99/yr**. Production traffic that needs headroom and no annual lock-in: **standard monthly, 6 GB or higher**.

Before you pay, confirm three things on the checkout page: the price actually charged for the plan you picked, that your tested datacenter is selectable for that plan, and whether you're on annual or monthly billing. Then run one last ping from your top two locations, pick the better number, and stop second-guessing it.

👉 [Start with the current RackNerd specials](https://bit.ly/RacKnerd)
