---
title: Secure Automation and Continuous Monitoring (SACM) Architecture
docname: draft-birkholz-sacm-architecture-latest
date: 2017-07-28

ipr: trust200902
area: security
wg: SACM Working Group
kw: Internet-Draft
cat: std

coding: us-ascii
pi:
   toc: yes
   sortrefs: yes
   symrefs: yes
   comments: yes

author:
- ins: H. Birkholz
  name: Henk Birkholz
  org: Fraunhofer SIT
  abbrev: Fraunhofer SIT
  email: henk.birkholz@sit.fraunhofer.de
  street: Rheinstrasse 75
  code: '64295'
  city: Darmstadt
  country: Germany
- ins: N. Cam-Winget
  name: Nancy Cam-Winget
  org: Cisco Systems
  email: ncamwing@cisco.com
  street: 3550 Cisco Way
  code: '95134'
  city: San Jose
  region: CA
  country: USA

normative:
  RFC2119:
#  RFC3635:
#  RFC1573:
#  I-D.greevenbosch-appsawg-cbor-cddl: cddl
#  I-D.ietf-sacm-architecture-13:

informative:
#  RFC7632:
#  I-D.ietf-sacm-requirements: sacm-req

--- abstract

The SACM Architecture Abstract (this is obviously a place-holder)

--- middle

# Introduction

Security Automation and Continuous Monitoring is conducted in a SACM domain. This document defines
the architectural components and corresponding roles a SACM Domain is composed of. The goal is to
enable interoperability between standard SACM Components and a minimal level of automated
orchestration that is always supported in a SACM Domain.

In consequence, this document also provides the reference terminology vital to security automation
or related to network-based remote assessment of security posture. Terms defined or referenced by
the SACM Architecture document are either not covered in or derived from RFC4949, or show an
impedance mismatch across existing standards and are unified via this document for future
application in the domain of security automation.

## Requirements notation

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT",
"SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and
"OPTIONAL" in this document are to be interpreted as described in RFC
2119, BCP 14 {{RFC2119}}.

# Roles in SACM

The architectural building blocks a SACM Domain is composed of are very modular. There are three
tiers of roles that facilitate this modular composability.

## Base Roles

Every endpoint that is part of a SACM Domain MUST take on at least one of the following roles:

* Either Target Endpoint or Excluded Endpoint, or
* SACM Component.

Target Endpoints are the endpoints of interest in a SACM Domain. Ultimately, these endpoints are
monitored continuously in order to enable security posture assessment, compliance assessment and
eventually remediation or mitigation of violations to security requirements in a SACM Domain. If an
endpoint that is part of the SACM Domain, is not a SACM Component and is not to be monitored, it
MUST take on the role of Excluded Endpoint.

SACM Components facilitate every activity conducted in a SACM Domain that enable security posture
assessment via specific functions, such as the collection (of measured or otherwise acquired
endpoint attributes) from data sources, the conveyance of annotated statements about security
posture, or the assessment via imperative and declarative guidance.

An endpoint MAY take on both the role of a Target Endpoint and a SACM Component. In this case,
information produced is fed directly into the SACM Domain by a software agent (that is a SACM
Component) residing on the Target Endpoint without the indirection of a collecting SACM Component.

## SACM Component Roles

Every SACM Component MAY incorporate functions that either produce information on the data-plane or
consume information on the data-plane. The corresponding two roles a SACM Component can take on are:

* Consumer of Information (in short: Consumer or Subscriber), and
* Provider of Information (in short: Provider or Publisher).

A SACM Component MAY take on both roles at once, for example, consuming information via one set of
functions, processing them internally, and then providing the results via another set of functions.

On the control-plane, every SACM Component MUST incorporate functions that enable it to take on the
role of an:

* Applicant, or
* Broker.

All activities of SACM components in a SACM domain MUST be orchestrated. Orchestration is
facilitated by conveying imperative guidance between Applicants and Brokers. Every Applicant MUST
register the functions it is designed to expose to the SACM Domain as Capabilities to a Broker. A
Broker MUST make the set of registered Capabilities (or a well-defined subset) available to other Applicants.

The set of Capabilities made available by a Broker SHOULD be restricted by a Content Authorization
function incorporated in Brokers.

## SACM Function Roles

Every function incorporated in a SACM Component MUST support the flow information and corresponding
processing of information in a SACM Domain. There is no finite list of SACM Functions, but there is a
well known set of functions for the control-plane and the management-plane:

* Registration Applicant and Applicant Registrar
* Collection Guidance Provider and Collection Guidance Consumer
* etc.pp. Note: Is this the correct level of detail or do we want "Collector" and "Assessor" here?

#  IANA considerations

This document may include requests to IANA some day.

#  Security Considerations

TBD

#  Acknowledgements

TBD

#  Change Log

First version -00

# Contributors

--- back
