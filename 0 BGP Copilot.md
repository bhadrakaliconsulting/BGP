📜 BGP Chapter 2 — Modern Telugu Script

Presenter: Kali | Duration: 7–15 Minutes | Format: Screen Share + Slides

🎬 Introduction (Slides 1–2)

🖥️ SLIDE 1 — Title

[Screen: BGP Chapter 2 Telugu Title Slide — "BGP Fundamentals" కనిపిస్తోంది]

[SCRIPT — INTRODUCTION]

హాయ్ అందరికీ! 👋

నేను Kali — మీకు Telugu లో BGP నేర్పించే instructor!

మన BGP Complete Learning Series లో ఇవాళ మనం Chapter 2 — BGP Fundamentals start చేస్తున్నాం.

Chapter 1 లో మనం BGP అంటే ఏమిటి, Autonomous Systems, AS Numbers — అన్నీ చూశాం.

ఇప్పుడు Chapter 2 లో BGP ఎలా work అవుతుందో concept level లో చూద్దాం.

ఈ వీడియోలో మనం నేర్చుకునేది:

BGP Path Vector Protocol అంటే ఏమిటి

BGP Speaker మరియు Router types

iBGP vs eBGP — key differences

TCP Port 179 session

BGP Neighbor concept

BGP Tables — RIB, Adj-RIB-In, Loc-RIB

NLRI — route announcement

7 topics — ఒక్కోటి real-life examples తో నేర్చుకుంటాం!

వీడియో చివరికి మీకు BGP fundamentals పూర్తిగా clear అవుతాయి — guarantee!

🖥️ SLIDE 2 — What We'll Learn

[Screen: Curiosity question + 3 learning cards కనిపిస్తున్నాయి]

[SCRIPT — HOOK]

ముందుగా ఒక question:

"మీరు కర్నూల్ నుండి WhatsApp message పంపితే — అది ముంబై server కి ఎలా చేరుతుంది?"

ఇది magic కాదు — ఇది BGP!

BGP ఆ data packet కి roadmap చూపిస్తుంది.

ఇవాళ మనం నేర్చుకునేది:

BGP ఎలా work అవుతుందో — concept level లో

Neighbors ఎలా form అవుతాయో — technical గా

BGP Tables data ని ఎలా store చేస్తాయో — practical గా

📚 Body Section (Slides 3–9)

🖥️ SLIDE 3 — 2.1 BGP Path Vector Protocol

[SCRIPT — 2.1 PATH VECTOR]

Protocols మూడు types:

Distance Vector — RIP, EIGRP — hop count మాత్రమే చూస్తాయి.

Link State — OSPF, IS-IS — full topology map build చేస్తాయి.

BGP — Path Vector — ఇది unique! AS_PATH తో పాటు మార్గం మొత్తం చూపిస్తుంది.

Example — Post Office:

Distance Vector: "3 cities దాటాను". Path Vector: "కర్నూల్ → హైదరాబాద్ → పుణే → ముంబై".

AS_PATH = [AS65001 → AS65002 → AS65003]

Benefits:

Loop prevention — స్వంత AS ఉంటే reject చేస్తుంది.

Policy decisions — shorter path choose చేయవచ్చు.

🖥️ SLIDE 4 — 2.2 BGP Speaker & Router Types

[SCRIPT — 2.2 SPEAKER]

BGP Speaker = BGP run చేసే router.

Router-ID = unique ID (usually Loopback IP).

Router Types:

Edge Router — AS border లో eBGP

Internal Router — AS లోపల iBGP

Route Reflector — iBGP routes re-advertise చేస్తుంది

ASBR — eBGP + iBGP రెండూ

PE Router — MPLS Provider Edge

🖥️ SLIDE 5 — 2.3 iBGP vs eBGP

[SCRIPT — 2.3 iBGP vs eBGP]

iBGP — Internal BGP:

ఒకే AS లోపల

Admin Distance = 200

TTL = 255

NEXT_HOP change చేయదు

Full Mesh అవసరం

eBGP — External BGP:

వేర్వేరు AS మధ్య

Admin Distance = 20

TTL = 1

NEXT_HOP = peer IP

AS_PATH లో own AS add చేస్తుంది

🖥️ SLIDE 6 — 2.4 TCP Port 179

[SCRIPT — 2.4 TCP]

BGP TCP Port 179 వాడుతుంది.

ఎందుకు TCP?

UDP reliable కాదు.

TCP — reliable, ordered delivery.

TCP 3-Way Handshake:

SYN

SYN-ACK

ACK

Timers:

Hold Timer = 90s

Keepalive = 30s

🖥️ SLIDE 7 — 2.5 BGP Neighbor

[SCRIPT — 2.5 NEIGHBOR]

OSPF neighbors auto-discover అవుతాయి. BGP neighbors manual configure చేయాలి.

router bgp 65001
 neighbor 192.168.1.2 remote-as 65002

Mandatory: IP + Remote-AS.

🖥️ SLIDE 8 — 2.6 BGP Tables

[SCRIPT — 2.6 TABLES]

BGP 4 tables:

Adj-RIB-In — inbound routes

Decision Process — best path selection

Loc-RIB — main table

Adj-RIB-Out — outbound routes

🖥️ SLIDE 9 — 2.7 BGP NLRI

[SCRIPT — 2.7 NLRI]

NLRI = Network Layer Reachability Information.

Format: (Length, Prefix).

Example: 192.168.10.0/24.

UPDATE message లో:

NLRI field — new routes

Withdrawn field — removed routes

🖥️ SLIDE 10 — Summary

[SCRIPT — SUMMARY]

Path Vector — AS_PATH తో

BGP Speaker — Router-ID

iBGP vs eBGP — AD 200 vs 20

TCP Port 179 — reliable

Neighbors — manual config

Tables — Adj-RIB-In → Loc-RIB → Adj-RIB-Out

NLRI — Prefix + Length

📣 Call to Action

ఈ వీడియో useful గా అనిపిస్తే:

👍 Like చేయండి 🔔 Subscribe చేయండి 💬 Comments లో doubts అడగండి 📤 Share చేయండి

Next Video: Chapter 3 — BGP Message Types!
