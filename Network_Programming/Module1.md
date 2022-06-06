# Module1
> Network study material from CISCO
## Network Components
<hr/>
<p>
<b>Hosts:</b> All computers that are connected to a network and participate directly in network communication are classified as hosts. Hosts can be called end devices. Some hosts are also called clients. The term hosts specifically refers to devices on the network that are assigned a number for communication purposes. This number enables to identify the host within a particular network and also called the Internet Protocol(IP) address.
</p>
<p>
<b>Server:</b> Computer with software that allow them to provide information. Each service such as email or web pages require separe server software. 
<p>
<br/>
<table>
<tr>
<th>Type</th>
<th>Description</th>
</tr>
<tr>
<th>Email server:</th>
<td>runs email server software. Clients use mail client software, such as Microsoft Outlook to access email on the server.</td>
</tr>
<tr>
<th>Web server:</th>
<td>The web server runs web server software. </td>
</tr>
<tr>
<th>File server:</th>
<td>The file server stores corporate and user files in a central location. The client devices access these files with client software such as the Windows File Explorer.</td>
</tr>
<table>
<br/>
<hr/>

## Peer-to-Peer
<hr/>
<p>
It is possible for one computer to be used both client and server at the same time. In small businesses and homes, many computers function as the servers and clients on the network. This type of network is called a peer-to-peer network.<br/>
For example : print sharing PC has a Universal Serial Bus (USB) connection to the printer and a network connection, using a network interface card (NIC), to the file sharing PC.
</p>
Advantages of peer-to-peer networking:
<ul>
    <li>Easy to set up</li>
    <li>Less complex</li>
    <li>Lower cost because network devices and dedicated servers may not be required</li>
    <li>Can be used for simple tasks such as transferring files and sharing printers</li>
</ul>
Disadvantages of peer-topeer networking:
<ul>
    <li>No cnetralized administration</li>
    <li>Not as secure</li>
    <li>Not scalable</li>
    <li>All devices may act as both clients and servers which can slow their performance</li>
</ul>
<br/>
<hr/>

## Intermediary Devices
<hr/>
<p>
Intermediary devices connect the individual end devices to the network. They can connect multiple individual networks to form an internetwork. These intermediary devices provide connectivity and ensure that data flows across the network.

Intermediary devices use the destination end device address, in conjunction with information about the network interconnections, to determine the path that messages should take through the network.
</p>
<br/>

> <b>Intermediary Devices: </b> Wireless Router, LAN Switch, Router, Multilayer Swith, Firewall Appliance 

<br/>
Intermediary network devices perform some or all of these functions:
<ul>
<li>Regenerate and retransmit communication signals</li>
<li>Maintain information about what pathways exist through the network and internetwork</li>
<li>Notify other devices of errors and communication failures</li>
<li>Direct data along alternate pathways when there is a link failure</li>
<li>Classify and direct messages according to priorities</li>
<li>Permit or deny the flow of data, based on security settings</li>
</ul>

<br/>
<hr/>

## Nework Media
<hr/>
<p>Communication transmits across a network on media. The media provides the channel over which the message travels from source to destination.
</p>

> Modern networks primarily use three types of media to interconnect devices : <b>Cooper, Fiber-optic, Wireless </b>

<br/>
The 4 main criteria for choosing network media are these:
<ul>
<li>What is the maximum distance that the media can succssefully carry a signal?</li>
<li>What is the environment in which the media will be installed?</li>
<li>What is the amount of data and at what speed must it be transmitted?</li>
<li>What is the cost of the media and installation?</li>
</ul>
<br/><hr/>

## Network Representations and Topologies
<hr/>
<p>
In addition to these representations, specialized terminology is used to describe how each of these devices and media connect to each other:

<b>Network Interface Card (NIC)</b> - A NIC physically connects the end device to the network.<br/>
<b>Physical Port -</b> A connector or outlet on a networking device where the media connects to an end device or another networking device.<br/>
<b>Interface -</b> Specialized ports on a networking device that connect to individual networks. Because routers connect networks, the ports on a router are referred to as network interfaces.</p>

> <b>Note:</b> The terms port and interface are often used interchangeably.

<br/>
<p>Topology diagrams are mandatory documentation for anyone working with a network. There are two types of topology diagrams: physical and logical.<br/>

<b>Physical Topology Diagrams</b>

Physical topology diagrams illustrate the physical location of intermediary devices and cable installation. You can see that the rooms in which these devices are located are labeled in this physical topology.<br/>

<b>Logical Topology Diagrams</b>

Logical topology diagrams illustrate devices, ports, and the addressing scheme of the network. You can see which end devices are connected to which intermediary devices and what media is being used.
</p>
<br/><hr/>

## LANs and WANs
<hr/>
<p>
The two most common types of network infrastructures are Local Area Networks (LANs), and Wide Area Networks (WANs). <br/>
<b>LANs</b>

A LAN is a network infrastructure that spans a small geographical area. LANs have specific characteristics:
</p>
<ul>
<li>LANs interconnect end devices in a limited area such as a home, school, office building, or campus.</li>
<li>A LAN is usually administered by a single organization or individual. </li>
<li>Administrative control is enforced at the network level and governs the security and access control policies.</li>
<li>LANs provide high-speed bandwidth to internal end devices and intermediary devices, as shown in the figure.</li>
</ul>
<p><b>WANs</b>

The figure shows a WAN which interconnects two LANs. A WAN is a network infrastructure that spans a wide geographical area. WANs are typically managed by service providers (SPs) or Internet Service Providers (ISPs).

WANs have specific characteristics:
</p>
<ul>
<li>WANs interconnect LANs over wide geographical areas such as between cities, states, provinces, countries, or continents.</li>
<li>
WANs are usually administered by multiple service providers.</li>
<li>WANs typically provide slower speed links between LANs.</li>
</ul>
<br/><hr/>

## Internet
<hr/>
<p>
WANs are then connected to each other. The red WAN connection lines represent all the varieties of ways we connect networks. WANs can connect through copper wires, fiber-optic cables, and wireless transmissions (not shown).

The internet is not owned by any individual or group. Ensuring effective communication across this diverse infrastructure requires the application of consistent and commonly recognized technologies and standards as well as the cooperation of many network administration agencies. There are organizations that were developed to help maintain the structure and standardization of internet protocols and processes. These organizations include the Internet Engineering Task Force (IETF), Internet Corporation for Assigned Names and Numbers (ICANN), and the Internet Architecture Board (IAB), plus many others.
</p>
<br/><hr/>

## Intranets and Extranets
<hr/>
<p>
There are two other terms which are similar to the term internet: intranet and extranet.

Intranet is a term often used to refer to a private connection of LANs and WANs that belongs to an organization. An intranet is designed to be accessible only by the organization's members, employees, or others with authorization.

An organization may use an extranet to provide secure and safe access to individuals who work for a different organization but require access to the organization’s data. <br/>
Here are some examples of extranets:
<ul>
<li>A company that is providing access to outside suppliers and contractors</li>
<li>A hospital that is providing a booking system to doctors so they can make appointments for their patients</li>
<li>A local office of education that is providing budget and personnel information to the schools in its district</li>
</ul>
</p>
Intranet (Company only) < Extranet (Suppliers,Customers,Collaborators) < Interent (The World)
<br/><hr/>

## Home and Small Office Internet Connections
<hr/>

### Home and Small Office

<p>
<b>Cable -</b> Typically offered by cable television service providers, the internet data signal transmits on the same cable that delivers cable television. It provides a high bandwidth, high availability, and an always-on connection to the internet.<br/>
<b>DSL -</b> Digital Subscriber Lines also provide high bandwidth, high availability, and an always-on connection to the internet. DSL runs over a telephone line. In general, small office and home office users connect using Asymmetrical DSL (ADSL), which means that the download speed is faster than the upload speed.<br/>
<b>Cellular -</b> Cellular internet access uses a cell phone network to connect. Wherever you can get a cellular signal, you can get cellular internet access.Performance is limited by the capabilities of the phone and the cell tower to which it is connected.<br/>
<b>Satellite -</b> The availability of satellite internet access is a benefit in those areas that would otherwise have no internet connectivity at all. Satellite dishes require a clear line of sight to the satellite.<br/>
<b>Dial-up Telephone -</b> An inexpensive option that uses any phone line and a modem. The low bandwidth provided by a dial-up modem connection is not sufficient for large data transfer, although it is useful for mobile access while traveling.
</p>

<br/>

### Businesses Internet Connections
<p>
<b>Dedicated Leased Line -</b> Leased lines are reserved circuits within the service provider’s network that connect geographically separated offices for private voice and/or data networking. The circuits are rented at a monthly or yearly rate.<br/>
<b>Metro Ethernet -</b> This is sometimes known as Ethernet WAN. In this module, we will refer to it as Metro Ethernet. Metro ethernets extend LAN access technology into the WAN. Ethernet is a LAN technology.<br/>
<b>Business DSL -</b> Business DSL is available in various formats. A popular choice is Symmetric Digital Subscriber Line (SDSL) which is similar to the consumer version of DSL but provides uploads and downloads at the same high speeds.<br/>
<b>Satellite -</b> Satellite service can provide a connection when a wired solution is not available.</p>
<br/><hr/>

## The Converging Network 
<hr/>
<p>
<b>Traditional Separate Networks</b>

Consider a school built thirty years ago. Back then, some classrooms were cabled for the data network, telephone network, and video network for televisions. These separate networks could not communicate with each other. Each network used different technologies to carry the communication signal. Each network had its own set of rules and standards to ensure successful communication. Multiple services ran on multiple networks.
</p>

<p>
<b>Converged Networks</b>

Today, the separate data, telephone, and video networks converge. Unlike dedicated networks, converged networks are capable of delivering data, voice, and video between many different types of devices over the same network infrastructure. This network infrastructure uses the same set of rules, agreements, and implementation standards. Converged data networks carry multiple services on one network.

Converged data network carrying multiple services on one network.
</p>

<br/><hr/>

## Network Architecture
<hr/>

### Fault Tolerance
<p>
A fault tolerant network is one that limits the number of affected devices during a failure. It is built to allow quick recovery when such a failure occurs. These networks depend on multiple paths between the source and destination of a message. If one path fails, the messages are instantly sent over a different link. Having multiple paths to a destination is known as redundancy.

Implementing a packet-switched network is one way that reliable networks provide redundancy. Packet switching splits traffic into packets that are routed over a shared network. A single message, such as an email or a video stream, is broken into multiple message blocks, called packets. Each packet has the necessary addressing information of the source and destination of the message. The routers within the network switch the packets based on the condition of the network at that moment. This means that all the packets in a single message could take very different paths to the same destination. In the figure, the user is unaware and unaffected by the router that is dynamically changing the route when a link fails.
</p>
<br/>

### Scalability
<p>A scalable network expands quickly to support new users and applications. It does this without degrading the performance of services that are being accessed by existing users. </p>
<br/>

### Quality of Service
<p>
Quality of Service (QoS) is an increasing requirement of networks today. New applications available to users over networks, such as voice and live video transmissions, create higher expectations for the quality of the delivered services. Have you ever tried to watch a video with constant breaks and pauses? As data, voice, and video content continue to converge onto the same network, QoS becomes a primary mechanism for managing congestion and ensuring reliable delivery of content to all users.

Congestion occurs when the demand for bandwidth exceeds the amount available. Network bandwidth is measured in the number of bits that can be transmitted in a single second, or bits per second (bps). When simultaneous communications are attempted across the network, the demand for network bandwidth can exceed its availability, creating network congestion.

When the volume of traffic is greater than what can be transported across the network, devices will hold the packets in memory until resources become available to transmit them. In the figure, one user is requesting a web page, and another is on a phone call. With a QoS policy in place, the router can manage the flow of data and voice traffic, giving priority to voice communications if the network experiences congestion.The focus of QoS is to prioritize time-sensitive traffic. The type of traffic, not the content of the traffic, is what is important.
</p>
<br/>

### Network Security
<p>
The network infrastructure, services, and the data contained on network-attached devices are crucial personal and business assets. Network administrators must address two types of network security concerns: network infrastructure security and information security.

Securing the network infrastructure includes physically securing devices that provide network connectivity and preventing unauthorized access to the management software that resides on them, as shown in the figure.
Network administrators must also protect the information contained within the packets being transmitted over the network, and the information stored on network attached devices. In order to achieve the goals of network security, there are three primary requirements.
</p>
<ul>
<li>Confidentiality - Data confidentiality means that only the intended and authorized recipients can access and read data.</li>
<li>Integrity - Data integrity assures users that the information has not been altered in transmission, from origin to destination.</li>
<li>Availability - Data availability assures users of timely and reliable access to data services for authorized users.</li>
</ul>
<br/><hr/>

## Netwwork Trends
<hr/>

### Cloud Computing


<table>
<caption>Cloud Types</caption>
<tr>
<th>Cloud Type</th>
<th>Description</th>
</tr>
<tr>
<th>Public clouds</th>
<td>Cloud-based applications and services offered in a public cloud are made available to the general population. Services may be free or are offered on a pay-per-use model, such as paying for online storage. The public cloud uses the internet to provide services.
Private clouds	<td>
</tr>
<tr>
<th>Private clouds</th>
<td>Cloud-based applications and services offered in a private cloud are intended for a specific organization or entity, such as a government. A private cloud can be set up using the organization’s private network, though this can be expensive to build and maintain. A private cloud can also be managed by an outside organization with strict access security.</td>
</tr>
<tr>
<th>Hybrid clouds</th>
<td>A hybrid cloud is made up of two or more clouds (example: part private, part public), where each part remains a distinct object, but both are connected using a single architecture. Individuals on a hybrid cloud would be able to have degrees of access to various services based on user access rights.</td>
</tr>
<tr>
<th>Community clouds</th>
<td>A community cloud is created for exclusive use by specific entities or organizations. The differences between public clouds and community clouds are the functional needs that have been customized for the community. For example, healthcare organizations must remain compliant with policies and laws (e.g., HIPAA) that require special authentication and confidentiality. Community clouds are used by multiple organizations that have similar needs and concerns. Community clouds are similar to a public cloud environment, but with set levels of security, privacy, and even regulatory compliance of a private cloud.</td>
</tr>
</table>

 