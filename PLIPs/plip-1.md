---
plip: 1
title: PLIP Purpose and Guidelines
status: Draft
type: Meta
author: Karl Floersch <karl@plasma.group>, but most of this was originally written by Martin Becze <mb@ethereum.org>, Hudson Jameson <hudson@ethereum.org>, and others here https://github.com/ethereum/EIPs/blob/master/EIPS/eip-1.md
created: 2019-07-08
---

## What is a PLIP?

PLIP stands for Plasma Improvement Proposal. A PLIP is a design document providing information to the Plasma community, or describing a new feature for Plasma or its processes or environment. The PLIP should provide a concise technical specification of the feature and a rationale for the feature. The PLIP author is responsible for building consensus within the community and documenting dissenting opinions.

## PLIP Rationale

We intend PLIPs to be the primary mechanisms for proposing new features, for collecting community technical input on an issue, and for documenting the design decisions that have gone into Plasma. Because the PLIPs are maintained as text files in a versioned repository, their revision history is the historical record of the feature proposal.

For Plasma implementers, PLIPs are a convenient way to track the progress of their implementation. Ideally each implementation maintainer would list the PLIPs that they have implemented. This will give end users a convenient way to know the current status of a given implementation or library.

## PLIP Types

There are three types of PLIP:

- A **Standard Track PLIP** describes any change that affects most or all Plasma implementations, such as a change to the network protocol, a change in block or transaction validity rules, proposed application standards/conventions, or any change or addition that affects the interoperability of applications using Plasma. Furthermore Standard PLIPs can be broken down into the following categories. Standards Track PLIPs consist of three parts, a design document, implementation, and finally if warranted an update to the [formal specification].
  - **Core** - improvements which affect the core OVM (Optimistic Virtual Machine) or break backwards compatibility.
  - **Networking** - improvements around the communication layer for plasma implementations.
  - **Interface** - improvements around client [API/RPC] specifications and standards, and also certain language-level standards like method names and contract APIs.
  - **PRC** - application-level standards and conventions, including contract standards such as token standards (eg. minting logic), name registries, library/package formats, and wallet formats.
- A **Meta PLIP** describes a process surrounding Plasma or proposes a change to (or an event in) a process. Process PLIPs are like Standards Track PLIPs but apply to areas other than the Plasma protocol itself. They may propose an implementation, but not to Plasma's codebase; they often require community consensus; unlike Informational PLIPs, they are more than recommendations, and users are typically not free to ignore them. Examples include procedures, guidelines, changes to the decision-making process, and changes to the tools or environment used in Plasma development. Any meta-PLIP is also considered a Process PLIP.
- An **Informational PLIP** describes an Plasma design issue, or provides general guidelines or information to the Plasma community, but does not propose a new feature. Informational PLIPs do not necessarily represent Plasma community consensus or a recommendation, so users and implementers are free to ignore Informational PLIPs or follow their advice.

It is highly recommended that a single PLIP contain a single key proposal or new idea. The more focused the PLIP, the more successful it tends to be. A change to one client doesn't require a PLIP; a change that affects multiple clients, or defines a standard for multiple apps to use, does.

A PLIP must meet certain minimum criteria. It must be a clear and complete description of the proposed enhancement. The enhancement must represent a net improvement. The proposed implementation, if applicable, must be solid and must not complicate the protocol unduly.

## PLIP Work Flow

Parties involved in the process are you, the champion or *PLIP author*, the [*PLIP editors*](#plip-editors), and the affected plasma community.

:warning: Before you begin, vet your idea, this will save you time. Ask the Plasma community first if an idea is original to avoid wasting time on something that will be rejected based on prior research (searching the Internet does not always do the trick). It also helps to make sure the idea is applicable to the entire community and not just the author. Just because an idea sounds good to the author does not mean it will work for most people in most areas where Plasma is used. Examples of appropriate public forums to gauge interest around your PLIP include [the plasma.build forum], and [the Issues section of this repository]. In particular, [the Issues section of this repository] is an excellent place to discuss your proposal with the community and start creating more formalized language around your PLIP.

Your role as the champion is to write the PLIP using the style and format described below, shepherd the discussions in the appropriate forums, and build community consensus around the idea. Following is the process that a successful PLIP will move along:

```
[ WIP ] -> [ DRAFT ] -> [ LAST CALL ] -> [ ACCEPTED ] -> [ FINAL ]
```

Each status change is requested by the PLIP author and reviewed by the PLIP editors. Use a pull request to update the status. Please include a link to where people should continue discussing your PLIP. The PLIP editors will process these requests as per the conditions below.

* **Active** -- Some Informational and Process PLIPs may also have a status of “Active” if they are never meant to be completed. E.g. PLIP 1 (this PLIP).
* **Work in progress (WIP)** -- Once the champion has asked the Plasma community whether an idea has any chance of support, they will write a draft PLIP as a [pull request]. Consider including an implementation if this will aid people in studying the PLIP.
  * :arrow_right: Draft -- If agreeable, PLIP editor will assign the PLIP a number (generally the issue or PR number related to the PLIP) and merge your pull request. The PLIP editor will not unreasonably deny a PLIP.
  * :x: Draft -- Reasons for denying draft status include being too unfocused, too broad, duplication of effort, being technically unsound, not providing proper motivation or addressing backwards compatibility, or not in keeping with the [Ethereum philosophy](https://github.com/ethereum/wiki/wiki/White-Paper#philosophy) which us plasma folks embrace.
* **Draft** -- Once the first draft has been merged, you may submit follow-up pull requests with further changes to your draft until such point as you believe the PLIP to be mature and ready to proceed to the next status. A PLIP in draft status must be implemented to be considered for promotion to the next status (ignore this requirement for core PLIPs).
  * :arrow_right: Last Call -- If agreeable, the PLIP editor will assign Last Call status and set a review end date (`review-period-end`), normally 14 days later.
  * :x: Last Call -- A request for Last Call status will be denied if material changes are still expected to be made to the draft. We hope that PLIPs only enter Last Call once, so as to avoid unnecessary noise on the RSS feed.
* **Last Call** -- This PLIP will soon be listed prominently on the https://plips.plasma.group/ website once we get it set up.
  * :x: -- A Last Call which results in material changes or substantial unaddressed technical complaints will cause the PLIP to revert to Draft.
  * :arrow_right: Accepted (Core PLIPs only) -- A successful Last Call without material changes or unaddressed technical complaints will become Accepted.
  * :arrow_right: Final (Not core PLIPs) -- A successful Last Call without material changes or unaddressed technical complaints will become Final.
* **Accepted (Core PLIPs only)** -- This PLIP is in the hands of the Plasma client developers.  Their process for deciding whether to encode it into their clients is not part of the PLIP process.
  * :arrow_right: Final -- Standards Track Core PLIPs must be implemented in multiple viable Plasma clients before it can be considered Final. When the implementation is complete and adopted by the community, the status will be changed to “Final”.
* **Final** -- This PLIP represents the current state-of-the-art. A Final PLIP should only be updated to correct errata.

Other exceptional statuses include:

* **Deferred** -- This is for core PLIPs that have been put off for a future release.
* **Rejected** -- A PLIP that is fundamentally broken or a Core PLIP that was rejected by the Core Devs and will not be implemented.
* **Active** -- This is similar to Final, but denotes a PLIP which may be updated without changing its PLIP number.
* **Superseded** -- A PLIP which was previously final but is no longer considered state-of-the-art. Another PLIP will be in Final status and reference the Superseded PLIP.

## What belongs in a successful PLIP?

Each PLIP should have the following parts:

- Preamble - RFC 822 style headers containing metadata about the PLIP, including the PLIP number, a short descriptive title (limited to a maximum of 44 characters), and the author details. See [below](#plip-header-preamble) for details.
- Simple Summary - “If you can’t explain it simply, you don’t understand it well enough.” Provide a simplified and layman-accessible explanation of the PLIP.
- Abstract - a short (~200 word) description of the technical issue being addressed.
- Motivation (*optional) - The motivation is critical for PLIPs that want to change the Plasma protocol. It should clearly explain why the existing protocol specification is inadequate to address the problem that the PLIP solves. PLIP submissions without sufficient motivation may be rejected outright.
- Specification - The technical specification should describe the syntax and semantics of any new feature. The specification should be detailed enough to allow competing, interoperable implementations for any of the current Plasma platforms.
- Rationale - The rationale fleshes out the specification by describing what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work, e.g. how the feature is supported in other languages. The rationale may also provide evidence of consensus within the community, and should discuss important objections or concerns raised during discussion.
- Backwards Compatibility - All PLIPs that introduce backwards incompatibilities must include a section describing these incompatibilities and their severity. The PLIP must explain how the author proposes to deal with these incompatibilities. PLIP submissions without a sufficient backwards compatibility treatise may be rejected outright.
- Test Cases - Test cases for an implementation are mandatory for PLIPs that break backward compatibility. Other PLIPs can choose to include links to test cases if applicable.
- Implementations - The implementations must be completed before any PLIP is given status “Final”, but it need not be completed before the PLIP is merged as draft. While there is merit to the approach of reaching consensus on the specification and rationale before writing code, the principle of “rough consensus and running code” is still useful when it comes to resolving many discussions of API details.
- Copyright Waiver - All PLIPs must be in the public domain. See the bottom of this PLIP for an example copyright waiver.

## PLIP Formats and Templates

PLIPs should be written in [markdown] format.
Image files should be included in a subdirectory of the `assets` folder for that PLIP as follows: `assets/eip-X` (for eip **X**). When linking to an image in the PLIP, use relative links such as `../assets/eip-X/image.png`.

## PLIP Header Preamble

Each PLIP must begin with an [RFC 822](https://www.ietf.org/rfc/rfc822.txt) style header preamble, preceded and followed by three hyphens (`---`). This header is also termed ["front matter" by Jekyll](https://jekyllrb.com/docs/front-matter/). The headers must appear in the following order. Headers marked with "*" are optional and are described below. All other headers are required.

` plip:` <PLIP number> (this is determined by the PLIP editor)

` title:` <PLIP title>

` author:` <a list of the author's or authors' name(s) and/or username(s), or name(s) and email(s). Details are below.>

` * discussions-to:` \<a url pointing to the official discussion thread\>

` status:` <Draft | Last Call | Accepted | Final | Active | Deferred | Rejected | Superseded>

`* review-period-end:` <date review period ends>

` type:` <Standards Track (Core, Networking, Interface, PRC)  | Informational | Meta>

` * category:` <Core | Networking | Interface | PRC>

` created:` <date created on>

` * updated:` <comma separated list of dates>

` * requires:` <PLIP number(s)>

` * replaces:` <PLIP number(s)>

` * superseded-by:` <PLIP number(s)>

` * resolution:` \<a url pointing to the resolution of this PLIP\>

Headers that permit lists must separate elements with commas.

Headers requiring dates will always do so in the format of ISO 8601 (yyyy-mm-dd).

#### `author` header

The `author` header optionally lists the names, email addresses or usernames of the authors/owners of the PLIP. Those who prefer anonymity may use a username only, or a first name and a username. The format of the author header value must be:

> Random J. User &lt;address@dom.ain&gt;

or

> Random J. User (@username)

if the email address or GitHub username is included, and

> Random J. User

if the email address is not given.

#### `resolution` header

The `resolution` header is required for Standards Track PLIPs only. It contains a URL that should point to an email message or other web resource where the pronouncement about the PLIP is made.

#### `discussions-to` header

While a PLIP is a draft, a `discussions-to` header will indicate the mailing list or URL where the PLIP is being discussed. As mentioned above, examples for places to discuss your PLIP include this repository, [plasma.build](https://plasma.build/), and the [plasma contributors telegram group](https://t.me/plasmacontributors).

No `discussions-to` header is necessary if the PLIP is being discussed privately with the author.

As a single exception, `discussions-to` cannot point to GitHub pull requests.

#### `type` header

The `type` header specifies the type of PLIP: Standards Track, Meta, or Informational. If the track is Standards please include the subcategory (core, networking, interface, or PRC).

#### `category` header

The `category` header specifies the PLIP's category. This is required for standards-track PLIPs only.

#### `created` header

The `created` header records the date that the PLIP was assigned a number. Both headers should be in yyyy-mm-dd format, e.g. 2001-08-14.

#### `updated` header

The `updated` header records the date(s) when the PLIP was updated with "substantial" changes. This header is only valid for PLIPs of Draft and Active status.

#### `requires` header

PLIPs may have a `requires` header, indicating the PLIP numbers that this PLIP depends on.

#### `superseded-by` and `replaces` headers

PLIPs may also have a `superseded-by` header indicating that a PLIP has been rendered obsolete by a later document; the value is the number of the PLIP that replaces the current document. The newer PLIP must have a `replaces` header containing the number of the PLIP that it rendered obsolete.

## Auxiliary Files

PLIPs may include auxiliary files such as diagrams. Such files must be named PLIP-XXXX-Y.ext, where “XXXX” is the PLIP number, “Y” is a serial number (starting at 1), and “ext” is replaced by the actual file extension (e.g. “png”).

## Transferring PLIP Ownership

It occasionally becomes necessary to transfer ownership of PLIPs to a new champion. In general, we'd like to retain the original author as a co-author of the transferred PLIP, but that's really up to the original author. A good reason to transfer ownership is because the original author no longer has the time or interest in updating it or following through with the PLIP process, or has fallen off the face of the 'net (i.e. is unreachable or isn't responding to email). A bad reason to transfer ownership is because you don't agree with the direction of the PLIP. We try to build consensus around a PLIP, but if that's not possible, you can always submit a competing PLIP.

If you are interested in assuming ownership of a PLIP, send a message asking to take over, addressed to both the original author and the PLIP editor. If the original author doesn't respond to email in a timely manner, the PLIP editor will make a unilateral decision (it's not like such decisions can't be reversed :)).

## PLIP Editors

The current PLIP editors are

...`No one!`

PLIP editors may be added based on a show of consistent contribution and enthusiasm for filling the role.

## PLIP Editor Responsibilities

For each new PLIP that comes in, an editor does the following:

- Read the PLIP to check if it is ready: sound and complete. The ideas must make technical sense, even if they don't seem likely to get to final status.
- The title should accurately describe the content.
- Check the PLIP for language (spelling, grammar, sentence structure, etc.), markup (Github flavored Markdown), code style

If the PLIP isn't ready, the editor will send it back to the author for revision, with specific instructions.

Once the PLIP is ready for the repository, the PLIP editor will:

- Assign a PLIP number (generally the PR number or, if preferred by the author, the Issue # if there was discussion in the Issues section of this repository about this PLIP)

- Merge the corresponding pull request

- Send a message back to the PLIP author with the next step.

Many PLIPs are written and maintained by developers with write access to this codebase. The PLIP editors monitor PLIP changes, and correct any structure, grammar, spelling, or markup mistakes we see.

The editors don't pass judgment on PLIPs. We merely do the administrative & editorial part.
