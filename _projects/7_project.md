---
layout: page
title: onlineide
description: ASE project
img: assets/img/onlineide.jpg
importance: 4
category: computerscience
---

a bonus project from advanced software engineering course of TUM. Implement an onlineIDE and control the darkmode of it using RaspberryPI.

Overall architecture:
<div class="col-sm mt-3 mt-md-0">
   {% include figure.liquid loading="eager" path="assets/img/onlineide.png" class="img-fluid z-depth-1" zoomable=true %}
</div>

finished requirements:

**Source Code Editor (UI service) * 2 points** ✅
- A user can see syntax highlighting for the respective programming language when editing a
source file in the code editor.  √
* A user can compile single source code files and see the output of the compilation process (e.g. errors). √
* When a user edits a source file, he or she needs to save the changes first before being able to compile the code √

* A user can create, list, update and delete (source code) projects through the web GUI. √
* A user can create, list, update and delete source code files inside a project through the web GUI. √
* A user can share a project with another user. √

**Compilation (compiler service) * 1 point** ✅
* A user can compile single source code files containing C or Java code (both, C and Java must be
implemented). √
* A user can retrieve the standard output and errors of the compilation process. √

**Project File Management (project service) * 1 point** ✅
* A user can create, list, update and delete (source code) projects which have a unique name and are persisted in a database. √
* A user can create, list, update and delete source code files inside a project; the source code √
files are persisted in a database (you do not have to store the files to disk, but simply store their
content as a string in the database). √

**Authentication/Authorization (api-gateway service) * 2 points**  ✅
* Users can authenticate themselves via their GitLab LRZ account (OAuth 2.0). √
* User requests accessing projects, project files, or user information need to be authenticated and
authorized. √
* Users can share projects with other users registered with GitLab LRZ thereby granting them full
read/write permission. √

**Microservices Architecture (api-gateway and service-registry service) * 1 point** 
* All services need to be independently executable and deployable microservices written with
Spring Boot. √
* An API gateway serves as a single entry point for all clients and proxies/routes requests to the
appropriate services, if authorized.
* Service discovery is performed by a central service registry entity. √
* Load balancing is performed to distribute load across microservice instances.

**Dark Mode Toggle Button (dark-mode service) * 1 point** ✅

selection: GPIO18

* A user can use a dark mode button in the form of a hardware switch connected to the Raspberry
Pi, to toggle a dark color scheme for the syntax highlighting. √
* When pressing the hardware switch, an interrupt is triggered which sends an HTTP request to the
dark-mode service, which stores the dark mode status in memory (no need for other persistence). √
* For the sake of simplicity, the dark mode is not triggered for a specific user account, but rather for
the entire OnlineIDE. √
* The dark mode status is regularly fetched from the OnlineIDE’s frontend; there is no need to
implement bidirectional streaming (e.g., through websockets) √
* The final version of your C/C++ code is flashed to the Raspberry Pi before returning it to us. This
includes the static IP address of your Google VM, as this is where the HTTP request is sent. √

**Continuous Integration & Deployment * 2 points**
* Regression tests are continuously run in a continuous integration environment on each commit
(at least one unit, integration, and end-to-end test). √
* Each microservice lives in its own (Docker) container, to simplify scaling of specific services. √
* Containers of microservices and databases can be orchestrated and scaled independently. √
* The whole OnlineIDE microservice orchestration is continuously deployed to a Google VM and
accessible via the browser. √