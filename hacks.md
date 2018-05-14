---
layout: page
title: Accepted Hacks
---

{::options toc_levels="2,3" /}

* TOC
{:toc}

## 1. NFD Management Thread

Project Leads: Davide Pesavento, Junxiao Shi

**Motivation and Problem Statement**

- Management slows down NFD
  - The management module performs several costly operations in the same thread as forwarding.
  - Packet forwarding is completely stopped while management is doing this work.
- This project moves management to a new thread
(https://redmine.named-data.net/issues/4528)
  - Heavy tasks run in the management thread, so they do not block forwarding.
    - We cannot make NFD data structures thread-safe in 12 hours, so we will use a lightweight global lock: all tables will be briefly locked while management accesses them.
  - The new management thread and the existing RIB thread talk to NFD forwarding (main thread) via Unix stream faces. This should be changed to an in-memory shared ring buffer to avoid socket operations and packet encoding.
(https://redmine.named-data.net/issues/4530)
  - Afterwards, RIB can be merged into the new management thread, so that FIB updates can be done directly via function calls instead of Command Interests.
(https://redmine.named-data.net/issues/4529)

**Tasks**

- Data structure locking: Add a lightweight lock (a simple spinlock can be implemented with std::atomic_flag) to NFD's data structures that are accessed by both forwarding and management. This includes FaceTable, FIB, StrategyChoice, and ContentStore.
- Management thread separation: Create the management thread and move management protocol processing logic there.
- More efficient communication between threads: NFD-RIB currently connects to NFD's main thread through a Unix stream face, so communication involves socket operations and packet encoding. Since they are in the same process, they can instead communicate through an internal ""in-memory face"" implemented using a ring buffer or similar technique. Note that this can be applied to the new management thread in point 2 as well.
- Merge NFD-RIB thread into management thread: NFD-RIB currently interacts with FIB through control commands. Since management is now in its own thread, NFD-RIB can be merged into the same management thread, and interact with FIB through direct function calls. This decreases the complexity of NFD-RIB and FIB management (for instance, add-nexthop and remove-nexthop commands can be eliminated)."

**Required Knowledge for Participants**

- C++
- basic concepts of concurrency and thread synchronization
- knowledge about NFD internals, especially management

**Expected Outcomes**

- Mainly, that NFD still works after these changes
- NFD's management protocol is now handled (mostly) in a separate thread and its impact on packet forwarding latency is greatly reduced

---

## 2. Porting PSync C++ library to Java

Project Lead: Ashlesh Gawande

**Motivation and Problem Statement**

[PSync](https://named-data.net/publications/scalable_name-based_data_synchronization/) is an NDN sync protocol that supports full sync and parital sync. The aim of this hackathon project is to port the [PSync C++ library](https://netwisdom.cs.memphis.edu/gitlab/mzhang4/psync) (alpha s/w) to Java. We also hope to get some feedback on how to make the C++ library better.

**Tasks**

- Come up with an API and write the Java implementation.
- Design a simple Android application to demonstrate the library.

**Required Knowledge for Participants**

- PSync Protocol, Sync protocols in general
- C++11, jNDN, Android NFD

**Expected Outcomes**

PSync Java library that is used by an Android application for partial/full sync.

---

## 3. <del>Firefly for Android</del>

Project Lead: Jeff Thompson

**Motivation and Problem Statement**

Application developers need to focus on their NDN application, not implementing publisher mobility and data persistence. Firefly showed a solution in the browser using Google Firebase, with room for improvement.

**Tasks**

- Port the Firebase interface from JavaScript to Java (Android).
- Develop demo Android app (simplified ChronoChat).

**Required Knowledge for Participants**

- JavaScript
- Java
- Bonus: Android app development

**Expected Outcomes**

- Client library FireflyFace available to Java and Android developers.
- Demo app showing persistence/interoperability between an Android mobile and a laptop web app.

---

## 4. <del>Re-write NFD integration tests in Mini-NDN & create a gerrit bot</del>

Project Leads: Ashlesh Gawande, Saurab Dulal

**Motivation and Problem Statement**

[NFD integration tests](https://gerrit.named-data.net/NFD/integration-tests) are used to make sure that NFD runs and works correctly in a real environment. But these are not executed on every change on gerrit. We aim to write all the tests in Mini-NDN and add a bot to post a comment on every NFD patch similar to NLSR intergation tests.

**Contribution to NDN**

Don’t have to wait for an NFD release change to find out if anything is broken in integration test. Anybody with low resources can run these tests on a single machine.

**Tasks**

- Re-write existing NFD integration tests in Mini-NDN
- Modify NLSR gerrit bot to also test NFD changes

**Required Knowledge for Participants**

- NFD integration tests (bash scripts)
- Mini-NDN
- Gerrit

**Expected Outcomes**

Current NFD changes on gerrit receives verification comments from a bot running Mini-NDN integration tests.

---

## 5. IoT security bootstrapping with NDN

Project Leads: Yanbiao Li, Zhiyi Zhang, Haitao Zhang

**Motivation and Problem Statement**

Enroll a new IoT device in your home network, such that it can securely communicate with all other devices in the same network with NDN

**Contribution to NDN**

The first step to NDNoT; May also be used in security setup of NDN Edges

**Tasks**

- Implement a Controller on android phone: scan QR code; distribute TrustAnchor; issue Certificate
- Implement a Device on Raspberry Pi; initialize bootstrapping; generate key-pair and install Cert

**Required Knowledge for Participants**

- C/C++
- ndn-cxx
- NFD-android
- jNDN
- DH key exchange
- public-key encryption/decryption

**Expected Outcomes**

- The implementation of Controller and Device
- Use the Phone to bootstrap the device; then the device is able to communicate with the laptop

---

## 6. <del>Whisperface: NDN Face Over Audio Channel</del>

Project Lead: Alex Afanasyev

**Motivation and Problem Statement**

- New type of face for device-to-device communication
- Expand ability for NDN communication to new devices/channels

**Contribution to NDN**

Enables simple low-rate device-to-device communication, without affecting existing connections

**Tasks**

- Discover library that can be used to realize low-rate over microphone/dynamics

**Required Knowledge for Participants**

- NFD
- ndn-cxx
- Android
- Linux audio core
- C++
- Java

**Expected Outcomes**

- Draft of Linux and Android extensions for NFD
- Simple app that communicates NDN over audio channel

---

## 7. Implement State Vector Sync (SVS) and Apply It to Repo

Project Lead: Haitao Zhang

**Motivation and Problem Statement**

The current repo-ng does not replicate Data to different nodes. So we implement State Vector Sync, and make use of it to implement a distributed NDN Data repo

**Contribution to NDN**

Prove a State Vector Sync library and a distributed NDN Data repo

**Tasks**

- Implement the State Vector Sync library
- Apply State Vector Sync to repo-ng

**Required Knowledge for Participants**

- C++
- ndn-cxx
- repo-ng

**Expected Outcomes**

- State Vector Sync library
- A Distributed NDN Data Repo

---

## 8. Make NDN Congestion Control work in ndnSIM

Project Leads: Md Ashiqur Rahman, Klaus Schneider

**Motivation and Contribution to NDN**

The current NFD congestion detection doesn't work in ndnSIM, since ndnSIM doesn't use regular TCP, UDP, or Unix faces. This project aims to fix this and evaluate the proper function of the implementation.

**Tasks**

- Implement a ns-3 Queue based on CoDel that detects congestion and inserts congestion marks.
- Map these congestion marks onto NDNLP/ns-3 packets.
- Implement a ndnSIM consumer application that reacts to the congestion marks.

**Additional Tasks (if time)**

- Start submitting the code to Gerrit.
- Implement a TCP-Cubic like consumer app and compare it against the AIMD app.

**Required Knowledge for Participants**

- C++
- NFD
- ndnSIM

---

## 9. A Basic Forwarding Strategy for Ad-hoc Networks in NFD

Project Lead: Teng Liang

**Motivation and Problem Statement**

The current NFD considers little of ad-hoc networks and does not have a forwarding strategy for ad-hoc networks

**Contribution to NDN**

- Add a forwarding strategy for ad-hoc networks as a baseline to NFD (and ndnSIM)
- Understand how to adapt NFD to ad-hoc networks (necessary changes to forwarder pipelines)

**Tasks**

- Implement a basic forwarding strategy in NFD and evaluate it in ndnSIM

**Required Knowledge for Participants**

- C++
- NFD/ndn-cxx
- ndnSIM

**Expected Outcomes**

- A forwarding strategy in NFD and basic evaluation results
- Lessens on how to adapt NFD to ad-hoc networks and evaluation results
