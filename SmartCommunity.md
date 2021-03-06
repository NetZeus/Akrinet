# Internet Challenge
**10%** of all Americans (34 million people) lack access to quality Internet connectivity. <a href = "https://wirelesschallenge.mozilla.org/_assets/NSF-SmartCommunity.pdf" >The Smart Community Networks Challenge</a> aims to close this access gap by enhancing wireless connectivity in areas where Internet access is a challenge, whether due to geographic, financial or other factors. With a total of **$1M** in prize money, the Smart Community Networks Challenge seeks wireless solutions that leverage existing physical infrastructure to provide robust access to the whole Internet in underserved areas. 

## Our Problem Statement
The primary issue facing communities in need of greater access to the internet is infrastructure. The backbone of the internet is essentially composed of cables due their reliability and speed. Satellite and other wireless methods are alternative options yet these methods are undercut by geographical, meteorological, and other constraints. Provided little commercial interest and small government funding bottlenecks access to these communities or require them to set up their own infrastructure. 

## Our Solution Statement 
Our solution consists of 3 parts: **`Named Data Networking (NDN)`**, **`modified routers`**, and a **`networking logistics`** tool. NDN, a development in network protocols, is key to our project. Providing more security and faster browsing speeds over the existing TCP/IP protocol, it will achieve quick and reliable online access. The hardware leverages a low cost router to run NDN and establish a mesh-network. Our networking logistics assists communities with assessing, planning, and setting up internet access.

## Users
Like access to electricity and indoor plumbing, broadband Internet should be seen as a utility necessity. However, 34 million Americans lack access to quality Internet (of which **23 million** do not have access to broadband) due to various reasons **\[[1][1]]**.

**Internet Speed**
[![Speed Map](https://github.com/NetZeus/Akrinet/blob/master/Images/18yiv2rhdghz9png.png)](https://gizmodo.com/americas-internet-inequality-a-map-of-whos-got-the-b-1057686215)
<br>*Credit: NOAA, Gizmodo*

Our off-grid Internet design fulfills this gap by tailoring it to those with low quality or no access. It’s likely that this group has at __least one of the following characteristics__: 

        1) Low socioeconomic status (<= Federal Poverty Line) 
        2) Reside in difficult, isolated, or hazardous geographic zones
        3) Have between 1–2 Internet service providers (ISPs)
        4) Low education level. 

Income may be the most transparent factor as it correlates to the geographic variations of the amount of ISPs and education level **\[[2][2]]**. Currently, **80 – 90% of the most affluent** households in the United States have Internet at home, in contrast to **50% of the those with the lowest median income \[[3][3]]**. With that, our team will target rural communities as poverty and disability rates are higher than urban areas **\[[4][4]]**. Additionally they have less physical and financial access to resources, which translates to very few ISPs; thus, a lack of competition leads to overpriced and poor quality of services. 1 in 3 have only 1 ISP and majority of the rest have only 2 **\[[5][5]]**.

**Residential Fixed Internet Access Service Providers**
[![ISPs](https://github.com/NetZeus/Akrinet/blob/master/Images/Screenshot_2017-11-16_00-00-05.png)](https://www.fcc.gov/reports-research/maps/residential-fixed-internet-access-service-providers-by-census-block/)
<br>*Credit: FCC*


## Community / Location 
Numerous communities fit the listed characteristics from the “Users” section. Our focus will be on areas that match all three characteristics. __They include__: 

    1) Within the state borders of Mississippi, Louisiana, and Arkansas
    2) West Virginia
    3) Southern Texas
    4) Northern Maine

**Poverty Map**
[![Pov](https://github.com/NetZeus/Akrinet/blob/master/Images/8tKoLPLmAh)](http://www.povertyusa.org/wp-content/themes/poverty2012/full-screen-county-map.php)
<br>*Credit: Poverty USA*

These have clusters of high poverty rates with monopolized ISPs and in isolated geographic areas. Rural Louisiana, Arkansas, Mississippi consist a mix of cultivated agricultural, bayous, and water bodies. West Virginia hugs onto the Appalachian mountains. Southern Texas is isolated from the major cities (i.e. Houston, San Antonio) with a mix of shrub and grass land cover. In Northern Maine, we are incorporating Aroostook County and the unorganized territory since they are sparsely populated areas. Aroostook County has 68,000 people with an area larger than Connecticut and Rhode Island combined **\[[6][6]]**. On another note, its’ more remote cousin with no name - <a href = "http://maine.gov/revenue/propertytax/unorganizedterritory/unorganized.htm">unorganized territory of Maine</a> - has a population of only 8000 with an area larger than Maryland **\[[7][7]]**. These areas cover a diverse set of constraints especially with respect to geographical, meteorological, and population density concerns.

## Technical Feasibility 
Our solution takes on physical and virtual form, orchestrated by the Named Data Networking (NDN) protocol. The physical product is essentially a box containing a router, small computer, power supply, antennae, and backup battery supply. We call our box **`ANTs (Alternative Network Transmission boxes)`**. This will be our greatest technical hurdle as it requires much research and design to ensure maximized value in addition to overhead of testing hardware. To ensure continued internet access and notifications of blackouts, the ANT comes with a backup battery providing extra hours of power. We envision that ANTs will sit in homes and can be slung on trees allowing for easy installation and widespread access. Powering ANTs outside of homes will likely require plugging onto a nearby power grid (using pvc pipe and wiring) as the majority of the these communities have access to power. Manufacturing the case with aluminum will allow for cost effective, lightweight, and durable properties. Size will be somewhere between a WiFi router and a small shoebox.

Currently, research into desirable budget hardware running secure communications and NDN is being conducted. We are compiling a database of routing and processing hardware with information about performance, listings of supported software, cost, weight, and dimensions. With this information tradeoffs can be assessed finding the overall best value. The `Raspberry Pi 3` (RPI3) is our current choice given its community support, hardware extendability, and security as it runs mainline Linux. It’ll also allow for logging internet speeds to determine sources of slowdowns/bottlenecking of the connection. **Most importantly, the RPI3 can flash DD-WRT, OpenWRT, and the code running the NDN platform \[[8][8]]\[[9][9]]\[[10][10]]\[[11][11]]. Thus, removing the need of a router altogether provided the appropriate hardware is connected.** The device will likely also sport 3 antenna ports to interface for different communications; WiFi, 4G/ Cellular, and TV. We believe these port options should be available for communities requiring alternative or additional communications in addition to interfacing with established infrastructure that could be leveraged. These include existing fiber, wireless towers, and unused radio/television airwaves (known as "white space") to get online.

Like much of the US's problem with internet speed, the issue lies in infrastructure. Given the versatile constraints of this challenge slowdowns may occur even under optimal scenarios. One such concern is using locally available outdated infrastructure ("the last mile" issue) **[[12][12]][13][13]]**. Another is resiliency of wireless communications during storms slowing down speed. To overcome issues and provide faster speeds with the same infrastructure, NDN will run on ANT. NDN is an internet architecture that promotes reusing TCP/IP's successful components while addressing its' shortcomings **[[14][14]]**. One of the most significant changes is addressing content by name rather than by address. Requests are made by searching for cached content on the network, which are encrypted and tagged, and retrieves the content from the closest source. This prevents making a cross-country/global trip to get content and fetches it from the nearest source caching it instead. This allows access speeds to increase given that it cuts down on the distance and logistics of fetching content. There is a dedicated community, codebase, and investment from the NSF which makes this technology very attractive for this project as well as the future of the internet itself **[[15][15]]**.

Although ANT incorporates an attractive architecture, it only covers half of the battle. Assessing effective strategies for installation and cost will need a comprehensive system covering the constraints of each unique community. Network logistics will maximize feasibility by recommending strategies based on constraints. Assessing optimal impact will need two groups of data. **The first will include existing local infrastructure, ISPs (pricing & availability), non-profits (i.e. DBIUA), and geospatial databases.** Covering each area will pose its own unique geographic characteristics; thus shaping the distribution of the mesh network. Geospatial data (infrastructure, wireless towers, DEMs, etc) will be downloaded from open source venues and collected from sites for the sole purpose of research. Instrumenting data on ISPs and non-profits we can set up strategic partnerships to provide quality access to the internet. To further bolster effective placement of ANT boxes, drones are being considered to quickly collect additional geospatial data on communities lacking internet connection. The second set of features we require is information on the needs of the community and their personal constraints. This combined information can generate a report for interested parties with recommended solutions. In the future an interactive site (which can run offline as well) is being considered so users can enter inputs in our system to review their options.

## Differentiation 
While our product draws upon existing platforms, communities, and hardware, it is novel in how it tackles the internet accessibility issue. We noticed multiple past/existing projects trying to solve issues of quality internet access did so in familiar ways. Most would use wireless mesh networks composed of smartphones, desktops, "cantennas"/ yagi antennas, or expensive specialized instruments to facilitate case-specific constraints. These are relatively cheap methods, however, they only resolve certain cases. They also falter when density decreases and distance across each node increases **[[16][16]]**. Maximizing impact to the majority of the communities requires logistics on the constraints facing each one and scalable methods to quickly address those areas. We achieve this by aggregating data on those populations constraints and utilize optimization algorithms to decide the most effective path. Our hardware is designed to essentially be a radio tower in a box without the need for a tower reducing costs while increasing quality and means to the internet. Adopting the Named Data Network protocol to run our system especially differentiates our project from past attempts and attempts to enhance internet speed without modifying infrastructure. 

## Affordability  ![](https://money.yandex.ru/i/shop/apple-touch-icon-40x40.png)
**Our solution is simple as it is composed of the physical product and our intelligent network logistics strategy.** This means our costs can be broken down to three components: manufacturing, distribution, and processing. The product's value is the sum of its' parts prices multiplied by the number of orders that need to be filled. We can expect that the price of this product goes down as the quantity of production goes up since we would purchase the parts in bulk. Assembly could be done by the manufacturer, by our team, or by the community (just as IKEA does to drive the cost down of its' items). Distribution would be determined by factors of shipping such as weight and volume. Installation brings the cost up due to materials (pvc pipes, wires, and cables) and setup. Processing involves time and computing resources to run our service to assess optimal strategies for setting up internet connectivity. For this early stage our conservative estimate is that **`the cost per ANT would be between $1,000 and $1,500`** depending on the range and antenna. We believe that with time, experience, and improved methods we could bring it down to half the cost. 

## Social Impact 
Our solution is low cost, resilient, and easy to set up in comparison to historical methods of accessing internet. The solution embodies the strength and reliability of existing expensive network infrastructure with the resiliency of a community based mesh network. The low cost of the device reduces the barrier of accessibility and the community (distributed) centric design emphasizes higher adoption of the network itself by neighbors and members of the community. With these characteristics, this design encourages more residents to join, which likely entails a higher density of ANTs. This boosts connectivity and speeds while reducing overall operating costs; thus, lowering the cost per person and addressing the financial and connectivity concern for low income and sparsely developed communities. Additionally, it monitors and controls traffic speed enabling communities to determine the “health” status of the network. If bottlenecks in speed and/or signal strength are the result of the ANT mesh network, measures can be taken to prevent these issues (see scalability section). An extra layer of resiliency is added with respect to internet and/or electrical blackouts. Ultimately a decentralized network can be established on-the-fly.

[![decentr](https://github.com/NetZeus/Akrinet/blob/master/Images/ea87086c485460123cd2978fd7e46dbe.jpg)](https://www.dailydot.com/wp-content/uploads/58a/11/ea87086c485460123cd2978fd7e46dbe.jpg)
<br>*Credit: The Daily Dot*

## Scalability
Our product enhances internet connectivity and speed by scaling horizontally and vertically. As more devices get added to mesh network throughput increases thus preventing bottlenecking/ slowdowns during surges in internet consumption by the community. This is a typical issue in communities since much of their traffic is controlled by a single router/ point of contact to existing internet infrastructure. The addition of more ANTs in a given area entails stronger signal strength and a robust system with less congestion. Additionally, our solution scales vertically with NDN as it provides faster internet access speeds without changing the existing infrastructure/ resources. Should information get lost in transit between the request and the content, NDN goes to last router where the information was cached and retrieves it. This is different than TCP/IP which makes a full trip back to data centers/ CDNs when content gets lost in transmission. Additionally, greater density of ANTs entails a faster and more resilient network since content gets cached. Therefore a larger user base means more information get requested and cached in a distributed manner. 

## Openness
There are countless of resources to showcase our design to the general public. For professional and development purposes, we decide to share our progress through three different types of mediums - Github, <a href = "https://storymaps.arcgis.com/en/" >Esri’s StoryMap</a>, and <a href = "https://www.shinyapps.io">Shiny App IO</a>. **`Github`** is quite popular on the web with the proper format to display and update documentation. Additionally, it fosters a professional social networking atmosphere allowing for individuals to expand upon and reduce bugs in the project (Linus's law). **`Esri's StoryMap`** has aesthetically pleasing templates to build on a story of the project and display geospatial data on maps. **`Shiny Apps`** (written in R) will be incorporated into Esri's StoryMap to run additional data visualizations and statistical algorithms. Shiny App IO or Shiny via RStudio is somewhat simple, yet powerful for the audience to interact with our beta design including identifying digital divide areas.Furthermore, it allows for rapid prototyping of web applications that can run online and offline making it attractive to run an interactive site to collect forms and allow communities to assess optimal solutions provided they supply their constraints (investment, population density, etc).

## Network Footprint
Our hardware accommodates several mediums of transferring information on existing infrastructure. ANTs include multiple wireless options depending on need. These wireless ports will support (numbered by the port): 1) 2.4/5 GHz AC WiFi/ Long Range Yagi Antenna 2) 4G LTE 3) a TV antenna. To make use of the white space the TV antenna will be customized to send/receive antenna access (this is part of the research we are focusing on hardware). The ANT also comes with an ethernet port for direct access/ connectivity through an ethernet connection. With this strategy we can daisy chain a series of ANT boxes until at least one reaches a connection point with existing infrastructure. ANTs function as a Wireless Internet Service Provider (WISP), with the diversity of options available they can accommodate and extend existing infrastructure at a low cost (since the antennas are added on a need-minimum basis). Furthermore, adoption of NDN allows for a potential increase in transmission speeds due to caching and requesting data by name. Requests for data thus will travel to local most point to retrieve data. With network logistics, optimizing antenna setup will be made easy despite unique constraints facing each community. 

## Security and Privacy ![](https://github.com/NetZeus/Akrinet/blob/master/Images/penguin%2C%20server%2C%20system%2C%20platform%2C%20linux%2C%20os%20icon%20icon.png)
By design our solution incorporates the best security practices. The device will run mainline Linux ensuring it is secured with up to date packages and modules at no cost to user. Furthermore, adopting the NDN protocol requires that information needs to be encrypted in transit until reaching the requester of the data. Furthermore the architecture of NDN reinforces security by addressing content by name rather than by address (such as IP). Since requests are routed based on content rather than an address, those addresses will be less susceptible to concentrated/targeted attacks. Additionally, network congestion could be reduced with more routers allowing for cached content to be distributed. NDN, however, has its’ own set of tradeoffs and caveats; for instance instead of addresses being targeted for a DDoS attack, content could be targeted instead causing congestions in the network. At this early stage and scale of adoption this won’t be a concern. Ultimately, the NDN protocol goes beyond the security measures of the current TCP/IP protocol given that the protocol does not include security by design and is largely left to participants in the network.

## References 
[1]:http://bit.ly/2unN8Y2
[2]:http://brook.gs/2ilKvCK
[3]:http://bit.ly/2yKmGdU
[4]:http://to.pbs.org/2yMwqEt
[5]:http://bit.ly/2z661Wp
[6]:https://aroostook.me.us
[7]:http://n.pr/2yKCnBA
[8]:http://bit.ly/2zJKqC3
[9]:http://bit.ly/2z5MFRh
[10]:https://github.com/remap/ndn-pi
[11]:https://wiki.openwrt.org/toh/raspberry_pi_foundation/raspberry_pi
[12]:https://gizmodo.com/why-americas-internet-is-so-shitty-and-slow-1686173744
[13]:https://spectrum.ieee.org/telecom/internet/net-neutralitys-technical-troubles
[14]:https://arxiv.org/pdf/1609.06270v1.pdf
[15]:https://www.nsf.gov/pubs/2016/nsf16586/nsf16586.pdf
[16]:http://web.stanford.edu/~jacksonm/largeworlds-arxiv-0810.2603v1.pdf

1. Levitz, J. (2017, June 5). Rural America Is Stranded in the Dial-Up Age. *The Wall Street Journal*, Retrieved from:          http://bit.ly/2unN8Y2

2. Blelberg, J. and West, D. (2014, Dec. 10). Barriers to Universal Internet Access. *Brookings Institute*, Retrieved from: http://brook.gs/2ilKvCK

3. Dzieza, J. and Bi, F. (2015, July 15). Poverty, more than geography determines who gets online in America. *The Verge*, Retrieved from: http://bit.ly/2yKmGdU

4. Thiede, B., Grelman, L., Weller, S., Beda, S., and Conroy, T. (2017, March 17). 6 charts that illustrate the divide between rural and urban America. *PBS News Hour*, Retrieved from: http://to.pbs.org/2yMwqEt

5. Estes, A. (2015, March 3). Why America's Internet Is So Shitty and Slow. *Gizmodo*, Retrieved from: http://bit.ly/2z661Wp

6. Aroostook County Government. (2017). Aroostook County Quick Facts. Retrieved from: https://aroostook.me.us 

7. Berkes, H. (2005, June 10). Rural Maine Towns Give Up on Self-Government. *NPR Morning Edition*, Retrieved from: http://n.pr/2yKCnBA

8. Jacobson, V., Burke, J., Zhang, L., Zhang, B., Claffy, K., Papadopoulos, C., Abdelzaher, T., Wang, L., Halderman, J., and Crowley, P. (2015). Named Data Networking Next Phase (NDN-NP) Project May 2014 - April 2015 Annual Report. *Named Data Networking*, Retrieved from: http://bit.ly/2zJKqC3

9. Zhang, B. (2016, Sept. 26). An Overview of NDN Codebase. *ACM ICN 2016, Kyoto, Japan*, Retrieved from: http://bit.ly/2z5MFRh

10. Raspberry Pi NDN, Github: https://github.com/remap/ndn-pi 

11. Raspberry Pi OpenWrt, Wireless Freedom: https://wiki.openwrt.org/toh/raspberry_pi_foundation/raspberry_pi 

12. Estes, A. (2015, March 10). Why America's Internet Is So Shitty and Slow. *Gizmodo*, Retrieved from: http://bit.ly/2z661Wp

13. Hect, J. (2015, Feb. 12). Net Neutrality's Technical Troubles. *IEEE SPECTRUM*, Retrieved from: http://bit.ly/2yW71rZ

14. Teixeira, T., Wang, C., and Zink, M. (2016). Can NDN Perform Better than OLSR in Wireless Ad Hoc Networks? *ARXIV*, *University of Massachusetts Amherst*, Retrieved from: https://arxiv.org/pdf/1609.06270v1.pdf 

15. National Science Foundation. (2016). NSF/Intel Partnership on Information-Centric Networking in Wireless Edge Networks (ICN-WEN). Retrieved from: https://www.nsf.gov/pubs/2016/nsf16586/nsf16586.pdf

16. Jackson, M. (2008, Sept. 24). Average Distance, Diameter, and Clustering in Social Networks with Homophily. *ARXIV*, *Stanford University*, Retrieved from: http://web.stanford.edu/~jacksonm/largeworlds-arxiv-0810.2603v1.pdf
