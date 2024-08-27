# Meshplay Adapter Library
The Meshplay Adapter Library provides a common and consistent set of functionality that Meshplay adapters use for managing the lifecycle, configuration, operation, and performance of cloud native infrastructure. See [Introducing MeshKit and the Meshplay Adapter Library](https://khulnasoft.com/blog/meshplay/introducing-meshkit-and-the-meshplay-adapter-library) for more.

## Purpose 

The main purpose of the meshplay-adapter-library is to 
* provide a set of interfaces, some with default implementations, to be used and extended by adapters.
* implement common cross cutting concerns like logging, errors, and tracing
* provide a mini framework implementing the gRPC server that allows plugging in the mesh specific configuration and 
    operations implemented in the adapters.

### Overview and usage 

The library consists of interfaces and default implementations for the main and common functionality of an adapter. 
It also provides a mini-framework that runs the gRPC adapter service, calling the functions of handlers injected by the 
adapter code. This is represented in an UML-ish style in the figure below. The library is used in the Consul adapter, 
and others will follow. 

<img alt="Overview and usage of meshplay-adapter-library" src="./doc/meshplay-adapter-library-overview.png" align="center"/>

### Package dependencies hierarchy
A clear picture of dependencies between packages in a module helps avoid circular dependencies (import cycles), 
understand where to put code, design coherent packages etc.

Referring to the figure below, the packages `config` and `meshes` (which contains the adapter service proto definition) 
are at the top of the dependency hierarchy and can be used by any other package. Thinking in layers (L), `config`  
would be in the top layer, L1, `adapter` in L2, and `config/provider`  in L3. Packages can always be imported and used in lower layers.

<img alt="Package dependencies hierarchy" src="./doc/mesher-adapter-library-package-dependencies.png" align="center"/>

<div>&nbsp;</div>

## Join the KhulnaSoft community!

<a name="contributing"></a><a name="community"></a>
Our projects are community-built and welcome collaboration. 👍 Be sure to see the <a href="https://docs.google.com/document/d/17OPtDE_rdnPQxmk2Kauhm3GwXF1R5dZ3Cj8qZLKdo5E/edit">KhulnaSoft Community Welcome Guide</a> for a tour of resources available to you and jump into our <a href="http://slack.khulnasoft.com">Slack</a>!

<p style="clear:both;">
<a href ="https://khulnasoft.com/community/meshmates"><img alt="MeshMates" src=".github/readme/images/KhulnaSoft-MeshMentors.png" style="margin-right:10px; margin-bottom:7px;" width="28%" align="left" /></a>
<h3>Find your MeshMate</h3>

<p>MeshMates are experienced KhulnaSoft community members, who will help you learn your way around, discover live projects and expand your community network. 
Become a <b>Meshtee</b> today!</p>

Find out more on the <a href="https://khulnasoft.com/community">KhulnaSoft community</a>. <br />
<br /><br /><br /><br />
</p>

<div>&nbsp;</div>

<a href="https://meshplay.khulnasoft.com/community"><img alt="KhulnaSoft Service Mesh Community" src=".github/readme/images//slack-128.png" style="margin-left:10px;padding-top:5px;" width="110px" align="right" /></a>

<a href="http://slack.khulnasoft.com"><img alt="KhulnaSoft Service Mesh Community" src=".github/readme/images//community.svg" style="margin-right:8px;padding-top:5px;" width="140px" align="left" /></a>

<p>
✔️ <em><strong>Join</strong></em> any or all of the weekly meetings on <a href="https://calendar.google.com/calendar/b/1?cid=bGF5ZXI1LmlvX2VoMmFhOWRwZjFnNDBlbHZvYzc2MmpucGhzQGdyb3VwLmNhbGVuZGFyLmdvb2dsZS5jb20">community calendar</a>.<br />
✔️ <em><strong>Watch</strong></em> community <a href="https://www.youtube.com/playlist?list=PL3A-A6hPO2IMPPqVjuzgqNU5xwnFFn3n0">meeting recordings</a>.<br />
✔️ <em><strong>Access</strong></em> the <a href="https://drive.google.com/drive/u/4/folders/0ABH8aabN4WAKUk9PVA">Community Drive</a> by completing a community <a href="https://khulnasoft.com/newcomer">Member Form</a>.<br />
✔️ <em><strong>Discuss</strong></em> in the <a href="https://discuss.khulnasoft.com">Community Forum</a>.<br />
</p>
<p align="center">
<i>Not sure where to start?</i> Grab an open issue with the <a href="https://github.com/issues?q=is%3Aopen+is%3Aissue+archived%3Afalse+org%3Akhulnasoft+org%3Ameshplay+org%3Aservice-mesh-performance+org%3Aservice-mesh-patterns+label%3A%22help+wanted%22+">help-wanted label</a>.
</p>
