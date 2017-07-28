---
title: SACM Information Model
docname: birkholz-sacm-architecture-latest
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
  # I-D.ietf-sacm-architecture-13:
 
informative:
#  RFC7632:
  I-D.ietf-sacm-requirements: sacm-req

--- abstract

The SACM Architecture Abstract (this is obviously a place-holder)

--- middle

# Introduction

Security Automation and Continuous Monitoring is conducted in a SACM domain. This document defines the architectural components and corresponding roles a SACM Domain is composed of. The goal is to enable interoperability between standard SACM Components and a minimal level of automated orchestration that is always supported in a SACM Domain.
In consequence, this document also provides the reference terminology vital to security automation or related to network-based remote assessment of security posture. Terms defined or referenced by the SACM Architecture document are either not covered in or derived from RFC4949, or show an impedance mismatch across existing standards and are unified via this document for future application in the domain of security automation.

## Requirements notation

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT",
"SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and
"OPTIONAL" in this document are to be interpreted as described in RFC
2119, BCP 14 {{RFC2119}}.

# Roles in SACM

The architectural building blocks a SACM domain is composed of are very modular. There are three tiers of roles that facilitate this modular composability.

## Base Roles

Every endpoint that is part of a SACM domain can take one or two of the following base roles:

* Target Endpoint, and
* SACM Component.

Target Endpoints are the endpoints of interest a SACM domain. Ultimately, these endpoints are monitored continuously in order to enable security posture assessment, compliance assessment and eventually remediation or mitigation of violations to security requirements in a SACM Domain.

SACM Components facilitate every activity conducted in a SACM domain, such as collection (of measured or acuirelife data), the conveyance 

SACM component roles:

SACM function roles:

#  IANA considerations

This document might include requests to IANA at some point

#  Security Considerations

#  Acknowledgements

#  Change Log

First version -00

# Contributors

--- back
