# Configuring-and-Maintaining-DNS-Servers

Hey Friends! <a href="https://www.instagram.com/kelvinintech"><b>@Kelvinintech</b></a>here 👋🏽👋🏽

<p>I developed a project showing how to configure and maintain a DNS Server</p>

<p>

A <b>DNS server</b> is a specialized computer server that stores a database of domain names and their corresponding IP addresses. When a device needs to translate a domain name (like www.example.com) into an IP address (like 192.0.2.1), it sends a request to a DNS server. The <b>DNS server</b> then looks up the domain name in its database and responds with the corresponding IP address.
</p>

<p>Make sense? </p>


![this-is-so-strange-frederick-alexander-pye](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/baa8002c-791b-4f94-ad95-d65142be1557)

<p><b><i>Here's another explanation</i></b></p>

<p>
  
Imagine a <b>DNS server</b> as a big directory or phonebook. <b>Remember those? 🤣</b> 

It contains a list of domain names (like www.example.com) and their corresponding phone numbers (IP addresses).
When you want to visit a website, your device asks the <b>DNS server</b> for the website's IP address.
The <b>DNS server</b> looks up the IP address associated with the domain name and tells your device where to go.
</p>

<p>At this point you're probably wondering, "<b></b>so what is the DHCP thing?</b>"</p> 



<p>
When your device joins a network, it might not know which <b>DNS server</b> to ask for IP addresses. DHCP helps by telling your device the IP address of the DNS server it should use.
So, DHCP helps devices find and configure the <b>DNS server</b> they need to talk to when they want to resolve domain names.
</p>

  ![i'm-so-confused-miranda-lucas](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/3354b530-c089-4e43-b91d-848e6f83e54e)


<p>Confused again? <b>It's okay! It means you are trying!</b> 
  
  <i>Here's an analogy of the DHCP and DNS relationship:</i></p>


<p>
  
  Imagine a family going on a road trip. The family consists of parents (DHCP) and their children (DNS).

DHCP (the parent) is responsible for managing the trip logistics. When they arrive at a new destination (network), DHCP assigns each child (device) a seat in the car (IP address) and provides them with a map (network settings), including instructions on where to stop for food (<b>DNS server</b>).

DNS (the child) knows how to read the map and understands where they need to go (which DNS server to use) to find the nearest ice cream parlor (IP address of a website). However, DNS relies on the directions provided by DHCP (the parent) to know which ice cream parlor (DNS server) it's allowed to visit on the trip.

In this analogy, DHCP acts as the parent figure, guiding DNS and providing necessary instructions (such as the IP address of the DNS server) to navigate the journey (network communication). DNS, like a child, follows these instructions to reach the destination (resolve domain names to IP addresses) effectively.

</p>


![family-matters-ah-ha](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/36043c70-b359-4420-9001-d16cf302536b)


<p>

  When a <b>DNS server</b> is configured, depending on the need, additional DNS server and functionality can be configured for the hierarchy of the network these include the following:

<b>Root DNS Servers</b>: Root DNS servers' essential functionality is the translation of hostnames to IP addresses and provides answers to queries from devices on the network.

<b>Internal & External DNS Servers</b>: An internal DNS server will be hosted inside of the network and will only be accessible for internally connected devices. An external DNS server can be configured on the same network and handle only external requests. If an internal DNS server gets a request from an internal device and can not resolve it, the internal DNS server will contact the external DNS server to resolve the specific request.

<b>Authoritative name servers</b>: Authorative name servers contain specific information of the domain where it is located and are normally the last point of contact to resolve an IP address to a hostname.

<b>DNS caching & Time to live configuration</b>: DNS caching is a temporary database stored on a client machine. This database contains records of the recently visited sites and resources by the user. Time to live (TTL) is the time specified for how long a specific record should be stored on a server before it will be removed.

<b>Recursive lookup</b>: Recursive DNS queries are used when a DNS server queries other <b>DNS servers</b> on the network to determine the location of a specific IP address of a resource on the network.

The different record types can be configured on a <b>DNS server</b> to facilitate communication and access to resources located on the network. These records include the following:

<b>Canonical name (CNAME)</b>: CNAME records are used in conjunction with A records in a DNS system and are configured to point to the domain and never to an IP address. It can be used to set up aliases for resources on the network.

<b>Mail Exchange Record (MX record)</b>: MX records are configured on a DNS server to specify an SMTP server for the specific domain. These records are used to route outgoing emails to a mail server.

<b>Start of Authority (SOA)</b>: These records are part of the DNS Zone file and specify the Authoritative Name Server for the DNS zone. The details for the domain administrator and how often the DNS information needs to be updated are also part of these records.

<b>Pointer record (PTR)</b>: A PTR record provides the IP address associated with a domain name. It does the exact opposite of an A record.

<b>Text record (TXT)</b>: A domain administrator will create TXT records to add notes to the DNS system for reference. In addition, these records can also contain data referencing other devices.

<b>Service record (SRV)</b>: An SRV record is configured to point to a specific host and port on which the resource is available, for example, instant messaging or voice-over IP services.

<b>Name Server record (NS)</b>: Name Server records are configured to indicate which DNS server is authoritative in the domain. It provides information on the domain’s IP address.
</p>

<p>Below I documented the process of how to install and configure a <b>DNS Server</b></p>

<h3>Install and Configure an Alternative <b>DNS Server</b></h3>

<p>In the Server Manager window, select Add roles and features.</p>

![DCHP Server Lab](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/1a39925a-fd95-4b05-9ca1-4d081da250f8)

<p>In the Add Roles and Features Wizard window, see <b>Before You Begin</b> in a larger font. At the bottom of the page, click Next.</p>

![Step 2](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/fbeec4ba-3da2-40d7-83ba-0adb1c406fef)

<p>Leave the default selection and click <b>bext</b> on the Select installation type page</p>

![Step 3](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/7c2dac68-1327-4310-a4c7-b8fdb9fba4a4)

<p>In the Select destination server page, leave the default selection and click Next.</p>

![Destination Server](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/f3080086-8007-492e-a899-6da461b14a45)

<p>Enable the DNS Server checkbox.

![Select Server Roles](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/37ee022b-b95a-4f58-ac43-dcc383ce2794)
  
In the Add Roles and Features Wizard pop-up window, click <b>Add Features.</b></p>

<img width="633" alt="add features" src="https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/c4f3b95b-3f80-4490-aaee-01b6969bdc50">


<p> In the Select features page, leave the default selection and click <b>Next</b>. </p>

![Select Features](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/cbcd66be-01b7-4d96-8222-b1eac7bb4be4)

On the DNS Server page, review the content and click <b>Next<b/>.

![Step DNS server](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/c7bda645-8785-42ae-a578-4df1429b3543)

<p>Click <b>Install</b> on the <b>Confirm installation</b>selections page.

<i><h4>Note:</h4> The installation might take a couple of minutes to complete.</i></p>

<p><b>After the installation has been completed, click Close in the Installation progress window.</b></p>


![Step 5](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/f3b4e1c6-6be7-4ff7-a066-2ad5e40d2e2e)

<p><h4>Part 2 - Configuring an Additional DNS Server</h4>
In an internal network, it is best practice to configure an additional <b>DNS server</b>. This is to ensure high-availability and fault tolerance for the server.


In this task, an additional <b>DNS Server</b> will be configured for the internal network.</p>


<p>
  On the Server Manager window, click <b>Tools</b> and select <b>DNS</b>.
</p>

![Step 6](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/8c070a64-62ca-44fd-aa9f-1574c8bf0628)



<p>On the <b>DNS Manager</b> window, expand <b>Forward Lookup Zones</b>.
  
Right-click PRACTICELABS.COM and select <b>Properties</b>.</p>

<img width="472" alt="forward lookup zones 2" src="https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/8d7a2d2f-9192-4c56-b3a3-0f787a7cbaef">

<p>In the PRACTICELABS.COM Properties dialog box, select the <b>Zone Transfers tab</b></p>

![allow zone transfers](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/03616897-c023-46a9-9d28-941bba701818)

<p>Enable the <b>Allow zone transfers</b> checkbox.

Leave the default settings and click OK.</p>

![allow zone transfers 1](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/aa95b8c7-f0c4-4041-8367-4d023bd319d5)

<p>Close the DNS Manager window</p>

<img width="422" alt="close dns manager window 1" src="https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/d3ef90c6-e8f5-4bca-8f39-5e1d21c922e2">

<h3>We're Almost finished! Return to your original DNS Server
</h3>
<p></p>On the Server Manager window, click <b>Tools</b>and select <b>DNS</b>.</p>

![original window - tools](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/0d1715eb-0cf5-4fe5-a9f3-246214612a08)

<p>On the <b>DNS</b>Manager window, right-click DNS and select Connect to <b>DNS Server</b></p>

![connect to server](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/1241013f-8600-440a-b0cb-6b6c5f545976)

<p>On the Connect to <b>DNS Server</b> dialog box, select The following computer radio button.

Enter an  IP address and click OK </p>

<img width="634" alt="CONNECT TO DNS SERVER RADIO BUTTON" src="https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/d335348d-48d8-4bd0-afcc-e281645ed774">

<p><b>note: The IP address specified for the existing DNS server is the Domain Controller on the internal network, which has already been set up as a DNS server. It might take a couple of minutes to resolve the IP address.</b></p>



<p>Click the IP address you entered in the <b>DNS</b> Manager window.</p>

<img width="440" alt="click the ip address you selected in the server window" src="https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/27eed37a-b025-4674-be3c-4ebc9815a05b">

<p>
  <b>
    <i> Note: By selecting the added DNS server, the DNS records of the server can be viewed. It might take a couple of minutes to replicate the content. The replicated DNS records are read-only.</i>
  </b>
</p

  Right-click terminal name and select New-Zone...

<img width="440" alt="new zone " src="https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/968eb7d3-2ac3-4da8-a3e9-170aa056cd4c">



<p>In the New Zone Wizard pop-up window, click Next.</p>

![Right click on PLAB](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/dc0179ec-abdd-4b19-8e91-b7d8be77a3bd)

<p>In the New Zone Wizard > Zone Type page, select the Secondary zone radio button and click Next.</p>

![secondary zone](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/4e827b6f-f49e-4d15-9f2c-13f481c9c382)

<p>
  <i>
    <b> Note: By creating a Secondary DNs zone, the Primary DNS zone’s DNS records will be replicated to the secondary DNS zone. This will ensure high-availability for the DNS servers. </b>
  </i>
</p>

<p>Leave the default selection in the Forward or Reverse Lookup Zone page, and click Next.</p>

![Leave the default selection in the Forward or Reverse Lookup Zone page, and click Next](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/94c3088e-58d0-4d78-9042-44ef945072a5)

<p>
  Click Browse on the Zone Name page.
</p>

<img width="382" alt="browse on the zone name" src="https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/19294898-dec8-4ff7-a521-e42ca9958361">


<p>Select your IP address and click OK in the Browse window.</p>

<img width="347" alt="browse window" src="https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/503b1c3c-5ebc-47ac-b21f-f21467905974">


<p>
  In the Browse window, select Forward Lookup Zones and click OK
</p>

<img width="437" alt="Select forward lookup tables" src="https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/f6c34fa8-c32d-4c5f-80d8-ce9d2dbf8686">


<p>
  Select 192.168.0.2 and click OK in the Browse window.
</p>

<img width="387" alt="select 192 168 0 2" src="https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/d16b2205-e676-4ac8-bc16-5f782c15cdef">


<p>
  Select Practicelabs.com in the Browse window and click OK.
(your PC  will say something different than "practicelabs.com"
</p>

<img width="478" alt="select practice labs" src="https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/57e4b33f-d21e-42ee-a50d-666bde4f3e96">

<p>
  Back in the Zone Name page, click Next.
</p>

<img width="449" alt="zone page click next" src="https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/35c4f1d0-6002-4d01-b5ae-724bdc9e7ca3">

<p>On the Master DNS Servers page, enter the following IP address in the Master Servers field and click Next.
</p>
<img width="446" alt="masters DNS servers" src="https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/36756594-5b3b-4f70-933a-17d809167ee6">

<p>Click Next in the New Zone Wizard > Completing the New Zone Wizard page. Then, click Finish.</p>

<img width="428" alt="complete zone wizard" src="https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/70399ce7-78ec-4f25-882a-4a7b4bcc569b">

<p>

Back on the DNS Manager window, expand your terminal dropdown > Forward Lookup Zones and select PRACTICELABS.COM.

  <i>

  <b> 
    Note: The Forward lookup zones have been successfully replicated to the new server. If the zones do not show, please refresh the page. This is a read-only copy of the primary server’s Forward lookup zone.
  </b>
  
  </i>
</p>




<img width="451" alt="forward lookup zones practice labs" src="https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/62aee84c-d98a-4d7a-a9f9-4e2dcf274c7b">


<p>
  Close DNS Manager.
</p>


<h4>The Last Part!</h4>

<p>
  <b>Configuring a DNS Record</b>
A DNS A Record can be added to the DNS server. These records can then be used by client computers to locate specific resources on the network. DNS records are created using a specific resource's IP address, then translated to a hostname, making it easier to locate the specific resource.

In this task, different DNS records will be configured on a DNS reserver.
</p>


<p>
  In <b>Server Manager</b>, select <b>Tools</b> and click <b>DNS</b>.
</p>


<img width="497" alt="original dns server" src="https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/0d2224ca-e65c-4aa1-9a81-ce0cc2d69b40">

<p>
  On the <b>DNS Manager</b> window, expand <b>Forward Lookup Zones</b> > <b>PRACTICELABS.COM</b>.
</p>

![On the DNS Manager window, expand Forward Lookup Zones](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/ac1ac589-a67f-49c0-ace1-234a32552d9d)

<p
  Right-click PRACTICELABS.COM and select New Host (A or AAAA)…
  </p>


<img width="604" alt="aa or aaaa" src="https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/1a339f44-f47f-4eee-a9ac-2e7ae7477fd0">
