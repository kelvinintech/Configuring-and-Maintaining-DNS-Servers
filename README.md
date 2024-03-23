# Configuring-and-Maintaining-DNS-Servers

Hey Friends! <a href="https://www.instagram.com/kelvinintech"><b>@Kelvinintech</b></a>here 👋🏽👋🏽

<p>I developed a project showing how to configure and maintain a DNS Server</p>

<p>If you're like me, in 2022, who had no idea what DNS, DHCP or even Github were🤣, here's a breakdown</p>

<p>

A <b>DNS server</b> is a specialized computer server that stores a database of domain names and their corresponding IP addresses. When a device needs to translate a domain name (like www.example.com) into an IP address (like 192.0.2.1), it sends a request to a DNS server. The DNS server then looks up the domain name in its database and responds with the corresponding IP address.
</p>

<p>Make sense? </p>


![this-is-so-strange-frederick-alexander-pye](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/baa8002c-791b-4f94-ad95-d65142be1557)

<p><b><i>Here's another explanation</i></b></p>

<p>
  
Imagine a DNS server as a big directory or phonebook. <b>Remember those? 🤣</b> 
It contains a list of domain names (like www.example.com) and their corresponding phone numbers (IP addresses).
When you want to visit a website (like www.example.com), your device asks the DNS server for the website's IP address.
The DNS server looks up the IP address associated with the domain name and tells your device where to go.
</p>



<p>

  When a <b>DNS server</b> is configured, depending on the need, additional DNS server and functionality can be configured for the hierarchy of the network these include the following:

<b>Root DNS Servers</b>: Root DNS servers' essential functionality is the translation of hostnames to IP addresses and provides answers to queries from devices on the network.

<b>Internal & External DNS Servers</b>: An internal DNS server will be hosted inside of the network and will only be accessible for internally connected devices. An external DNS server can be configured on the same network and handle only external requests. If an internal DNS server gets a request from an internal device and can not resolve it, the internal DNS server will contact the external DNS server to resolve the specific request.

<b>Authoritative name servers</b>: Authorative name servers contain specific information of the domain where it is located and are normally the last point of contact to resolve an IP address to a hostname.

<b>DNS caching & Time to live configuration</b>: DNS caching is a temporary database stored on a client machine. This database contains records of the recently visited sites and resources by the user. Time to live (TTL) is the time specified for how long a specific record should be stored on a server before it will be removed.

<b>Recursive lookup</b>: Recursive DNS queries are used when a DNS server queries other DNS servers on the network to determine the location of a specific IP address of a resource on the network.

The different record types can be configured on a DNS server to facilitate communication and access to resources located on the network. These records include the following:

<b>Canonical name (CNAME)</b>: CNAME records are used in conjunction with A records in a DNS system and are configured to point to the domain and never to an IP address. It can be used to set up aliases for resources on the network.

<b>Mail Exchange Record (MX record)</b>: MX records are configured on a DNS server to specify an SMTP server for the specific domain. These records are used to route outgoing emails to a mail server.

<b>Start of Authority (SOA)</b>: These records are part of the DNS Zone file and specify the Authoritative Name Server for the DNS zone. The details for the domain administrator and how often the DNS information needs to be updated are also part of these records.

<b>Pointer record (PTR)</b>: A PTR record provides the IP address associated with a domain name. It does the exact opposite of an A record.

<b>Text record (TXT)</b>: A domain administrator will create TXT records to add notes to the DNS system for reference. In addition, these records can also contain data referencing other devices.

<b>Service record (SRV)</b>: An SRV record is configured to point to a specific host and port on which the resource is available, for example, instant messaging or voice-over IP services.

<b>Name Server record (NS)</b>: Name Server records are configured to indicate which DNS server is authoritative in the domain. It provides information on the domain’s IP address.
</p>


<p>Below I documented the process of how to and configure a DNS Server</p>

<h3>Install and Configure an Alternative DNS Server</h3>


![DCHP Server Lab](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/1a39925a-fd95-4b05-9ca1-4d081da250f8)
![Step 2](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/fbeec4ba-3da2-40d7-83ba-0adb1c406fef)
![Step 3](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/7c2dac68-1327-4310-a4c7-b8fdb9fba4a4)
![Destination Server](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/f3080086-8007-492e-a899-6da461b14a45)
![Select Server Roles](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/37ee022b-b95a-4f58-ac43-dcc383ce2794)
![Select Features](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/cbcd66be-01b7-4d96-8222-b1eac7bb4be4)
![Step DNS server](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/c7bda645-8785-42ae-a578-4df1429b3543)
![Step 5](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/f3b4e1c6-6be7-4ff7-a066-2ad5e40d2e2e)

![Step 6](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/8c070a64-62ca-44fd-aa9f-1574c8bf0628)
![Step 7](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/d30bf25b-e1f6-4c67-85f8-b4297e716f71)


![allow zone transfers](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/03616897-c023-46a9-9d28-941bba701818)
![close dns manager window](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/20a4fe40-28d0-4b1b-bf46-c3a4cd3e3ca4)
![original window - tools](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/c4bff874-1a10-45dd-a2b6-352746214e31)
![connect to server](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/1241013f-8600-440a-b0cb-6b6c5f545976)
![Enter an IP address 2](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/32ec4b48-8df1-4303-8adb-6b527f402e40)
<p>In the New Zone Wizard pop-up window, click Next.</p>

![Right click on PLAB](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/dc0179ec-abdd-4b19-8e91-b7d8be77a3bd)

<p>In the New Zone Wizard > Zone Type page, select the Secondary zone radio button and click Next.</p>

![secondary zone](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/4e827b6f-f49e-4d15-9f2c-13f481c9c382)

<p>Leave the default selection in the Forward or Reverse Lookup Zone page, and click Next.</p>

![Leave the default selection in the Forward or Reverse Lookup Zone page, and click Next](https://github.com/kelvinintech/Configuring-and-Maintaining-DNS-Servers/assets/110644520/94c3088e-58d0-4d78-9042-44ef945072a5)
