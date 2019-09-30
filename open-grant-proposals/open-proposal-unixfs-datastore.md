# Open Grant Proposal: Secure native file syncing on Filecoin via unixfs-datastore

**Name of Project:** Secure native file syncing on Filecoin via unixfs-datastore

**Proposal Category:** `devtools-libraries`

**Proposer:** [@requilence](https://github.com/requilence)

**Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

# Project Description

Native file syncing and sharing is an essential feature to provide competitive user experience vs. cloud solutions. 
Current solutions allow to mount IPFS with FUSE is suboptimal and doesn’t provide fluent user experience with the speed of native filesystem, like Dropbox does.

We propose to develop a cross platform go library to enable full OS integration (ipfs/filecoin with native file system). It will enable working with the same versions of files on different devices with different software. Example, a user can edit an xls file on her computer and it will be stored in filecoin immediately without data duplication on the client device. Files will be fully encrypted when stored in IPFS/filecoin.

## Value

Allowing end-users to back up files from their computers in the Filecoin network will create a new demand for Filecoin and strengthen the ecosystem. Native File API integration will allow a lot of developers to create apps and services that can compete with web 2.0 analogs or competitors.

## Deliverables

Custom datastore for go-ipfs & go-filecoin that will map UnixFS-v2 IPLD structure with native file APIs for MacOS and Windows. It will support encrypt-on-the-fly, so files will be encrypted when stored in other IPFS/filecoin peers, while being plaintext on the client’s machine

So as a result, users will be able to download go-filecoin and use it in a way they use Dropbox – to sync their local files between their or their team member computers.

## Development Roadmap

1. develop the new **unixfs-datastore** for go-ipfs based on badgerds datastore that will map native files in the user's OS with the UnixFS-v2 IPLD structure while being able to extract the raw IPLD blocks from this files. Badgerds will be used to index/map raw IPLD blocks within filesystem files and also to store blocks that are not part of UnixFS-v2 structure. 
- 2 people. Lead Golang developer, Golang developer.
- $17,400
- 1.5 months
2. Implement IPNS/pubsub interface and CLI commands to store UnixFS-v2 objects as a pointer to the actual IPLD root
- 2 people. Lead Golang developer, Golang developer.
- $11,600
- 1 month
3. Create interface to integrate different native file APIs with unixfs-datastore. Integrate MacOS native file API. Users will be able to modify files directly on their computer – this will trigger UnixFS-v2 IPLD structure to change. Every change that was triggered from the outside, will result in local file change
- 2 people. Lead Golang developer, Golang developer.
- $11,600
- 1 month
4. Implement encryption-on-the-fly. User store unencrypted files on their device, while nixfs-datastore should be able to encrypt them on reading(in order to extract IPLD blocks or transfer this blocks to the P2P network) and decrypt on writing,
- 2 people. Golang developer.
- $11,600
- 1 month
5. Integrate and test unixfs-datastore with go-filecoin
- 2 people. Lead Golang developer, Golang developer.
- $11,600
- 1 month
6. Integrate Windows native file API with unixfs-datastore
- 2 people. Lead Golang developer, Golang developer.
- $11,600
- 1 month
7. Develop API and CLI to monitor user usage and stats
- 2 people. Lead Golang developer, Golang developer
- $11,600
- 1 month
8. Put together all documentation 
- 1 people. Golang developer
- $5,800
- 1 month

## Total Budget Requested

$92,800, 2 developers - 8.5 months. 

## Maintenance and Upgrade Plans

We plan to maintain this repo long term, as our team will be it’s first consumer. 

# Team

## Team Members

- Roman Khafizianov [@requilence](https://github.com/requilence)
- Golang developer from our team (to be determined)

## Team Member LinkedIn Profiles

- https://www.linkedin.com/in/requilence/

## Team Website

https://anytype.io

## Relevant Experience

We have worked with go-ipfs for a long time. Last 10 months our team worked on Anytype – collaborative document editor on top of IPFS. We started to research filecoin recently

## Team code repositories

https://github.com/requilence/integram
Other repos related to IPFS is private(until the public release)

# Additional Information

Our team participated in the IPFS camp
