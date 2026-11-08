# The Cybrarians November Challenge: Office Network (VLANs)

*Prepared by Kareem, The Cybrarians*

## Overview

In October you built a basic topology. This month you level up: build a small office network with two separate departments (Staff and Guests), make them talk through a router, then lock Guests out of Staff resources.

- **Tool:** Cisco Packet Tracer (free)
- **Difficulty:** Beginner to Intermediate
- **Deadline:** 28th of November 

## What You Will Build

- 1 router
- 2 switches connected by a trunk link
- VLAN 10 (Staff): 6 to 7 PCs, split across both switches
- VLAN 20 (Guests): 6 to 7 PCs or laptops, split across both switches
- 1 server (web/DNS) in the Staff VLAN

## Suggested IP Plan

| Item | VLAN | Network | Gateway |
|---|---|---|---|
| Staff | 10 | 192.168.10.0/24 | 192.168.10.1 |
| Guests | 20 | 192.168.20.0/24 | 192.168.20.1 |
| Server | 10 | 192.168.10.100 (static) | 192.168.10.1 |

Exclude the server's address from the Staff DHCP pool.

## Tasks

1. **VLANs:** Create and name VLAN 10 (Staff) and VLAN 20 (Guests) on both switches. Assign access ports to the right VLANs.
2. **Trunk:** Configure the link between the two switches as a trunk.
3. **Inter-VLAN routing:** Set up router-on-a-stick using subinterfaces on the router.
4. **DHCP:** Configure DHCP on the router so every PC gets an IP automatically, with the correct gateway for its VLAN.
5. **ACL:** Guests must reach their own gateway but must NOT reach Staff devices or the server. Staff must still reach everything.
6. **Bonus:** Enable port security on the access ports, and set a login password on both switches.

## Scoring (100 points)

| Section | Points |
|---|---|
| VLANs and trunk | 20 |
| Inter-VLAN routing | 20 |
| DHCP working | 20 |
| ACL | 25 |
| Bonus (port security + switch passwords) | 15 |

Neatness counts: label devices clearly (e.g., Staff-PC1, Guest-PC1, SW1, SW2, R1, Server).

## Proof Required

Take these screenshots inside Packet Tracer:

1. `staff_ping_success.png`: a Staff PC successfully pinging the server
2. `guest_ping_fail.png`: a Guest PC failing to ping the server
3. `dhcp_proof.png`: any PC showing an automatically assigned IP (use `ipconfig`)

## Submission on GitHub

You will submit through a public GitHub repository. No Git commands needed, the browser is enough.

### Step 1: Create an account
Go to github.com and sign up for free (skip if you already have one).

### Step 2: Create the repository
1. Click **New repository**
2. Name it exactly: `cybrarians-nov-challenge`
3. Set it to **Public**
4. Tick **Add a README file**
5. Click **Create repository**

### Step 3: Name your files
- Packet Tracer file: `FullName_VLAN_Challenge.pkt` (example: `Aremu_Kareem_VLAN_Challenge.pkt`)
- Screenshots: the three names listed above

### Step 4: Upload your files
1. In your repo, click **Add file**, then **Upload files**
2. Drag in the `.pkt` file and the three screenshots
3. Click **Commit changes**

### Step 5: Edit the README
1. Click `README.md`, then the pencil icon (Edit)
2. Replace everything with the template below and fill it in
3. Click **Commit changes**

### Step 6: Send your link
Send your repo link to Kareem before the deadline. It should look like:

`https://github.com/your-username/cybrarians-nov-challenge`

Your deadline is judged by the time of your last commit on GitHub, so do not edit the repo after submitting.

## README Template

Copy and paste this into your README.md, then fill in the blanks:

```markdown
# Cybrarians November Challenge: Office Network (VLANs)

**Name:**
**Department/Level:**
**Date submitted:**

## What I Built
Short description of my network (number of PCs per VLAN,
switches, router):

## Tasks Completed
- [ ] VLANs created and ports assigned
- [ ] Trunk between switches
- [ ] Router-on-a-stick (inter-VLAN routing)
- [ ] DHCP for both VLANs
- [ ] ACL blocking Guests from Staff and the server
- [ ] Bonus: port security
- [ ] Bonus: switch login passwords

## IP Plan
| VLAN | Network | Gateway |
|---|---|---|
| 10 Staff | | |
| 20 Guests | | |

## Proof
### Staff pinging the server (success)
![Staff ping success](staff_ping_success.png)

### Guest pinging the server (blocked)
![Guest ping fail](guest_ping_fail.png)

### DHCP working
![DHCP proof](dhcp_proof.png)

## Challenges I Faced
One or two lines on what was hard and how I solved it.

## Files
- FullName_VLAN_Challenge.pkt
```

## Rules

- Work individually.
- Use only Cisco Packet Tracer.
- Late or incomplete submissions (missing `.pkt` file or screenshots) lose points.
- Questions? Ask in the community group.

Good luck, Cybrarians!
