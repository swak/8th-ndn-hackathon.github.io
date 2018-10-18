---
layout: page
title: Accepted Hacks
---

{::options toc_levels="2,3" /}

* TOC
{:toc}

## 1. An Android App to visualize the workflow in IoT

Project Leads: Zhiyi Zhang, Yanbiao Li, Bo Chen, NDN-IOT

### [Slides](https://github.com/7th-ndn-hackathon/7th-ndn-hackathon.github.io/blob/source/_assets/files/android%20-%20Zhiyi%20Zhang.pdf)

**Motivation and Problem Statement**

- Goal: An android app to work with NDN-RIOT system to get the status and
workflow of each node in the system
- Solution: 
    - Add a new service into the service discovery of NDN RIOT system to let each device be able to
reply it’s status to the controller (Android Phone)
   - Android phone periodically query the status from each device
   - Android phone visualize the status in its GUI
   - Requirement: Android Phone, Android App development skills


## 2. Broadcast and ad-hoc wireless faces in NFD

Project Lead: Md Ashiqur Rahman, The University of Arizona

[Slides](https://github.com/7th-ndn-hackathon/7th-ndn-hackathon.github.io/blob/source/_assets/files/Ashiq_ad-hoc%20-%20Md%20Ashiqur%20Rahman.pdf)

**Motivation and Problem Statement**

- Task
  - NDN self-learning is initially defined for point-to-point
links only. •An important scenario for NDN self-learning in NFD is on
wireless channels, such as ad-hoc WiFi networks among
Android devices. •Thus, the protocol definition shall be extended to
support broadcast and ad hoc wireless faces.

- Benefit to NDN:
  - Current NFD does not support broadcast and ad hoc wireless faces which would be helpful for working in ad-hoc networks. 

- Expected Outcome:
  - To have support for broadcast and wireless ad-hoc faces in NFD. 
- Tools:
  - NFD, ndn-cxx, C++
  
## 3. Interest Buffering

Project Lead: Tianxiang Li, UCLA

**Motivation and Problem Statement**

- Task

  - When transmitting Interests, what if there is no available faces
  - If no face available, Interest is buffered in PIT
  - Detect when a face is up, trigger Interest to be sent out on that face
  - Face should report to strategy its own status, whether it’s up or down
  - Face signaling has not been supported yet in NFD
- Tools
  - NFD, ndn-cxx, C++

  
## 4. NFD Self-learning: Implementation, Testing and Evaluation

Project Leads: Proposal Leader(s), Proposal Associates

**Motivation and Problem Statement**
- Self-learning is an important mechanism for NDN research/testing/deployment to achieve plug and
play. The first version of self-learning is reaching its final stage and requires extensive testing.
- Tasks
  - Finalize self-learning strategy implementation (redmine: #4279)
  - Test self-learning with integration-testing
  - Evaluate self-learning performance
- Required knowledge for participants
  - C++, NFD development experience
- Expected outcome
  - Working code
  - Evaluation results
  
## 5. A use-case example APP using NDN-IoT package
  
Project Leads: Yanbiao Li, Zhiyi Zhang

**Motivation and Problem Statement**

- Need an simple smart home app based on the NDN-IoT package
- Tasks
  - A Controller APP on the phone to manage and monitor the home network
  - The device APP on two nRF52840 boards to control LED lights based; the APP is built upon the NDN-IoT package.
  - The controller communicates with devices via BLE; devices communicate with each other via 802.15.4
- Required knowledge for participants
  - C/C++, ndn-cpp-lite, NFD-android, jNDN, BLE
- Expected outcome
  - The Controller App and the Device App.
  
## 6. 3D Visualization of NDN Traffic
  
Project Leads:  Alexander Monaco, Alexander Afanasyev

**Motivation and Problem Statement**
  - The understanding of traffic flow is important in development of resilient network tools.
  - 3D NDN Visualization could aid in providing a more efficient method of analyzing and interpreting traffic data.
- Contribution to NDN
  - An alternative visualization to current NDN data output that can potentially display data in a more efficient manner
for both experts and non experts.
- Tasks
  - Investigate existing tools for identifying and analyzing network traffic.
  - Use available network data to evaluate promising tools.
  - Attempt to create a visualization using the output of these tools.
- Required knowledge for participants
  - Since the visualization will be developed using the Unity engine, the main language that will be used will be C#
- Expected outcome
  - A simple visualization that can be further developed into a working 3D visualization prototype.

## 7. NDN sign-on protocol implementation over BLE
  
Project Leads:  Yanbiao Li, Zhiyi Zhang

**Motivation and problem statement**
  - As a typical use-case of sign-on, a constrained device obtains the local trust anchor and an
anchor-signed certificate from the controller (i..e, an android-phone). But some constrained
device can only communicate with the phone via Bluetooth Low Energy.
- Contribution to NDN-IoT
  - Enable to deploy NDN-IoT package on more boards
- Tasks
  - Implement NDN sign-on protocol (detail doc will be provided to the participants later) with an
android phone and a nRF58240 board
- Required knowledge for participants
  - jNDN, NFD-android, C/C++, BLE
- Expected outcome
  - The implementation of sign-on over BLE
  
## 8. Mini-NDN documentation
  
Project Leads:  Ashlesh Gawande

**Motivation and problem statement**

  - Add any missing documentation and auto-generate to website
  - Also create a FAQ/documentation of most popular questions from the mailing list
- Contribution to NDN
  - Lower getting started barrier with Mini-NDN
- Tasks
  - Choose a documentation standard and setup auto generation
  - Identify what documentation can be updated and what needs to be added (look at mailing list)
  - Verify + update existing doc and add new documentation
- Required knowledge for participants
  - Mini-NDN, Mininet, Python, Probably Sphinx/Doxygen
- Expected outcome
  - Updated documentation which is automatically mirrored to the website

## 9. Make NDN-RIOT + NDN-IoT pkg work on NRF52840
  
Project Leads:  Zhiyi Zhang, Yanbiao Li, Bo Chen, NDN-IOT

**Motivation and problem statement**
 - Current NDN-RIOT works fine on Atmel Xpro boards
 - Make it work on NRF52840, a board that support BLE, Bluetooth 5.0, and
802.15.4 at the same time!
- Goal: to let the existing service discovery and access control protocol function
on the new boards
 - Requirement: NRF52840 board, C coding skills

## 10. Certificate Support in esp8266ndn Library
  
Project Leads:   Junxiao Shi

**Motivation and problem statement**

- esp8266ndn: library for developing NDN app on ESP8266/ESP32 MCU
  - esp8266ndn is used in building sensing deployments at Memphis & NIST.
- esp8266ndn supports HMAC and EC signing and verification, but application
must provide uncompressed kit bits.
- This project: add NDN Certificate v2 decoder and encoder.
  - It paves the way of implementing trust schema, ndncert-client, and secure device onboarding in the
future.
- Requirement: must have ESP8266 or ESP32 hardware.


## 11. Tiny Forwarder with esp8266ndn Library

Project Leads:   Junxiao Shi

**Motivation and problem statement**

- esp8266ndn: library for developing NDN app on ESP8266/ESP32 MCU
  - esp8266ndn is used in building sensing deployments at Memphis & NIST.
  - In both systems, sensor nodes are one hop away from NFD.
- This project: create a tiny forwarder on ESP8266/ESP32.
  - We explore a specific design: per-face Bloom filters as PIT, instead of name-based PIT.
  - Sacrifice preciseness of PIT name matching and InterestLifetime, in exchange for lower memory
requirement.
- If successful:
  - Building sensing deployments do not need to depend on infrastructure network.
  - Same design can be ported to NDN-RIOT.
- Requirement: must have ESP8266 or ESP32 hardware.

## 12. HMAC and Merkle-Hash-Tree Signatures in ndn-cxx

Project Leads:   Junxiao Shi

**Motivation and problem statement**

- SignatureHmacWithSha256: hash-based signature with provenance.
  - defined in NDN Packet Format, implemented in CCL, but missing in ndn-cxx.
- SHA-256-Merkle-Hash-Tree: aggregated signing, individually verifiable.
  - defined in CCNxx 0 packet format, but we should explore this algorithm. 
  - When producing many Data packets, the producer only needs to perform one RSA/ECDSA
signing, while each Data packet is individually verifiable.
- This project: add HMAC and Merkle hash tree signing/verification.
  - HMAC implementation is intended to be mergeable to the codebase.
- Requirement: understand crypto; can write C++14.

## 13. NDN File System without FUSE

Project Leads:   Junxiao Shi

**Motivation and problem statement**

- NDNFS: an “NDN-friendly file system”. https://github.com/remap/ndnfs-port
  - Copy files to FUSE <= cannot use existing folder of files.
  - NDNFS daemon segments the file and stores signatures <= several open bugs.
  - Data are then served over the network.
- This project: explore a different design.
  - Program works with an existing folder on the filesystem. No FUSE.
  - File segmented and Data signed on the fly upon Interest arrival.
  - It’s as simple as `python3 -m http.server`.
- Requirement: know either ndn-cxx or CCL.

## 14. Modernize ndn-js

Project Leads:   Junxiao Shi

**Motivation and problem statement**

- ndn-js: JavaScript client library for Named Data Networking.
  - NodeJS: works reasonably well.
  - Browser: written in 2013, not kept up with rapidly evolving JavaScript ecosystem.
- This project: make ndn-js integrate well in a modern JavaScript project.
  - Replace Waf build process with a bundler such as Brunch or Webpack.
    - require("ndn-js") should work in web application.
    - Dependencies should come from NPM, not contrib/ folder.
- Provide TypeScript declaration file.
  - This enables type checking of ndn-js APIs in a TypeScript project.
- Add Promise-based APIs as an alternative to callback-based APIs.
- Requirement: can write JavaScript.

• Junxiao Shi

## 15. Packet03, Data Synchronization, and More in repo-sql

Project Leads:   Junxiao Shi

**Motivation and problem statement**

- repo-sql: alternate NDN repository implemented backed by a SQL database.
  - https://github.com/3rd-ndn-hackathon/repo-sql
- This project: a refresh of repo-sql.
  - NDN Packet Format 0.3: Selectors are gone.
    - Redesign database schema and query procedure.
    - Reimplement QueryProcessor without selectors.
- Add some commands: let's compete with repo-ng.
  - TCP bulk insertion.
  - Data insertion command.
- Data synchronization using PSync: repo-ng does not have this, but we have.
  - Start with one-way mirroring: secondary instance mirrors a subset of Data from primary instance.
- Requirement: can write C++14 and know ndn-cxx.

## 16. Refactor encoding and decoding in NDN-RIOT and make it more usable to developers

Project Leads:   Zhiyi Zhang, Yanbiao Li, Bo Chen, NDN-IOT

**Motivation and problem statement**

- Existing NDN-RIOT:
  - NDN packet format 0.2 
  - Some APIs are missing, e.g., name decoding
  - Too many dynamic memory allocation, which is highly not recommended by RIOT team
  - Not very developer-friendly: developers need to manually work on encoding and decoding process
in some cases
- Goal: Make NDN-RIOT a better library to use
- A work in progress
  - We already re-implemented the basic block 0.3 encoding/decoding APIs, name APIs, Interest APIs
  - Refactor other modules (Data, Certificate, etc.)
- Requirement: C coding skills

## 17. Schematized Trust in NDN-RIOT

Project Leads:   Zhiyi Zhang, Yanbiao Li, Bo Chen, NDN-IOT

**Motivation and problem statement**

- With NDN-RIOT, we are able to do basic signature signing and verification.
However, to achieve trust and more fine-grained authentication, schematized
trust is required in IoT scenarios.
- Goal: A simplified version of trust schema in NDN-RIOT
  - Use pre-defined rules instead of manually configured rules as the default trust policy to minimize
the human interactions
    - E.g., some pre-defined rules: Controller Only, Same First n Prefix Only, Signature Only
  - Make schematized trust configuration a service accessible to system controller only: controller can
configure the trust policies of a device
    - E.g., Add one or a set of prefixes/devices into the authorized list to a service provided by the device
- Requirement: C coding skills

## 18. Development of Yang Data Model for NFD Mgmt. Protocol

Project Leads: Rajendra Kumar

[Slides](https://github.com/7th-ndn-hackathon/7th-ndn-hackathon.github.io/blob/source/_assets/files/Yang_data_Model_NDN%20-%20Rajender%20Kumar.pdf)

**Motivation and problem statement**

- To develop a Netconf based protocol for network management of NDN, we need a data model
which can define the current NFD management protocol
- Contribution to NDN
  - Yang data model will help in the development of a network management protocol for NDN
  - Yang data model is extensible (equipment manufacturer and network manager can augment the
current model with new data or operation)
- Tasks
  - Identification of different operation, attributes and other information related to NFD mgmt. protocol
  - Development of Yang data model for current NFD management protocol
- Required knowledge for participants
  - Yang Data modeling Language, NFD
- Expected outcome
  - Yang data model for current NFD management protocol


