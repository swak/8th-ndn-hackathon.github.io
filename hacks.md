---
layout: page
title: Accepted Hacks
---

{::options toc_levels="2" /}

* TOC
{:toc}

[Project Pitches]({% asset_path project-pitches.pdf %})

## 1. <del>ndnSIM analysis/illustration tools for collected metrics</del>

Lead: Spyros Mastorakis

ndnSIM currently relies mostly on tracers for the collection of simulation/network metrics. However, the tracers typically generate very large output files, which are very hard for users to read. Therefore, these files require post-processing/offline analysis (e.g., using some R or python script). As of now, we provide a couple of sample R scripts on the ndnSIM website (http://ndnsim.net/2.4/metric.html), however, more scripts are required to allow for further metric analysis and illustration flexibility.

**Tasks to accomplish**

- Create a number of scripts (e.g., in R or python, etc.) that would enable further flexibility during the analysis of tracers' output files. The scripts should also automate the illustration of the analyzed metrics (e.g., by using ggplot2, numpy, etc.)
- Submit the scripts to Gerrit for review (the goal is to get them merged to the master branch ASAP).
- Demonstration of the illustration to the hackathon committee. 

**Knowledge Requirements**

ndnSIM, python or R, C++.

**Expected Outcome**

A set of scripts to automate the analysis and illustration of metrics collected using the ndnSIM tracers.

---

## 2. Demonstration of latest NFD features in ndnSIM

Lead: Spyros Mastorakis

**Problem Statement**

Since ndnSIM 2.0, ndnSIM is integrated with the real NDN prototypes (NFD and ndn-cxx). Lately, new features have been added to NFD (e.g., packet fragmentation and reassembly, congestion control, ad-hoc faces). The goal of this project is to create ndnSIM simulation scenarios and ndnSIM-specific (NS-3-based) or real world applications (if needed) to demonstrate those features. This project would be very useful for the ndnSIM community, since there will be ready-to-use pieces of code for the users to experiment with the new NFD features.

**Tasks to accomplish**

- Create a set of ndnSIS simulation scenarios, applications and make all the changes needed to ndnSIM, so that newly added NFD features can be used (e.g., packet fragmentation and reassembly, congestion control, ad-hoc faces and any other the developers might consider important and useful)
- Create some related documentation, so that we can add the created code on the ndnSIM website
- Submit the code to Gerrit for review (the goal is to get them merged to the master branch ASAP)

**Knowledge Requirements**

ndnSIM, NFD, ndn-cxx, C++.

**Expected Outcome**

A set of simulation scenarios, applications and any other changes needed.

---

## 3. Firefly: A globally scalable message bus with NDN at the edge 

Project Leads: Jeff Burke, Jeff Thompson 

**Summary  / Contribution**

This project aims to design and demonstrate a scalable, fault-tolerant message bus for mobile applications that uses native Named Data Networking (NDN) communication for robust and disruption tolerant communication at the edge, while employing a cloud-hosted, best-in-class "real-time database", Google Firebase, as its core transport.  The project will be implemented in a demonstration application with a Unity client on an Android mobile phone and a web application.

**Problem statement**

Sync, repo, prefix registration and publisher mobility support are still research topics and implementations are in early stages.   At the same time, apps deploying over existing, TCP/IP based distributed messaging and database platforms still face limitations due to IP, such as difficulty leveraging multiple interfaces and broadcast channels in local networks, and providing  a data-centric security model.  

**Approach**

This project explores what is possible if higher-level functionality envisioned for NDN is made available (for some slice of use cases) globally and robustly, by using Firebase as a transport for NDN data and if NDN is used to provide robust and flexible communication between nodes at the edge.  

We will design and implement a bridge between NDN and Google Firebase's Real-time Database service (and other components if necessary), an arbitrary number of instances of which can be run on a local NDN network to provide persistent storage and sync with other NDN edge networks. Client libraries will be provided in the NDN-CCL that follow the format of or directly duplicate APIs for prefix registration, repo storage, and sync.

NDN signatures and verification will be supported by storing the wire format as well as decoded messages (using Firebase as a transport layer).   Named data  objects will be immutable and mapped to into Firebase's hierarchical namespace.

**Planned Tasks To Accomplish**

- Create necessary accounts, sample databases, API keys, etc. for using Firebase (before the hackathon) 
- Design mapping between Firebase and NDN namespaces and data formats (sketched before hackathon)
- Develop bridge process for linking a local NDN network with a Firebase store
- Implement client code on ndn-dot-net and ndn-js 
- Develop sample application, probably inspired by IoT and AR experiments already underway by NDN team

**Knowledge Requirements**

- Basic understanding of NDN including interest/data exchange, synchronization.
- Familiarity with at least one of the following languages, including how to use external libraries and write event-driven code: C#, NDN-JS, and Python.
- Helpful: Understanding of NoSQL databases

**Expected Outcome**

- Demonstration application 
- Prototype library using firebase to provide sync (and other derived features) to NDN apps
- Insight into potential opportunities to extend "pure NDN" sync, storage, and routing to meet application needs

---

## 4. NDN Stack for ESP8266 Microcontroller

Project Lead: Ashlesh Gawande

**Motivation**

The ESP8266 is a low-cost WiFi chip with full TCP/IP stack and microcontroller capability. It supports 802.11bgn WiFi at 2.4GHz, features a 80MHz 32-bit CPU with 96KB of data RAM, and has GPIO pins, analog input, and other ports. At an unbeatable price point of USD $3, it is one of the most popular microcontroller chips among western makers.

The ESP8266 can be programmed with the Arduino IDE. We have ported ndn-cpp-lite to the ESP8266, and packaged it as an Arduino library, available at https://github.com/yoursunny/esp8266ndn.

This project is to add more features into the esp8266ndn library, and develop some applications to demonstrate the power of combining ESP8266 and NDN.

**Contribution to NDN**

Allow NDN to operate on the ESP8266 microcontroller, a popular chip among western makers.

**Tasks**

- Prefix registration with HMAC: Implement prefix registration on ESP8266 with HMAC signatures. Either develop an ndn-cxx Validator to validate HMAC signatures and integrate this Validator into NFD-RIB, or develop a proxy application (with any library) to accept such commands and send an RSA-signed prefix registration command to NFD-RIB; this program runs on a regular computer.
- ECDSA signing and verification via micro-ecc: Determine the correct parameters to initialize micro-ecc library, so that the signatures generated by ndn-cxx can be verified with micro-ecc, and vice versa; this step can be done on a regular computer. Port micro-ecc onto the ESP8266.
- Prefix registration with ECDSA: Implement prefix registration on ESP8266 with ECDSA signatures. This shall  be compatible with regular NFD with ECDSA verification enabled.
- Nack: Add features to send and receive network Nacks.
- Demo applications: See "expected outcome" section.

**Required Knowledge for Participants**

- General knowledge about signed Interests
- C++11, ndn-cxx or ndn-cpp-lite API
- a computer capable of running the Arduino IDE: most Windows/Linux/macOS laptops with a full-size USB
- port will work fine
- a computer capable of running NFD: this can be a virtual machine

The project leader will have at least 3 ESP8266 units (Wemos D1 mini boards) for this project, and can explain most of the existing code of esp8266ndn library. Maximum team size is 3.

**Expected Outcome**

- Prefix registration and Nack demo: ping server Use an ESP8266 unit with one LED, a computer with patched Validator or proxy application. The ESP8266 registers its prefix onto the NFD using HMAC. The computer  can ndnping the prefix of ESP8266. The ESP8266 blinks its LED each time a ping request is processed. If     the computer sends an Interest not served by the ndnping server, the ESP8266 should respond with a Nack.
- ECDSA demo: light Use an ESP8266 unit with two LEDs, and a computer with regular NFD. The ESP8266 registers its prefix onto the NFD using ECDSA. A simple program on the computer sends a signed Interest  with ECDSA to the ESP8266. The ESP8266 verifies the signature, and then blinks blue LED if signature is valid, or blinks red LED if signature is invalid.

---

## 5. NDN with Docker

Project Lead: Haitao Zhang

**Motivation**

One big roadblock for people to try NDN are the troublesome operations of downloading, compiling, installation, and configuration.
Docker is an open platform for developers and sysadmins to build, ship, and run distributed applications, whether on laptops, data center VMs, or the cloud. Executable applications and well-configured environment are directly packed into a container. Given most OS supports docker and docker is lightweight in size, docker is a very good carrier of NDN stack.
By packing the NDN stack into the docker container, all OSs that support docker can talk in NDN by installing our conatiner, and users don't bother to compile/install/config this and that.

**Contribution to NDN**

- Make most operating systems (including Windows) able to send/receive NDN packets
- Users can simply install the container and don't bother to compile/install/config

Those will definitely help to enlarge the NDN community and encourage more people to try NDN.

**Tasks**

- Preparation: Learn how to use Docker and make Docker container.
- Main part: Pack well-configured ndn-cxx, NFD, ndncert, repo-ng, and their dependencies into the container.
- Test: Have some operating systems (Windows, Ubuntu, MacOS, etc) to install the container and communicate using the NDN packets.

**Required Knowledge for Participants**

- Have some basic knowledge of Docker.
- Once in his/her life time has successfully finished NDN environment setup.

**Expected Outcome**

If one's OS supports docker, it can talk in NDN in a very simple way.

---

## 6. Implementing Broadcast-based Self-learning Forwarding Strategy in NFD

Project Lead: Teng Liang

**Motivation**

In local area networks and mobile ad-hoc networks, broadcast-based self-learning is a common mechanism to find packet delivery paths. Self-learning broadcasts the first packet, observes where the returning packet comes from, then creates the corresponding forwarding table entry so that future packets will only need unicast. The main benefits of this mechanism are its simplicity, adaptability, and support of mobility. Junxiao designed a broadcast-based self-learning mechanism for NDN. The NFD development team has a lot of discussion on its implementation design. In addition, its implementation is in progress.

**Contribution to NDN**

This project implements the first broadcast-based self-learning forwarding strategy in NFD, which can be customized in many scenarios, such as in LAN and wireless ad hoc networks. NDN developers can use this forwarding strategy for its simplicity, adaptability, and support of mobility in different scenarios. Researchers can use this forwarding strategy as a baseline for their research.

**Tasks**

We have broken the implementation design into several tasks defined on Redmine, including discovery Interest indication (#4355), prefix announcement for self-learning (#4280), measurement table for self-learning, and self-learning forwarding strategy (#4279).

In addition, this task is blocked by the task of giving strategy authority over Data packets (#4290).

**Required Knowledge for Participants**

C++11

**Expected Outcome**

The ideal outcome is the full implementation of broadcast-based self-learning forwarding strategy in NFD with a test scenario. As the implementation design is already broken into several tasks after rounds of discussions. The outcome can be quantified by the accomplishment of tasks.

---

## 7. Demonstrating the Benefits of In-Network Congestion Detection

Project Leads: Klaus Schneider, Eric Newberry, Chavoosh Ghasemi

**Motivation**

Congestion control is an important part of almost every application. Examples include big data (like Hadoop), content distribution networks, data center networks, wireless networks, and audio/video streaming. Without a comprehensive congestion control framework, application developers have to either implement their own ad-hoc solutions or suffer from poor performance.

**Contribution to NDN**

Over the last weeks and months we have made good progress in implementing key parts of a congestion control framework for NDN:
- [Issue #1624](https://redmine.named-data.net/issues/1624), [Issue #3797](https://redmine.named-data.net/issues/3797)
- [Issue #3823](https://redmine.named-data.net/issues/3823), [Issue #4289](https://redmine.named-data.net/issues/4289)

In this hackathon project, we want to put the pieces together and demonstrate that our scheme of in-network congestion detection outperforms solutions that solely detect congestion at the end-points.

**Tasks**

- Implement In-Network Congestion Detection. Either on:
  * Ethernet links
  * TCP/UDP Tunnels
  * Via NDNLP Link Loss Detection

- Implement the congestion signaling, while considering the current [NFD limitations](https://redmine.named-data.net/issues/4290)
  * Choose an application to demonstrate the results: File Transfer, Video Streaming, others?

- Evaluate the performance on real-world hardware (laptops, switches), together with traffic shaping tools (earlier evaluations were restricted to ndnSIM).

**Recommended Knowledge for Participants**

- C++, ndn-cxx library, NFD
- Socket programming, linux queuing discipline (qdisc), ioctl commands
- Traffic shaping tools (e.g. `tc netem`)
- Statistical tools, like R, to create plots of the results.

**Expected Outcome**

A clear demonstration of better application performance due to the use of congestion control.

---

## 8. NFD Measurements Table Manager

Project Lead: Davide Pesavento

**Motivation**

- Currently, NFD's measurements table is not exposed to management clients.
- Hard to retrieve stats for measurements-based strategies such as ASF.
- Help operators and developers understand/debug the behavior of forwarding strategies.

**Objectives**

Support per-prefix read-only access to the measurements table via NFD management protocol.

**Tasks**

- Implement encoding/decoding of measurement entries, namely (in increasing order of difficulty):
  * For a given name, represent the entry as a free-form string
    - Displayed as-is by the client
  * For a given name, represent the entry as a map {face-id => string} or similar structure, where "string" contains face-specific measurements info
    - Strings displayed as-is by the client, indexed by face-id
  * For a given name, represent the entry fields as structured TLVs
    - This requires the client to understand the TLV types, but is machine readable
- Implement an NFD manager that responds to `/localhost/nfd/measure/query/PREFIX` (where `PREFIX` is encoded as one name component)
- Implement a new nfdc command: `nfdc measure query PREFIX`

**Requirements for Participants**

- C++11
- Understanding of how NFD management works
- High-level understanding of how strategies and the measurements table are implemented
- A machine capable of running NFD

**Expected Outcome**

Demonstrate the new nfdc command on the ASF strategy, with ndn-traffic-generator or ndnping.

---

## 9. NDN Snapchat

Project Lead: Nicholas Gordon

**Problem statement**

Build a weakly-secure Snapchat-like photosharing program on NDN, using QR codes and phone scanners to share keys.

**Planned tasks**

- Implement Android-to-Android file sharing using jNDN.
- Extend file sharing to be "media aware" in Android.
- Implement "self-destruct" timer for photos.
- Implement QR code generation and scanning with some library.
- Utilize QR code system to share keys and photo prefixes.
- Encrypt shared photos.
- (Stretch goal) Integrate with any available TPMs for better security.
- (Stretch goal) Improve encryption scheme to improve cachability of data.
- (Stretch goal) Integrate with the testbed to enable remote filesharing.

**Knowledge requirements**

- NDN and its concepts, including namespace design, key systems, sync
- Android app development
- Android system programming for stretch goals

**Expected outcomes**

- (Artifact) Simple NDN-based file transfer app for android
- (Artifact) Weakly-secure NDN-based Snapchat app
- (Skill) Improved community familiarity with NDN on Android
- (Investigation) Feasibility of QR code scanning for out-of-band key exchanges

---

## 10. NFD Content Store Management

Project Lead: Davide Pesavento

**Motivation**

An NDN node implements in-network caching through a Content Store (CS), which is widely studied in the literature. NFD, the most popular NDN forwarder implementation, offers only a very limited facility to observe the CS runtime behavior (just plain logging).

This project is to design and implement a Content Store Management protocol for NFD. The protocol would allow experimenters and operators to instrument the CS, to understand the effectiveness of in-network caching. It also includes a command to erase selected CS entries for experiment purposes.

**Contribution to NDN**

Provide visibility into the Content Store, an important component of an NDN node.

**Tasks**

- CS hit/miss counters: Publish a status dataset at `/localhost/nfd/cs/info`, providing CS hit/miss counters. Implement `nfdc cs info` command to show these counters.
- CS enumeration: Provide a CS enumeration operation at `/localhost/nfd/cs/query/PREFIX` (where `PREFIX` is encoded as a name nested in one component), listing the first 256 Data names (no implicit digest) under the specified prefix. Implement `nfdc cs list prefix PREFIX` command to execute the query.
- CS erase entry command: Add a control command at `/localhost/nfd/cs/erase`, that erases CS entries under a name prefix specified in the parameters, limited to the first 256 entries. Implement `nfdc cs erase PREFIX` command to execute the command and show the number of erased entries.

**Required Knowledge for Participants**

- C++11
- A computer capable of compiling and running NFD (can be a virtual machine)
- Knowledge about NFD internals, especially management, is a plus

**Expected Outcome**

Use ndnping or ndn-traffic-generator to send traffic through NFD. Demonstrate the `nfdc cs` subcommands implemented in this project.

---

## 11. NFD Management Thread

Project Lead: Davide Pesavento

**Motivation**

NFD currently implements its management protocol in the same thread as packet forwarding. As part of the management protocol implementation, the main thread is doing computationally intensive work, such as packet signing and signature verification, causing significant forwarding delays.

This project moves the management protocol implementation into a separate thread. Packet signing, signature verification, as well as command/dataset encoding and decoding, are performed in the management thread. The forwarder's data structures are shared between forwarding thread and management thread, and must be protected by a global lock. Compared to the current NFD implementation, forwarding is stopped only when management is accessing those data structures, which is a shorter duration than the entire management processing.

**Contribution to NDN**

Improve NFD performance with regard to [management](https://redmine.named-data.net/issues/3565).

**Tasks**

- Data structure locking: Add a lightweight lock (a simple spinlock can be implemented with `std::atomic_flag`) to NFD's data structures that are accessed by both forwarding and management. This includes FaceTable, FIB, StrategyChoice, and ContentStore.
- Management thread separation: Create a management thread. Connect management thread to forwarding through a Unix stream face.
- More efficient communication between threads: NFD-RIB currently connects to NFD's main thread through a Unix stream face, so communication involves socket operations and packet encoding. Since they are in the same process, they can instead communicate through an internal "in-memory face" implemented using a ring buffer or similar technique. This should be applied to NFD-RIB first, and can be applied to the new management thread as well.
- Merge NFD-RIB thread into management thread: NFD-RIB currently interacts with FIB through control commands. Since management is now in its own thread, NFD-RIB can be merged into the same management thread, and interact with FIB through direct function calls. This decreases the complexity of NFD-RIB and FIB management (`add-nexthop` and `remove-nexthop` commands can be eliminated).

**Required Knowledge for Participants**

- C++11
- Basic concepts of concurrency and thread synchronization
- NFD internals, especially management
- A computer capable of compiling and running NFD (can be a virtual machine)

**Expected Outcome**

- Project report slides: The report should contain a diagram illustrating how the management thread works.
- Project demo: The demo shows implemented features through NFD logs.
