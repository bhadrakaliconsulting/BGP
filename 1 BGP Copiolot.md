SLIDE 1
ఈ రోజు మనం నేర్చుకునే విషయాలు:

BGP అంటే ఏమిటి?

BGP చరిత్ర

BGP-1 నుండి BGP-4 వరకు

IGP vs BGP — తేడా ఏమిటి?

Autonomous Systems concept

AS Numbers — Public, Private

2-byte AS మరియు 4-byte AS అర్థం

SLIDE 2
మీరు Google లో search చేసినప్పుడు… Amazon లో order చేసినప్పుడు… WhatsApp message పంపినప్పుడు…
ఆ data, ఆ packet — Hyderabad నుండి America లో ఉన్న Google server కి ఎలా వెళ్తుంది?
జవాబు: BGP!

👉 BGP లేకపోతే — Internet పూర్తిగా ఆగిపోతుంది. ఒక్క రోజు BGP fail అయితే — లక్షల websites unreachable అవుతాయి.
అంత ముఖ్యమైన protocol ఇదే.

ఈ video చివరికి మీరు — BGP ని confidently explain చేయగలరు.

SLIDE 3
BGP అంటే ఏమిటి?  
BGP — Border Gateway Protocol. ఇది Internet యొక్క ప్రధాన routing protocol.

Post Office example తో అర్థం చేసుకుందాం:
🏪 Hyderabad నుండి Mumbai కి letter పంపాలంటే — మీరు Post Office కి వెళ్తారు. Post Office వాళ్లు best route ఎంచుకుంటారు.
అదే విధంగా BGP — Internet లో packets కి best route ఎంచుకుంటుంది.

👉 Technical details:

BGP ఒక Path Vector Protocol — routes ని path information తో share చేస్తుంది.

Example (AS Path): Hyderabad లో ఉన్న Airtel ISP (AS9498) కి Google server (AS15169) కి వెళ్లే మార్గం తెలుసు.
Airtel advertise చేసిన path ఇలా ఉంటుంది:
AS9498 → AS55836 (Jio) → AS16509 (Amazon) → AS15169 (Google)

Neighbor routers ఈ path ని note చేసుకుంటాయి.

ఇప్పుడు Hyderabad నుండి Google కి packet పంపితే, అది ఈ AS sequence follow చేస్తుంది.

Distance మాత్రమే చెప్పే protocols (RIP లాంటి) కంటే, BGP path details (AS numbers list) కూడా share చేస్తుంది.
👉 అందుకే loops prevent అవుతాయి, మరియు ISPs తమ business policies apply చేయగలుగుతారు.

TCP Port 179 ఉపయోగిస్తుంది — reliable connection కోసం

Current standard: BGP-4

Internet లో 9,00,000+ routes ఉన్నాయి

ISPs, Cloud providers, Enterprises అన్నీ BGP వాడుతున్నాయి

📌 BGP లేకపోతే Internet పని చేయదు!

SLIDE 4
BGP చరిత్ర  
1989 లో మొదలైంది.

ఒక dinner meeting లో Kirk Lougheed మరియు Yakov Rekhter — 3 napkins మీద protocol design చేశారు! అందుకే దీనిని Three-Napkin Protocol అంటారు.

Timeline:

BGP-1 (1989) — Initial version. Weekend లో Internet ని save చేయడానికి create చేశారు

BGP-2 (1990) — Improvements, loop prevention

BGP-3 (1991) — Route filtering, ISPs adopt చేశారు

BGP-4 (1995) — Current version. CIDR support, 4-byte AS numbers. 9 లక్షల routes handle చేస్తుంది

👉 30+ years నుండి Internet ని run చేస్తున్న stable version ఇదే!

SLIDE 5
IGPs ఎందుకు Internet కి సరిపోవు?  
OSPF, EIGRP — ఇవి company/campus లో బాగుంటాయి. కానీ Internet కి fail అవుతాయి.

కారణాలు:

Scale Problem — OSPF max 50–100 routers. Internet లో 9,00,000+ routes ఉన్నాయి. Crash అవుతుంది!

Multiple Organizations — OSPF ఒకే trust domain లో పని చేస్తుంది. Airtel, Jio వేర్వేరు companies.

Policy Control లేదు — OSPF fastest path మాత్రమే choose చేస్తుంది. ISPs కి business policies అవసరం.

Convergence Slow — Large networks లో OSPF convergence slow. Internet scale కి తట్టుకోదు.

📌 అందుకే BGP design చేశారు — scalable, policy-based, multi-organization routing!

SLIDE 6
Comparison Table: BGP vs OSPF vs EIGRP

BGP — Path Vector Protocol. Different AS మధ్య పని చేస్తుంది. 9 లక్షల routes handle చేస్తుంది. TCP Port 179. Policy control flexible.

OSPF — Link State Protocol. Same AS లోపల. Max ~500 routers. Fast convergence కానీ policy control limited.

EIGRP — Cisco Hybrid Protocol. Same AS లోపల. ~250 routers. Very fast convergence కానీ Cisco proprietary.

📌 Simple rule: Company network లో OSPF/EIGRP. Internet మీద BGP.

SLIDE 7
BGP Usage — Real World Examples

Internet Backbone — worldwide backbone routing protocol

ISP Networks — Airtel, Jio, BSNL అన్నీ BGP వాడతాయి

Enterprise Multi-homing — redundancy కోసం 2 ISPs connect చేస్తారు

Cloud Providers — AWS Direct Connect, Azure ExpressRoute, GCP Interconnect అన్నీ BGP మీద run అవుతాయి

SLIDE 8
Autonomous System (AS) అంటే ఏమిటి?  
Country example తో అర్థం చేసుకుందాం:
🏙️ ప్రతి country independent గా ruling ఉంటుంది. Countries మధ్య roads ఉంటాయి.
అదే విధంగా — AS అంటే ఒక organization network. BGP అంటే countries మధ్య roads లాంటిది.

Official definition:
AS అంటే ఒక organization లేదా ISP network — ఒకే routing policy కింద manage అవుతుంది.

📌 Real examples: Airtel India AS 9498, Jio AS 55836, Google, Amazon ASNs.

SLIDE 9
AS Numbers అంటే ఏమిటి?  
ప్రతి AS కి unique number ఉంటుంది — ASN. India కి phone code +91 ఉన్నట్లే.

2-byte ASNs: Range 0–65535

1–64511 Public

64512–65534 Private

4-byte ASNs: Range 0–4.2 billion (2009 నుండి)

📌 Real examples: Google AS 15169, Amazon AS 16509
📌 Private ASNs Internet లో advertise చేయకూడదు — labs/testing లో మాత్రమే.

SLIDE 10
ఈ chapter లో నేర్చుకున్నవి:

BGP అంటే ఏమిటి

TCP Port 179

BGP చరిత్ర — 1989 నుండి BGP-4 వరకు

IGP limitations — scale, multi-org, policy issues

BGP vs IGP

BGP Usage — Internet, ISPs, Enterprise, Cloud

AS concept

AS Numbers — 2-byte, 4-byte, Public & Private

SLIDE 11 (Closing)
Chapter 1 complete! 🎉
మీరు ఇప్పుడు Internet backbone ని అర్థం చేసుకున్నారు.

👉 Next video: Chapter 1 Lab — EVE-ng లో BGP Basic Setup! Real routers, real config, real verification.

Closing line:  
“మీరు ఇప్పుడు Internet యొక్క secret language నేర్చుకోవడం మొదలుపెట్టారు. See you in the next video!” 🙏
