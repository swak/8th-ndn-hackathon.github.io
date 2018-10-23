---
layout: page
title: Accepted Hacks
---

{::options toc_levels="2,3" /}

* TOC
{:toc}


## 1. Modernize ndn-js
  
Project Lead: Junxiao Shi (NIST)

Project Members: Mheni Merzouki (NIST), Omar Ilias El Mimouni (NIST)

### **[Slides](https://github.com/7th-ndn-hackathon/modernize-ndnjs/blob/master/README.md)**

**Targeted participant**
- People new to NDN code development

**How does your proposal benefit NDN?**
- ndn-js <https://github.com/named-data/ndn-js> is a JavaScript client library for Named Data Networking. It works with both NodeJS and browsers.

- The browser edition of ndn-js was developed in 2013. Since then, the JavaScript ecosystem has evolved greatly, but ndn-js has not been able to keep up.This causes several difficulties when integrating ndn-js in a modern JavaScript project.
This project is to modernize several aspects of ndn-js, so that it can work well in today's JavaScript ecosystem.

**Briefly describe the tasks**
1. Replace Waf build process with a modern bundler such as Brunch or Webpack.
   The goal is to allow a web application to `require("ndn-js")` and have the bundler do the rest.
   The ability of building a self-contained `ndn.js` must be preserved.
   If feasible, remove the copied dependencies in `contrib/`, and import them from NPM.
2. Provide TypeScript declaration file to enable type checking of ndn-js APIs in a TypeScript project.
   These commonly used classes should be given priority: `Name Name.Component Interest Data NetworkNack Blob Face`.
   Others may be declared as `any` type.
3. Add Promise-based APIs as an alternate to callback-based APIs.
   These functions need an alternate that returns a Promise: `Face.expressInterest Face.registerPrefix KeyChain.createIdentityV2`.
   These functions need an alternate that takes a callback whose return value is a Promise: `Face.setInterestFilter Face.registerPrefix`.
   
**Any specific tools or language**
- Participant must be able to write JavaScript

**Expected outcomes**
- Show the result of listed tasks in a simple web application.


## 2. Interest Buffering
  
Project Lead: Tianxiang Li (UCLA)

Project Members: Spyros Mastorakis (UCLA), Xinyu Ma, Klaus Schneider (Arizona)

### **[Slides](https://docs.google.com/presentation/d/1QwbaS0EZ-7x4FhmzX-5bhb5a0Z01EcetlbbXjvVR8zk/edit?usp=sharing)**

**Targeted participant**
- People new NDN code development 

**How does your proposal benefit NDN?**
- Enable support for Interest buffering and face signaling in NFD. Allows better forwarding strategies based on face status.

**Briefly describe the tasks**
- Allow Interest Buffering in PIT and enable face status signaling to determine whether to send out an Interest

**Any specific tools or language?**
- NFD, ndn-cxx, C++

**Expected outcomes**
- Enable support for Interest buffering and face signaling in NFD


## 3. Self-learning Forwarding Strategy: NFD Implementation and Testing
  
Project Lead: Teng Liang (Arizona)

Project Members: Md Ashiqur Rahman (Arizona), Ju Pan (Arizona)

### **[Slides](https://docs.google.com/presentation/d/15p6E4KOiw6iL3AhdDeeY-_k7pQgdqtQ9IgBI-Ob8k8w/edit#slide=id.p)**

**Targeted participant**  
- People with NDN code development experience

**How does your proposal benefit NDN?**  
- Self-learning is an important mechanism for NDN research/testing/deployment to achieve plug-and-play

**Briefly describe the tasks**  
- Finalize self-learning strategy implementation (redmine: #4279)
- Test self-learning with integration-testing
- Evaluate self-learning performance  

**Any specific tools or language?**
- C++, NFD development experience, or NDN-Android development experience

**Expected outcomes**  
- Working code that can be merged to NFD
- Evaluation results



## 4. Fractalide - An NDN Browser
  
Project Lead: Stewart Mackenzie (Fractalide)

Project Members: Claes Wallin (Fractalide)

### **[Slides](https://github.com/7th-ndn-hackathon/rkt-ndn/blob/master/Team-Fractalide-rkt-ndn-7th-ndn-hackathon.pdf)**

**Targeted participant**
- People with NDN code development experience

**How does your proposal benefit NDN?**
- Just as TCP/IP became popular because of the HTTP browser so we hope NDN will become popular with an NDN browser

**Briefly describe the tasks**
- Fork this repository https://github.com/fractalide/rkt-ndn
- Build a racket language binding to Named Data Networking library

**Any specific tools or language**
- Racket FFI

**Expected outcomes**
- We’ll have a functional library that allows racket users to build on Named Data Networking


## 5. Mini-NDN documentation
  
Project Lead: Ashlesh Gawande (Memphis)

Project Members: Alexander Lane (Memphis)

### **[Slides](https://docs.google.com/presentation/d/1lK8g1_Njf6Sg9tystirL2W8IYtCmv8svS_6_YmM8cO0/edit#slide=id.g44acded8c6_2_55)**

**Targeted participant**
- People new to NDN code development

**How does your proposal benefit NDN?**
- Lower barrier to getting started with Mini-NDN

**Briefly describe the tasks**
- Choose a documentation standard and setup auto generation
- Identify what documentation can be updated and what needs to be added (look at mailing list)
- Verify + update existing doc and add new documentation

**Any specific tools or language**
- Mini-NDN, Mininet, Python, Probably Sphinx/Doxygen

**Expected outcomes**
- Updated documentation which is automatically mirrored to the website


## 6. 3D Visualization of NDN Traffic
  
Project Lead: Alexander Monaco (FIU)

Project Members: Alex Afanasyev (FIU), Tarannum Islam (FIU), Rajender Kumar (FIU)


### **[Slides](https://www.dropbox.com/s/1g1jpigkm8hrxip/3d-viz.pptx?dl=0)**

**Targeted participant**
- People new to NDN code development

**How does your proposal benefit NDN?**
- The understanding of traffic flow is important in development of resilient network tools. 3D NDN Visualization could aid in providing a more efficient method of analyzing and interpreting traffic data. 

**Briefly describe the tasks**
- Investigate existing tools for identifying and analyzing network traffic, use available network data to evaluate promising tools, and attempt to create a visualization using the output of these tools.

**Any specific tools or language**
- Since the visualization will be developed using the Unity engine, the main language that will be used will be C#

**Expected outcomes**
- A simple visualization that can be further developed into a working 3D visualization prototype. 



## 7. Refactor encoding and decoding in NDN-RIOT and make it more usable to developers
  
Project Lead: Zhiyi Zhang

Project Members: Tianyuan Yu, Bo Chen, Weijia Yuan

### **[Slides](https://docs.google.com/presentation/d/1kCr13NbT7H3d1QO7VyV69-Jrg6gh86uD79ZJ2Wn_BMQ/edit#slide=id.g44ad830ee9_2_75)**

**Targeted participant**
- People with NDN code development experience

**How does your proposal benefit NDN?**
- Make NDN-RIOT a better library to use

**Briefly describe the tasks**
- We already re-implemented the basic block 0.3 encoding/decoding APIs, name APIs, Interest APIs. Refactor other modules (Data, Certificate, etc.)

**Any specific tools or language**
- C

**Expected outcomes**
- Unit tests to show everything is fine


## 8. Named Reddit
  
Project Lead: Ernest McCracken (Memphis)

Project Members: Tianxing Ma (Memphis), Saurab Dulal (Memphis)

### **[Slides](https://docs.google.com/presentation/d/10B7US38NbLciBemyKgiwclUHHaYQJR7zFAR0nXt1B08/edit#slide=id.p)**

**Targeted participant**
- People new to NDN code development

**How does your proposal benefit NDN?**
- Contribution to web based browsing of NDN supported content

**Briefly describe the tasks**
- Web front end portal, React server serving static web content as well as servicing ndn-js requests.  Support for simple API commands.

**Any specific tools or language**
- html, reactJS, ndn-js, json based db

**Expected outcomes**
- A web application that enables reddit style posts as well as supporting a hierarchy of sub reddits instead of just a single level.


## <del>~~Certificate Support in esp8266ndn Library~~</del>
  
Project Lead: Junxiao Shi

**[Slides](https://github.com/7th-ndn-hackathon/7th-ndn-hackathon.github.io/blob/source/_assets/files/pitch-slides%20-%20Junxiao%20Shi%20(3)%20-%201.pdf)**

**Targeted participant**
- People new to NDN code development

**How does your proposal benefit NDN?**

- esp8266ndn <https://github.com/yoursunny/esp8266ndn> is an Arduino library that supports NDN application development on ESP8266 and ESP32 microcontrollers.
University of Memphis and NIST each has a building sensing deployment utilizing this library.

- So far esp8266ndn supports HMAC and EC signing and verification, but the application must provide uncompressed key bits.
This project adds a NDN Certificate v2 <https://named-data.net/doc/ndn-cxx/current/specs/certificate-format.html> decoder and encoder to the esp8266ndn library, paving the way of implementing trust schema, ndncert-client, and secure device onboarding in the future.

**Briefly describe the tasks**

1. Study the encoding format (including common variations if any) of X509PublicKeyContent used in NDN Certificate.
2. Implement or adapt an ASN.1 encoder and decoder for ESP8266/ESP32 Arduino.
3. Implement a NDN Certificate decoder to extract public key and validity period from a `DataLite` instance.
4. Implement a NDN Certificate encoder to create a `DataLite` from name, public key, and validity period, and then sign it with an existing `EcPrivateKey`.

**Any specific tools or language**
- Participant must have access to one ESP8266 or ESP32 microcontroller.
- Participant must have access to a 2.4GHz WiFi network and an NFD node on this network. 
- Participant should be able to read ndn-cxx code related to certificates.


**Expected outcomes**
- Certificate decoder demo:

    1. Operator enters a Data name through serial console.
    2. Microcontroller retrieves the Data packet.
    3. Microcontroller follows KeyLocator to retrieve the certificate.
    4. Microcontroller decodes the certificate and verifies the Data packet against the public key embedded in the certificate, and then prints verification result on the serial console.

- Certificate encoder demo:

    1. Upon startup, microcontroller generates an EC key pair and a self-signed certificate.
    2. Operator executes a consumer program on the computer (written in ndn-cxx or PyNDN or similar) to retrieve microcontroller's certificate and a Data packet signed by its private key.
    3. The consumer program decodes the certificate and verifies the Data packet against the public key embedded in the certificate, and then prints verification result on standard output.

## <del>Tiny Forwarder with esp8266ndn Library</del>
  
Project Lead: Junxiao Shi

**[Slides](https://github.com/7th-ndn-hackathon/7th-ndn-hackathon.github.io/blob/source/_assets/files/pitch-slides%20-%20Junxiao%20Shi%20(3)%20-%202.pdf)**

**Targeted participant**
- People with NDN code development experience

**How does your proposal benefit NDN?**

- esp8266ndn <https://github.com/yoursunny/esp8266ndn> is an Arduino library that supports NDN application development on ESP8266 and ESP32 microcontrollers. University of Memphis and NIST each has a building sensing deployment utilizing this library. In both systems, the sensor nodes is one hop away from an NFD node.

- This project explores a specific design of a tiny forwarder on the ESP8266/ESP32 microcontrollers.
Given the memory constraint, this tiny forwarder uses per-face Bloom filters as the Pending Interest Table (PIT), instead of a regular name-based PIT. It sacrifices preciseness of PIT name matching and InterestLifetime, in exchange for lower memory requirement.

- If this design is proven to be successful, building sensing deployments can reduce dependency on the infrastructure network.
In the future, it's also possible to port the same design to NDN-RIOT.

**Briefly describe the tasks**

1. Implement a PIT based on per-face Bloom filters, using hsip-bf library <https://github.com/yoursunny/hsip-bf>.
2. Create several faces. The easiest way is to run the forwarder node in AP mode, and have four unicast UDP faces.
3. Implement a tiny forwarder. For simplicity, the FIB is hard-coded.
4. (optional) Replace hard-coded FIB with simple self-learning.
5. Through theoretical analysis as well as experiments, find out efficiency of the tiny forwarder: how much excess traffic is caused by impreciseness of PIT name matching and InterestLifetime.

**Any specific tools or language**
- Participant must have access to one ESP8266 or ESP32 microcontroller. 
- Participant must have access to three or more WiFi-capable NDN end hosts. These can be computers or microcontrollers.

**Expected outcomes**
- Tiny forwarder demo:

    1. Each end host runs a producer and several consumers retrieving from other producers.
    2. If the participant has a WiFi NIC capable of monitor mode, show how the forwarder works via WiFi monitoring. Otherwise, show how the forwarder works using serial console logs.
    

## <del>HMAC and Merkle-Hash-Tree Signatures in ndn-cxx</del>
  
Project Lead: Junxiao Shi

**[Slides](https://github.com/7th-ndn-hackathon/7th-ndn-hackathon.github.io/blob/source/_assets/files/pitch-slides%20-%20Junxiao%20Shi%20(3)%20-%203.pdf)**

**Targeted participant**
- People new to NDN code development

**How does your proposal benefit NDN?**
- SignatureHmacWithSha256 is one of the signature types defined in NDN Packet Format. It ensures provenance that the Data packet was signed by one of the parties who holds the shared key. Common Client Libraries (CCL) support this signature type, but ndn-cxx does not.

- SHA-256-Merkle-Hash-Tree is a signature type defined in CCNx 0 packet format <https://web.archive.org/web/20150226084828/http://www.ccnx.org:80/releases/latest/doc/technical/SignatureGeneration.html>.
With this signature type, when a producer creates multiple Data packets, it only needs to perform expensive RSA or EC signing once.Each Data packet carrying a Merkle hash tree aggregated signature is individually verifiable and does not require retrieving a separate catalog/manifest packet.

- This project adds SignatureHmacWithSha256 to ndn-cxx, so that it can better interoperate with CCL. This project also explores Merkle hash tree aggregated signing.

**Briefly describe the tasks**
1. Create SignatureHmacWithSha256 wire format encoder and decoder.
2. Add SignatureHmacWithSha256 signing procedure to KeyChain.
3. Add SignatureHmacWithSha256 validation procedure to Validator.
4. Design wire format for Merkle hash tree aggregated signature.
5. Create Merkle hash tree aggregated signature wire format encoder and decoder.
6. Add Merkle hash tree aggregated signing procedure to KeyChain.
7. Add Merkle hash tree signature validation procedure to Validator.

**Any specific tools or language**
- Participant must understand crypto including HMAC, hash, and asymetric signing. 
- Participant must be able to write C++14.

**Expected outcomes**
- Show the result of listed tasks in two simple console programs.


## <del>NDN File System without FUSE</del>
  
Project Lead: Junxiao Shi

**[Slides](https://github.com/7th-ndn-hackathon/7th-ndn-hackathon.github.io/blob/source/_assets/files/pitch-slides%20-%20Junxiao%20Shi%20(3)%20-%204.pdf)**

**Targeted participant**
- People with NDN code development experience

**How does your proposal benefit NDN?**
- NDNFS <https://github.com/remap/ndnfs-port> is an "NDN-friendly file system".
- The NDNFS daemon creates a FUSE mountpoint. When a file is added under this FUSE mountpoint, it internally segments the file into Data packets and generates signatures. These Data packets can then be served over the network. This method causes difficulty in serving large number of existing files because they must be copied into FUSE, and has several bugs when files are added via SFTP.

- This project explores a different kind of NDN File System. Instead of using FUSE, the program works with an existing folder on the filesystem. When an Interest arrives, it segments and signs the Data on the fly, and caches the signature. The user experience is similar to `python3 -m http.server`

**Briefly describe the tasks**
1. Develop a daemon program that serves files in the current working directory.
   Assuming the files do not change, the Data packets can used a fixed version number.
   Files should be retrievable with `ndncatchunks` using fixed version discovery.
2. Add signature caching to reduce signing overhead.
3. Add directory listing feature using a simple protocol, and develop a client program to retrieve directory listing.
4. Add Realtime Data Retrieval protocol support to accomodate file updates.
   Files should be retrievable with `ndncatchunks` using RDR version discovery method; in case this discovery method isn't available at time of project, the participant would have to develop a ndn-tools patch for this.
5. Develop systemd service file for the daemon.

**Any specific tools or language**
- Participant must be familiar with either ndn-cxx or Common Client Libraries

**Expected outcomes**
- Show the result of listed tasks in simple console applications.

## <del>Packet03, Data Synchronization, and More in repo-sql</del>
  
Project Lead: Junxiao Shi

**[Slides](https://github.com/7th-ndn-hackathon/7th-ndn-hackathon.github.io/blob/source/_assets/files/pitch-slides%20-%20Junxiao%20Shi%20(3)%20-%206.pdf)**

**Targeted participant**
- People with NDN code development experience

**How does your proposal benefit NDN?**
- repo-sql <https://github.com/3rd-ndn-hackathon/repo-sql> is an alternate NDN repository implementation backed by a SQL database. It was developed in 3rd NDN Hackathon, and is still being maintained. Two years later, it is in need of a refresh.

- This project switches repo-sql to use NDN Packet Format 0.3 (packet03), which greatly simplifies the QueryProcessor. Also, repo-sql can have Data synchronization using the C++ PSync library.

**Briefly describe the tasks**
1. Redesign database schema and query procedure for packet03.
   Database migration script is optional.
2. Implement `QueryProcessor` with the redesigned query procedure.
3. Add TCP bulk insertion feature.
4. Add Data insertion command <https://redmine.named-data.net/projects/repo-ng/wiki/Basic_Repo_Insertion_Protocol>.
5. Develop a data synchronization mechanism.
   The primary repo-sql instance has all the Data, and applications should only write to the primary instance.
   Secondary repo-sql instances mirrors a subset of stored Data under one or more specified name prefixes using PSync.
   This is a one-way mirroring at this stage: the secondary instances do not allow direct insertion.
   
**Any specific tools or language**
- Participant must know ndn-cxx.

**Expected outcomes**
- Show the result of listed tasks in the console.

## <del>Broadcast and ad-hoc faces in NFD for ad-hoc wireless networks.</del>
  
Project Lead: Md Ashiqur Rahman

**[Slides](https://github.com/7th-ndn-hackathon/7th-ndn-hackathon.github.io/blob/source/_assets/files/Ashiq_ad-hoc%20-%20Md%20Ashiqur%20Rahman.pdf)**

**Targeted participant**
- People with NDN code development experience

**How does your proposal benefit NDN?**
- Current NFD does not support broadcast and ad hoc wireless faces which would be helpful for working in ad-hoc networks.

**Briefly describe the tasks**
1. NDN self-learning is initially defined for point-to-point links only. An important scenario for NDN self-learning in NFD is on wireless channels, such as ad-hoc WiFi networks among Android devices.
2. Thus, the protocol definition shall be extended to support broadcast and ad hoc wireless faces.

**Any specific tools or language**
- NFD, ndn-cxx, C++

**Expected outcomes**
- To have support for broadcast and wireless ad-hoc faces in NFD.

## <del>NDN sign-on protocol implementation over BLE</del>

Project Lead: Yanbiao Li

**[Slides](https://github.com/7th-ndn-hackathon/7th-ndn-hackathon.github.io/blob/source/_assets/files/ndn-hackathon-SignOn-BLE%20-%20Yanbiao%20Li.pdf)**

**Targeted participant**
- People with NDN code development experience

**How does your proposal benefit NDN?**
- Enable to deploy NDN-IoT package on more boards

**Briefly describe the tasks**
- Implement NDN sign-on protocol with an android phone and a nRF58240 board  

**Any specific tools or language?**
- java, C/C++

**Expected outcomes**
- sign-on over BLE
  
## <del>A use-case example APP using NDN-IoT package</del>
  
Project Lead: Yanbiao Li

**[Slides](https://github.com/7th-ndn-hackathon/7th-ndn-hackathon.github.io/blob/source/_assets/files/ndn-hackathon-IoT-App%20-%20Yanbiao%20Li.pdf)**

**Targeted participant**
- People with NDN code development experience

**How does your proposal benefit NDN?**
- help to release the NDN-IoT package

**Briefly describe the tasks**
- develop the two ends (controller and device) of a simple smart home APP

**Any specific tools or language?**
- Java, C/C++, python

**Expected outcomes**
- The Controller App on phone and the Device App on nRF85240 boards

## <del>Development of Yang Data Model for NFD Mgmt. Protocol</del>
  
Project Lead: Rajender Kumar

**[Slides](https://github.com/7th-ndn-hackathon/7th-ndn-hackathon.github.io/blob/source/_assets/files/Yang_data_Model_NDN%20-%20Rajender%20Kumar.pdf)**

**Targeted participant**
- People new NDN code development

**How does your proposal benefit NDN?**
- Yang data model will help in the development of a network management protocol for NDN.
- Yang data model is extensible (equipment manufacturer and network manager can augment the current model with new data or operation).

**Briefly describe the tasks**
- Identification of different operation, attributes and other information related to NFD mgmt. protocol.
- Development of Yang data model for current NFD management protocol.

**Any specific tools or language**
- Yang Data modeling Language, NFD Management Protocol

**Expected outcomes**
- Yang data model for current NFD management protocol

## <del>Contribute to NDN IoT</del>
  
Project Lead: Zhiyi Zhang

**Targeted participant**
- People with NDN code development experience

**How does your proposal benefit NDN?**
- Provide better support of NDN in IoT scenarios

**Briefly describe the tasks**
- Implement the missing features in existing codebase and required features that have not been realized yet.

**Any specific tools or language**
- C

**Expected outcomes**
- Live Demo to show the system work.


## <del>Make NDN-RIOT + NDN-IoT pkg work on NRF52840</del>
  
Project Lead: Zhiyi Zhang

**[Slides](https://github.com/7th-ndn-hackathon/7th-ndn-hackathon.github.io/blob/source/_assets/files/nrf52840%20-%20Zhiyi%20Zhang.pdf)**

**Targeted participant**
- People with NDN code development experience

**How does your proposal benefit NDN?**
- Let the existing service discovery and access control protocol function
on the new boards

**Briefly describe the tasks**
- Debug any possible bugs when we deploy NDN-RIOT on the new boards

**Any specific tools or language**
- C

**Expected outcomes**
- Have two nrf52840 boards talk to each other and have a live demo


## <del>An Android App to visualize the workflow in IoT</del>
  
Project Lead: Zhiyi Zhang

**[Slides](https://github.com/7th-ndn-hackathon/7th-ndn-hackathon.github.io/blob/source/_assets/files/android%20-%20Zhiyi%20Zhang.pdf)**

**Targeted participant**
- People with NDN code development experience

**How does your proposal benefit NDN?**
- Visualize the workflow in NDN IoT scenarios.

**Briefly describe the tasks**
- Develop a simple android app to work with NDN-RIOT system to get the status and workflow of each node in the system.

**Any specific tools or language**
- Android (Java)

**Expected outcomes**
- Live demo to show the app can visualize the status


## <del>Schematized Trust in NDN-IoT</del>
  
Project Lead: Zhiyi Zhang

**[Slides](https://github.com/7th-ndn-hackathon/7th-ndn-hackathon.github.io/blob/source/_assets/files/schematized_trust%20-%20Zhiyi%20Zhang.pdf)**

**Targeted participant**
- People with NDN code development experience

**How does your proposal benefit NDN?**
- Achieve trust and more fine-grained authentication in NDN IoT scenarios.

**Briefly describe the tasks**
- Implement a simplified version of trust schema in NDN-RIOT

**Any specific tools or language**
- C

**Expected outcomes**
- A live demo to show the difference of whether to have a trust policy or not.


