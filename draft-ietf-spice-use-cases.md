---
title: "Use Cases for SPICE"
category: info

docname: draft-ietf-spice-use-cases-latest
submissiontype: IETF  # also: "independent", "editorial", "IAB", or "IRTF"
number:
date:
consensus: true
v: 3
area: "Security"
workgroup: "Secure Patterns for Internet CrEdentials"
keyword:
 - SPICE
venue:
  group: "Secure Patterns for Internet CrEdentials"
  type: "Working Group"
  mail: "spice@ietf.org"
  arch: "https://mailarchive.ietf.org/arch/browse/spice/"
  github: "brentzundel/draft-ietf-spice-use-cases"
  latest: "https://brentzundel.github.io/draft-ietf-spice-use-cases/draft-ietf-spice-use-cases.html"

author:
 -
    fullname: "Michael Prorock"
    organization: "Tradeverifyd"
    email: "mprorock@tradeverifyd.com"

 -
    fullname: "Brent Zundel"
    organization: "Tradeverifyd"
    email: "brent.zundel@tradeverifyd.com"

normative:

informative:


--- abstract

This document describes various use cases related to credential exchange in a
three party model (issuer, holder, verifier). These use cases aid in the
identification of which Secure Patterns for Internet CrEdentials (SPICE) are
most in need of specification or detailed documentation.


--- middle

# Introduction

There is a need to more clearly document digital credentials that utilize the
issuer-holder-verifier model across various work at IETF, ISO, W3C, and other
SDOs. This need particularly arises in use cases for verifiable credentials that
do not involve human-in-the-loop interactions, require strong identifiers for
business entities, call for the benefits of CBOR encoding, or leverage the
cryptographic agility properties of COSE. This document covers multiple use
cases for verifiable credentials that help inform both the required architecture
and components, as well as to frame needs for clearly defined message formats or supporting mechanisms.

# Conventions and Definitions

{::boilerplate bcp14-tagged}

# SPICE Common Patterns

Within SPICE there are a few common patterns that continually arise:

- Selective disclosure with CBOR based verifiable credentials
- Cryptographic agility support via COSE, including support for PQC, and
  to permit use of the same signature algorithms with both selective
  disclosure as well as fully disclosed credentials
- Strong and long-lived identities that may be correlated with public key
  material for verification and permit binding to DNS or existing x509
  certificates, as well as providing ready access to public keys for
  verification utilizing HTTP

# SPICE Use Cases

There are several expanding use cases and common patterns that motivate
the working group and broader community, including:

- Microcredentials, particularly in education
- Digitization of physical supply chain documents in multiple
  jurisdictions:
  - CBOR credentials
  - High-volume system-to-system exchange of credentials
  - Regulatory data and business-driven information
- Credentials related to IoT, Control Systems, and Critical Infrastructure 
- Credentials related to authenticity and provenance, especially of
  digital media
- Offline exchange (in person) of credentials that may have been
  internet issued
- Embedding credentials in other data formats
- Digital Wallet Initiatives

# Use Case Discussion

## Roles

An "issuer", an entity (person, device, organization, or software agent) that constructs, secures, and shares digital credentials.

A "holder", an entity (person, device, organization, or software agent) that
stores issued credentials and controls their disclosure.

A "verifier", an entity (person, device, organization, or software agent) that
receives, verifies, and validates disclosed digital credentials.

## Microcredentials in Education

TODO microcredentials use case

## Physical Supply Chain Credentials

Physical supply chains provide several unique scenarios and requirements for
implementers of digital credentials. There is a strong movement toward
digitization of physical supply chain documents which are typically exchanged on
paper or scanned pdf form today using legacy approaches.
Some steps have been taken towards digitatization of supply chain documents
using XML, however this has proved problematic over native binary formats due to
the complexity, size, and volumes of transmission often involved.

Common use cases for physical supply chains include:

- Regulatory data capture and exchange with governmental bodies
- Requirements around capturing specific types of data including:
  - Inspection information
  - Permits
  - Compliance certification (both regulatory and private)
  - Traceability information, including change of control and geospatial
    coordinates
- Providing the ability for 3rd parties to "certify" information about
  another actor in the supply chain. e.g., Vendor A is an approved
  supplier for Company X
- Passing of data between multiple intermediaries, before being sent
  along to customs agencies or consignees.
- Moving large amounts of signed data asyncronously, and bi-directionally
  over a network channel
- Identifying actors in a supply chain and linking them with legal
  entity information

## IoT, Control Systems, and Critical Infrastructure Credentials

The deployment of digital credentials in constrained systems such as IoT,
control systems, and critical infrastructure environments introduces challenges.
These systems often operate in environments with strict security, latency, and
interoperability requirements. Digital credentials play a role in ensuring
secure device identity, access control, and trusted data exchange between
interconnected systems.

Common use cases include: 
- Device identity and authentication ensuring only authorized IoT devices can
  connect to a network or control system.
- Restricting access to critical systems, such as industrial control systems,
  SCADA networks, and energy grid controllers, to only authorized personnel and
  devices.
- Role-based access control (RBAC) and attribute-based access control (ABAC)
  policies using digital credentials.
- Encrypted and authenticated data exchange between industrial sensors,
  actuators, and control systems.
- Verifying software updates and firmware integrity using signed credentials to
  prevent unauthorized modifications.
- Tamper-resistant logging and auditing: digitally signed operational logs and
  sensor data to enable post-incident forensic analysis.
- Temporary access credentials for emergency personnel and automated response
  systems during critical incidents.

## Credentials related to Authenticity and Provenance

Due to a proliferation of AI-generated or modified content, there is an
increased need to provide the ability to establish the provenance of digital
materials.  Questions of authenticity and the means of creation (human created,
machine assited, machine created) also abound. In cases where an AI created the
content, providing the model information related to the generation of that
content is becoming increasingly important.

Common use cases include:

- Determining whether a received piece of media is human created, and that
  the content is authorized for certain uses.
- Providing the ability to trace training materials for LLMs and similar
  models to output
- Understanding if media was created by an authoritative or trustworthy
  source

## Offline exchange of credentials

Many real-world scenarios require credentials to be disclosed, verified, and
validated without continuous or immediate access to online services. This can be
due to network limitations, privacy concerns, or operational constraints in
environments where connectivity is intermittent or unavailable. Some digital
credential frameworks assume online verification mechanisms, which may not be
suitable for offline-first environments where entities must verify credentials
using locally-available data and cryptographic techniques.

Common use cases include:

- Identity verification in disconnected environments, such as remote regions,
  military operations, or disaster recovery efforts.
- Travel and border security, where credentials such as visas, vaccination
  records, or national IDs must be verified in locations with limited or no
  network connectivity.
- Access control in secure facilities, such as industrial sites, research labs,
  or private events.
- Device authentication in air-gapped systems.
- Peer-to-peer credential sharing.

## Embedding Credentials

TODO embedding credentials use case

## Digital Wallets

TODO digital wallet use case

# Security Considerations

TODO Security


# IANA Considerations

This document has no IANA actions.


--- back

# Acknowledgments
{:numbered="false"}

TODO acknowledge.
