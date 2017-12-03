# Off-the-Grid Internet Challenge

How can we leverage wireless technology to keep people connected to each other and to vital information sources in the aftermath of a disaster where Internet access is unavailable or compromised?

The [Off-the-Grid Internet Challenge](https://wirelesschallenge.mozilla.org/_assets/NSF-OffTheGrid.pdf) seeks solutions that can provide connectivity in one of the most challenging situations: the immediate aftermath of a major disaster. When disasters like earthquakes, tsunamis and hurricanes strike, communications networks are often among the first pieces of critical infrastructure to overload or fail, leaving individuals disconnected from one another and from essential services and communications. With a total of **$1M** in prize money, the Off-the-Grid Internet Challenge seeks solutions that help individuals wirelessly access each other and information services like maps and messaging following a disaster.

## Problem Statement
With stable infrastructure and poor communications outages from disasters, gathering information will be difficult further exacerbating the damage and loss of lives. Time is of the essence; without a concrete plan and solution to address the people affected by the disaster, responses are restricted to decisions made on the fly. More often than not, strategies to overcome these issues usually act as damage control serving as last minute efforts to salvage whatever can be saved. 

## Solution Statement 
Our solution consists of 3 parts: **`Named Data Networking (NDN)`**, **`modified routers`**, and a **`networking logistics`** tool. NDN, a development in network protocols, is key to our project. Providing enhanced security and faster browsing speeds over the existing TCP/IP protocol, it will achieve quick and reliable online access. The hardware leverages a low cost router to run NDN and establish a mesh-network on the fly. It will also include a battery to operate it. 

## Users
Telecommunication technologies has expanded quickly in the last decade as seen with the rise of 3G, 4G, LTE, free wireless zones, and the potential upcoming 5G network. However, many don’t realize how these telecommunications operate taking for granted our constant access to the rest of the world. The US has one of the most Internet cable connections in the world, leaving it virtually impossible for attackers to shutdown the entire country in a series of coordinated events **\[[1][1]]\[[2][2]]**. Though, the network is still vulnerable to smaller scale (i.e. Northeast) blackouts by accidental forces (i.e. car crashing into a telepole), unlikely but possible EMP attacks from adversaries, and especially natural disasters. This can pose a security problem and with little information to resolve affected areas, government agencies could be diverting relief sources ineffectively; thus, slowing down resolvement and putting civilians at greater risk. Therefore, the intent users applies to everyone, particularly those of low socioeconomic status, residing in high vulnerable zones (i.e. floodplains), and/or in active disaster zones (i.e. Puerto Rico). This solutions also covers cases with concerns regarding censorship and internet shutdown.

## Community / Location 
From earthquakes to blizzards to tornadoes and hurricanes, the United States has a wide range of natural disasters that can cost municipalities millions, occasionally billions of dollars **\[[3][3]]**, to rebuild. Depending on the impact of the natural disaster, repairing infrastructure (electricity and internet) can take a mere few hours to days, and sometimes weeks (i.e. 2008 Northeast Ice Storm **\[[4][4]]**). This can be found in many parts across the country; however, we decide to narrow down areas that are either currently damaged or very prone to high impact disasters (i.e. California). With that, we believe that Puerto Rico is the perfect location to implement our design due to its current state. Nearly two months since Hurricane Irma and Maria plowed through Puerto Rico, 70% of the island’s 3.4 million people (40% are poor **\[[5][5]]**) is still left without electricity **\[[6][6]]**, which includes no access to telecommunications **\[[7][7]]** and clean water. This leaves the territory in a major humanitarian crises. Reasons why it’s been painstaking slow to bring back power are due to outdated grid, "brain drain", bankrupt government, and its geography (isolated from the mainland and rough terrain). With that, this is an opportunity for us to apply an off-grid, robust telecom network. 

## Technical Feasibility

Our solution tackles off-grid and disaster recovery using a prevention first mindset. Buildings have fire extinguishers, medical kits, and AEDs for emergencies to prevent issues from getting worse rather than treating them in the aftermath. We envision that under dire circumstances people use our product to power their devices and establish an off-grid internet.

The physical product is essentially a box containing a router, small computer, power supply, antennae, and backup battery supply. We call our box ANTs (Alternative Network Transmission boxes). This will be our greatest technical hurdle as it requires much research and design to ensure maximized value in addition to overhead of testing hardware. To ensure continued internet access and notifications of blackouts, the ANT comes with a backup battery providing extra hours of power. ANTs can also connect with other ANTs forming a mesh network which can behave as a community based Wireless Internet Service Provider (WISP) on the fly. ANTs can serve as a router for homes/ buildings, however, we imagine that people will especially purchase them for insurance against disasters. Powering ANTs to run outside of homes will likely require plugging onto a nearby source of electricity (whether by on or off grid means). Manufacturing the case with aluminum will allow for cost effective, lightweight, and durable properties. Size will be somewhere between a WiFi router and a small shoebox.

Currently, research into desirable budget hardware running secure communications and NDN is being conducted. We are compiling a database of routing and processing hardware with information about performance, listings of supported software, cost, weight, and dimensions. With this information tradeoffs can be assessed finding the overall best value. The Raspberry Pi 3 (RPI3) is our current choice given its community support, hardware extendability, and security as it runs mainline Linux. It’ll also allow for logging internet speeds to determine sources of slowdowns/bottlenecking of the connection. Most importantly, the RPI3 can flash DD-WRT **\[[8][8]]**, OpenWRT **\[[9][9]]**, and the code running the NDN platform **\[[10][10]]\[[11][11]]\[[12][12]]**. Thus, removing the need of a router altogether provided the appropriate hardware is connected **\[[13][13]]**. The device will likely also sport 3 antenna ports to interface for different communications, notably; WiFi and 4G/ Cellular. 

With time being of the essence and an absence of infrastructure, it is critical for the item to be lightweight, portable, durable, and accessible to many from a reasonable range. Additionally, it must overcome data congestion issues prevalent in disasters. Furthermore, it must be able to transmit data quickly, resiliently, and, if possible, in a fault tolerant manner to prevent the loss of the data/ messages. While existing P2P/ Wireless Mesh Networks (WMNs) address the issue of maintaining a network **\[[14][14]]\[[15][15]]**, they often fall behind in range, speed, and reliability **\[[16][16]]**. To improve upon established systems, concerns regarding the etablishing of WMNs must be defined and considered carefully. Conceptually, as instituted by ISO (International Organization for Standardization), an ideal/ model network can be broken down into seven layers as described by OSI (Open Systems Interconnection) **\[[17][17]]\[[18][18]]**:  

| Layer        |Function                                                                                                                                |
| -------------|:---------------------------------------------------------------------------------------------------------------------------------------|
| Physical     | Transmit & receive raw data over a physical medium (concerned with hardware).                                                          |
| Data Link    | Reliable transmission of data between 2 nodes connected by a physical layer.                                                           |
| Network      | Structuring & management of a multi-node network. Responsibilities include: <ul><li>Addressing</li><li>Routing</li><li>Traffic Control</li></ul>|
| Transport    | Reliable transmission of data segments between points on a network. Responsibilities include: <ul><li>Segmentation</li><li>Acknowledgement</li><li>Multiplexing</li></ul>|
| Session      | Managing communication sessions/ continuous exchange of information. |
| Presentation | Translation of data between a networking service and an application. Includes: <ul><li>Character Encoding</li><li>Data Compression</li><li>Encryption/Decryption</li></ul>|
| Application  | High-level APIs. Includes: <ul><li>Resource Sharing</li><li>Remote File Access</li></ul>|

Practically, this manifested itself in the TCP/IP protocol becoming the global standard we use today. The implementation of TCP/IP relative to OSI is as follows **\[[19][19]]**: 

| Implemented TCP Layering System | OSI Layer                                                         |
| ----------------------------| ------------------------------------------------------------------|
| Network Access              | <ul><li>Physical</li><li>Data Link</li></ul>                      | 
| Internet (IP)               | <ul><li>Network</li></ul>                                         |
| Transport (TCP)             | <ul><li>Transport</li></ul>                                       |
| Application                 | <ul><li>Session</li><li>Presentation</li><li>Application</li></ul>|

After reviewing the history of the internet's architecture, the following concerns (at each layer) were identified as it relates to this project: 

| Implemented TCP Layering System | Concerns for Off-Grid Internet                                    |
| --------------------------------| ------------------------------------------------------------------|
| Network Access                  | <ol><li>Physical</li><ul><li>(Random) Mobility</li><li>Link Adaptation</li><li>Variable Transmission Power</li><li>Multiple Transceivers</li><li>Signal Strength</li><li>Link Quality Feedback</li><li>Transceiver Performance</li></ul><li>Data Link<ul><li>Multipoint Communication (MAC protocols allow for only single hops) **\[[21][21]]**\*</li></ul></li></ol>| 
| Internet (IP)                   | Current Network Standard in WMN System Struggles With:<br/><br/><ul><li>Routing Protocol\*</li><li>Multicast Scalability/Efficiency\*</li><li>Reliability\*</li><li>Mobile User Connectivity\*</li><li>Flexibility\*</li><li>Quality of Service (QoS)\*</li><li>Fairness\*</li></ul>|
| Transport                       | TCP Protocol Falters With:<br/><br/><ul><li>Transmission<ol><li>Not good for data in single hops\*</li><li>Inherent traffic flow control (flow balance)</li><li>Poor adaptive routing and forwarding capabilities (does not deal with wildly fluctuating network path)</li><li>QoS and bandwidth reservation</li></ol></li><li>Security: cryptographic authentication of every single packet</li></ul>|
| Application                     | <ul><li>Resource Discovery (DNS works for discovery of online services, not for device/ sensor discovery)\*</li><li>Caching<ol><li>Requires client & server (end-to-end points) to be constantly online\*</li><li>Loss of realtime data\*</li><li>No Latency Requirements\*</li><li>Performance Impairments (bottlenecked throughput due to automatic repeat request)\*</li></ol></li></ul>|


<center>

\*Reference to: **\[[20][20]]**

</center>

Our solution covers the hardware constraints and concerns of range. To address issues concerning speed, resiliency, and fault tolerance, NDN will run on ANT. NDN is an internet architecture that promotes reusing TCP/IP's successful components while addressing its' shortcomings. One of the most significant changes is addressing content by name rather than by address. Requests are made by searching for cached content on the network, which are encrypted and tagged, and retrieves the content from the closest source. This prevents making a cross-country/global trip to get content and fetches it from the nearest source caching it instead. This allows access speeds to increase given that it cuts down on the distance and logistics of fetching content. There is a dedicated community, codebase, and investment from the NSF which makes this technology very attractive for this project as well as the future of the internet itself **\[[22][22]]**.

Assessing effective strategies for resilient communication in various off-grid scenarios will need a comprehensive system covering the constraints of each unique community. Network logistics will maximize communication potential by recommending strategies by simulating communications fault tolerance in the respective area. Our simulation primarily focuses on geospatial, internet infrastructure, and commercial/ industry as well as nonprofit presence data. These features will be downloaded from open source venues and collected from sites for the sole purpose of research. In the long term, we desire to create an internet/ communications resiliency alliance program to form strategic partnerships with governments, industry, non-profits, and other institutions to evenly distribute the ANTs in preparation.   

## Differentiation
While our product draws upon existing platforms, communities, and hardware, it is novel in how it tackles the internet accessibility issue. ANT is essentially designed to be a radio tower in a box without the need for a tower reducing costs while enhancing resiliency.The NDN protocol differentiates our project from past attempts by enhancing speed and security without modifying infrastructure. To maximize impact to areas requires logistics on the constraints facing each area and insightful planning. Our data and optimization algorithms empower the planning for disaster recovery. 

Little, if any, has been done to develop a “disaster proof” internet network for the affected and potentially vulnerable areas. Satellite and weather balloons are one solution, yet are costly, run into bottlenecked bandwidth speed, and falter under live meteorological constraints. Surviving towers are not reliable as it can easily get overwhelmed from too many users. Our solution, incorporating resilient hardware and logistical planning, tackles this issue in a different way. We solve this with a prevention first, treatment secondary ethos. We take preventative measures keeping the internet grounded through strategic distribution and rugged design. 

## Affordability
Our solution is simple as it is composed of the physical product and our intelligent network logistics strategy. This means our costs can be broken down to three components: manufacturing, distribution, and processing. The product's value is the sum of its' parts prices multiplied by the number of orders that need to be filled. We can expect that the price of this product goes down as the quantity of production goes up since we would purchase the parts in bulk. Assembly could be done by the manufacturer, by our team, or by the community (just as IKEA does to drive the cost down of its' items). Distribution would be determined by factors of shipping such as weight and volume. Installation brings the cost up due to materials (pvc pipes, wires, and cables) and setup. Processing involves time and computing resources to run our service to assess optimal strategies for setting up internet connectivity. For this early stage our conservative estimate is that the cost per ANT would be between $1,000 and $1,500 depending on the range and antenna. We believe that with time, experience, and improved methods we could bring it down to half the cost. 

## Social Impact
Our solution is low cost, resilient, and easy to set up in comparison to historical methods of accessing internet. The solution embodies the strength and reliability of existing expensive network infrastructure with the resiliency of a community based mesh network. The low cost of the device reduces the barrier of accessibility and the community (distributed) centric design emphasizes higher adoption of the network itself by neighbors and members of the community. With these characteristics, this design encourages more residents to join, which likely entails a higher density of ANTs. This boosts connectivity and speeds while reducing overall operating costs; thus, lowering the cost per person and addressing the financial and connectivity concern for low income and sparsely developed communities. Additionally, it monitors and controls traffic speed enabling communities to determine the “health” status of the network. If bottlenecks in speed and/or signal strength are the result of the ANT mesh network, measures can be taken to prevent these issues (see scalability section). An extra layer of resiliency is added with respect to internet and/or electrical blackouts. Ultimately a decentralized network can be established on-the-fly. 

## Scalability
Our product enhances internet connectivity and speed by scaling horizontally and vertically. As more devices get added to mesh network throughput increases thus preventing bottlenecking/ slowdowns during surges in internet consumption by the community. This is a typical issue in communities since much of their traffic is controlled by a single router/ point of contact to existing internet infrastructure. The addition of more ANTs in a given area entails stronger signal strength and a robust system with less congestion. Additionally, our solution scales vertically with NDN as it provides faster internet access speeds without changing the existing infrastructure/ resources. Should information get lost in transit between the request and the content, NDN goes to last router where the information was cached and retrieves it. This is different than TCP/IP which makes a full trip back to data centers/ CDNs when content gets lost in transmission. Additionally, greater density of ANTs entails a faster and more resilient network since content gets cached. Therefore a larger user base means more information get requested and cached in a distributed manner. 

## Openness
There are countless of resources to showcase our design to the general public. For professional and development purposes, we decide to share our progress through three different types of mediums - Github **\[[23][23]]**, Esri’s StoryMap **\[[24][24]]**, and Shiny App IO **\[[25][25]]**. Github is quite popular on the web with the proper format to display and update documentation. Additionally, it fosters a professional social networking atmosphere allowing for individuals to expand upon and reduce bugs in the project (Linus's law). Esri's StoryMap has aesthetically pleasing templates to build on a story of the project and display geospatial data on maps. Shiny Apps (written in R) will be incorporated into Esri's StoryMap to run additional data visualizations and statistical algorithms. Shiny App IO or Shiny via RStudio is somewhat simple, yet powerful for the audience to interact with our beta design including identifying digital divide areas.Furthermore, it allows for rapid prototyping of web applications that can run online and offline making it attractive to run an interactive site to collect forms and allow communities to assess optimal solutions provided they supply their constraints (investment, population density, etc).

## Portability
Every building has fire extinguishers for fire emergency purposes in addition to AEDs and Medkits for threatening situations. These were set up as insurance in the event that something may go terribly wrong. We see the issue concerning off-grid/ disaster resiliency in a similar manner. A well designed item, covering the basis of and responds to an important concern which is prepped for in advance. This communication device should be portable, able to power other devices, communicate with other devices/ members, and send out distress signals especially in the event of a electrical and communication blackouts from disasters. Therefore, our solution is designed to be lightweight with dimensions between a wireless router and a small shoebox. Composed of an aluminum shell, the exterior has interfaces for antennae, ethernet, a USB port, and a concealed emergency button. The interior consists of a power converter, cluster of batteries (120 Wh), and the router (assuming we use it) / Raspberry Pi, hardrive, and sensors tracking acceleration as well as heat. Hence, the entire box will weigh between 7 - 10 pounds, light enough for individuals to carry it by hand and bring it with them wherever they go. 

## Power
A Yagi Antenna (7 W) and Raspberry Pi 3 B Base Model (2 - 5W) will consume between 9 and 12 W depending on the amount of stress the Raspberry Pi will receive from its users. With that and the 120 Wh battery, the box on emergency power mode will last for 12 - 13 hours, which should be sufficiently buy enough time for rescue missions, repair crews to repair the powerline(s), community members helping each other out, and/or emergency personnel pinpointing the geocoordinate location of the distress signal. This time will go down if the ANT is also powering another device.

## Applications
Naming in NDN, along with caching, is of critical importance given how it provides some unique opportunities. Namespace management is not part of the NDN architecture just as address space management is not part of the IP architecture. This allows for NDN to support for functionality such as content distribution, mobility, and delay-tolerant networking. Enter the emergency feature.

During an event such as that of a disaster all data can not be treated equal. One watching Netflix should not have priority over/ be on par with someone trying to take action in times of crisis. In such scenarios an emergency broadcast system and data prioritization will be needed. Our emergency prioritization will change how namespace is managed on the network to send and receive only certain information. Our system will allow for real time text based (and in the future, depending on test results, voice/ video) messaging between participants on the network. Additionally, a form tracking/requesting provisioning of resources could be implemented to distribute resources quickly. This achieved by using Sync, which leverages NDN’s basic Interest-Data exchange communication model (a built-in multicast delivery), to synchronize datasets in the mesh network.

[1]:https://dyn.com/blog/internetunderfire/
[2]:https://www.vox.com/a/internet-maps#list-18
[3]:https://en.wikipedia.org/wiki/List_of_disasters_by_cost
[4]:http://www.nytimes.com/2008/12/12/us/12cnd-storm.html
[5]:https://www.census.gov/content/dam/Census/library/publications/2017/acs/acsbr16-01.pdf
[6]:https://www.usatoday.com/story/news/world/2017/10/30/puerto-rico-power-restoration-why-taking-so-long/806747001/
[7]:https://www.wired.com/story/in-puerto-rico-no-power-means-no-telecommunications/
[8]:https://raspberrypi.stackexchange.com/questions/67600/can-my-rpi3-running-raspbian-be-used-to-flash-dd-wrt-on-to-a-compatible-router
[9]:https://wiki.openwrt.org/toh/raspberry_pi_foundation/raspberry_pi
[10]:https://github.com/remap/ndn-pi
[11]:http://named-data.net/wp-content/uploads/2015/06/ndn-ar2015.pdf
[12]:https://named-data.net/wp-content/uploads/2016/10/2-codebase-overview.pdf
[13]:https://medium.com/@edoardo849/turn-a-raspberrypi-3-into-a-wifi-router-hotspot-41b03500080e
[14]:https://www.wired.com/2014/01/its-time-to-take-mesh-networks-seriously-and-not-just-for-the-reasons-you-think/
[15]:https://www.technologyreview.com/s/404601/from-the-editor-mesh-networking-matters/
[16]:http://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=7754201
[17]:https://en.wikipedia.org/wiki/OSI_model
[18]:https://www.iso.org/ics/35.100/x/
[19]:https://spectrum.ieee.org/tech-history/cyberspace/osi-the-internet-that-wasnt
[20]:https://named-data.net/wp-content/uploads/2016/02/ndn-0038-1-challenges-iot.pdf
[21]:http://user.it.uu.se/~erikn/papers/Realman05.pdf
[22]:https://named-data.net/wp-content/uploads/2014/10/named_data_networking_ccr.pdf
[23]:https://github.com/
[24]:https://storymaps.arcgis.com/en/
[25]:https://www.shinyapps.io/

## References 
1. “Syria, Venezuela, Ukraine: Internet Under Fire | Dyn Blog.” Dyn Syria Venezuela Ukraine Internet Under Fire Comments, Oracle + Dyn, 26 Feb. 2014, https://dyn.com/blog/internetunderfire/.

2. Lee, Timothy B. “40 Maps That Explain the Internet.” Vox.com, Vox, 2 June 2014, www.vox.com/a/internet-maps#list-18.

3. “List of Disasters by Cost.” Wikipedia, Wikimedia Foundation, 2017, https://en.wikipedia.org/wiki/List_of_disasters_by_cost.

4. THE ASSOCIATED PRESS. “Ice Storm Cripples Parts of Northeast.” The New York Times, The New York Times, 12 Dec. 2008, www.nytimes.com/2008/12/12/us/12cnd-storm.html.

5. Bishaw, Alemayehu, and Craig Benson. “Poverty: 2015 and 2016: American Community Survey Briefs.” ACS, vol. 16, no. 01, Sept. 2017, pp. 3–4., doi:https://www.census.gov/content/dam/Census/library/publications/2017/acs/acsbr16-01.pdf.

6. Gomez, Alan, and Rick Jervis. “Puerto Rico Power Restoration: Why It Is Taking so Long.” USA Today, Gannett Satellite Information Network, 31 Oct. 2017, www.usatoday.com/story/news/world/2017/10/30/puerto-rico-power-restoration-why-taking-so-long/806747001/.

7. Rogers, Adam. “In Puerto Rico After Hurricane Maria, No Power Means No Telecommunications.” Wired, Conde Nast, 10 Oct. 2017, www.wired.com/story/in-puerto-rico-no-power-means-no-telecommunications/.

8. “Can My RPi3 Running Raspbian Be Used to Flash DD-WRT on to a Compatible Router.” Pi 3 - Can My RPi3 Running Raspbian Be Used to Flash DD-WRT on to a Compatible Router - Raspberry Pi Stack Exchange, Stack Exchange, https://raspberrypi.stackexchange.com/questions/67600/can-my-rpi3-running-raspbian-be-used-to-flash-dd-wrt-on-to-a-compatible-router.

9. “OpenWrt Wiki.” Raspberry Pi [OpenWrt Wiki], OpenWrt Wiki, wiki.openwrt.org/toh/raspberry_pi_foundation/raspberry_pi.

10. Remap. “Remap/Ndn-Pi.” GitHub, 4 July 2017, https://github.com/remap/ndn-pi.
