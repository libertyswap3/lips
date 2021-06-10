---
Lip: 1
title: LIP Purpose and Guidelines
status: Living
type: Meta
author: James <James485713@yahoo.com>
created: 2021-06-10
---

## What is an LIP?

LIP stands for Libertyswap Improvement Proposal. An LIP is a design document providing information to the Libertyswap community, or describing a new feature for Libertyswap or its processes or environment. The lIP should provide a concise technical specification of the feature and a rationale for the feature. The LIP author is responsible for building consensus within the community and documenting dissenting opinions.

## LIP Rationale

We intend LIPs to be the primary mechanisms for proposing new features, for collecting community technical input on an issue, and for documenting the design decisions that have gone into Libertyswap. Because the LIPs are maintained as text files in a versioned repository, their revision history is the historical record of the feature proposal.

For Libertyswap implementers, LIPs are a convenient way to track the progress of their implementation. Ideally each implementation maintainer would list the LIPs that they have implemented. This will give end users a convenient way to know the current status of a given implementation or library.

## LIP Types

There are three types of LIP:

- A **Standards Track LIP** describes any change that affects most or all Libertyswap implementations, such as—a change to the network protocol, a change in block or transaction validity rules, proposed application standards/conventions, or any change or addition that affects the interoperability of applications using Libertyswap. Standards Track LIPs consist of three parts—a design document, an implementation, and (if warranted) an update to the [formal specification]. Furthermore, Standards Track LIPs can be broken down into the following categories:
 
- A **Meta LIP** describes a process surrounding Libertyswap or proposes a change to (or an event in) a process. Process LIPs are like Standards Track LIPs but apply to areas other than the Libertyswap protocol itself. They may propose an implementation, but not to Libertyswap's codebase; they often require community consensus; unlike Informational LIPs, they are more than recommendations, and users are typically not free to ignore them. Examples include procedures, guidelines, changes to the decision-making process, and changes to the tools or environment used in Libertyswap development. Any meta-LIP is also considered a Process LIP.

- An **Informational LIP** describes an Libertyswap design issue, or provides general guidelines or information to the Libertyswap community, but does not propose a new feature. Informational LIPs do not necessarily represent Libertyswap community consensus or a recommendation, so users and implementers are free to ignore Informational LIPs or follow their advice.

It is highly recommended that a single LIP contain a single key proposal or new idea. The more focused the LIP, the more successful it tends to be. A change to one client doesn't require an LIP; a change that affects multiple clients, or defines a standard for multiple apps to use, does.

An LIP must meet certain minimum criteria. It must be a clear and complete description of the proposed enhancement. The enhancement must represent a net improvement. The proposed implementation, if applicable, must be solid and must not complicate the protocol unduly.

### Special requirements for Core LIPs

If a **Core** LIP mentions or proposes changes to the EVM (Libertyswap Virtual Machine), it should refer to the instructions by their mnemonics and define the opcodes of those mnemonics at least once. A preferred way is the following:
```
REVERT (0xfe)
```

## LIP Work Flow

### Shepherding an LIP

Parties involved in the process are you, the champion or *LIP author*, the [*LIP editors*](#LIP-editors).

Before you begin writing a formal LIP, you should vet your idea. Ask the Libertyswap community first if an idea is original to avoid wasting time on something that will be rejected based on prior research.  

Once the idea has been vetted, your next responsibility will be to present (by means of an LIP) the idea to the reviewers and all interested parties, invite editors, developers, and the community to give feedback on the aforementioned channels. You should try and gauge whether the interest in your LIP is commensurate with both the work involved in implementing it and how many parties will have to conform to it. For example, the work required for implementing a Core LIP will be much greater than for an ERC and the LIP will need sufficient interest from the Libertyswap client teams. Negative community feedback will be taken into consideration and may prevent your LIP from moving past the Draft stage.

### Core LIPs

For Core LIPs, given that they require client implementations to be considered **Final** (see "LIPs Process" below), you will need to either provide an implementation for clients or convince clients to implement your LIP. 

The best way to get client implementers to review your LIP is to present it on an AllCoreDevs call. You can request to do so by posting a comment linking your LIP on an [AllCoreDevs agenda GitHub Issue].  

The AllCoreDevs call serve as a way for client implementers to do three things. First, to discuss the technical merits of LIPs. Second, to gauge what other clients will be implementing. Third, to coordinate LIP implementation for network upgrades.

These calls generally result in a "rough consensus" around what LIPs should be implemented. This "rough consensus" rests on the assumptions that LIPs are not contentious enough to cause a network split and that they are technically sound.

:warning: The LIPs process and AllCoreDevs call were not designed to address contentious non-technical issues, but, due to the lack of other ways to address these, often end up entangled in them. This puts the burden on client implementers to try and gauge community sentiment, which hinders the technical coordination function of LIPs and AllCoreDevs calls. If you are shepherding an LIP, you can make the process of building community consensus easier by making sure that thread for your LIP includes or links to as much of the community discussion as possible and that various stakeholders are well-represented.

*In short, your role as the champion is to write the LIP using the style and format described below, shepherd the discussions in the appropriate forums, and build community consensus around the idea.* 

### LIP Process 

The following is the standardization process for all LIPs in all tracks:

![LIP Status Diagram](../assets/LIP-1/LIP-process.png)

**Idea** - An idea that is pre-draft. This is not tracked within the LIP Repository.

**Draft** - The first formally tracked stage of an LIP in development. An LIP is merged by an LIP Editor into the LIP repository when properly formatted.

**Review** - An LIP Author marks an LIP as ready for and requesting Peer Review.

**Last Call** - This is the final review window for an LIP before moving to `FINAL`. An LIP editor will assign `Last Call` status and set a review end date (review-period-end), typically 14 days later.

If this period results in necessary normative changes it will revert the LIP to `REVIEW`.

**Final** - This LIP represents the final standard. A Final LIP exists in a state of finality and should only be updated to correct errata and add non-normative clarifications.

**Stagnant** - Any LIP in `DRAFT` or `REVIEW` if inactive for a period of 6 months or greater is moved to `STAGNANT`. An LIP may be resurrected from this state by Authors or LIP Editors through moving it back to `DRAFT`.

>*LIP Authors are notified of any algorithmic change to the status of their LIP*

**Withdrawn** - The LIP Author(s) have withdrawn the proposed LIP. This state has finality and can no longer be resurrected using this LIP number. If the idea is pursued at later date it is considered a new proposal.

**Living** - A special status for LIPs that are designed to be continually updated and not reach a state of finality. This includes most notably LIP-1. Any changes to these LIPs will move between `REVIEW` and `LIVING` states.

## What belongs in a successful LIP?

Each LIP should have the following parts:

- Preamble - RFC 822 style headers containing metadata about the LIP, including the LIP number, a short descriptive title (limited to a maximum of 44 characters), and the author details. See [below](./LIP-1.md#LIP-header-preamble) for details.
- Abstract - A short (~200 word) description of the technical issue being addressed.
- Motivation (*optional) - A motivation section is critical for LIPs that want to change the Libertyswap protocol. It should clearly explain why the existing protocol specification is inadequate to address the problem that the LIP solves. LIP submissions without sufficient motivation may be rejected outright.
- Specification - The technical specification should describe the syntax and semantics of any new feature. The specification should be detailed enough to allow competing, interoperable implementations for any of the current Libertyswap platforms (cpp-Libertyswap, go-Libertyswap, parity, LibertyswapJ, Libertyswapjs-lib, [and others](https://github.com/Libertyswap/wiki/wiki/Clients).
- Rationale - The rationale fleshes out the specification by describing what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work, e.g. how the feature is supported in other languages. The rationale may also provide evidence of consensus within the community, and should discuss important objections or concerns raised during discussion.
- Backwards Compatibility - All LIPs that introduce backwards incompatibilities must include a section describing these incompatibilities and their severity. The LIP must explain how the author proposes to deal with these incompatibilities. LIP submissions without a sufficient backwards compatibility treatise may be rejected outright.
- Test Cases - Test cases for an implementation are mandatory for LIPs that are affecting consensus changes. Tests should either be inlined in the LIP as data (such as input/expected output pairs, or included in `../assets/LIP-###/<filename>`.
- Reference Implementation - An optional section that contains a reference/example implementation that people can use to assist in understanding or implementing this specification.
- Security Considerations - All LIPs must contain a section that discusses the security implications/considerations relevant to the proposed change. Include information that might be important for security discussions, surfaces risks and can be used throughout the life-cycle of the proposal. E.g. include security-relevant design decisions, concerns, important discussions, implementation-specific guidance and pitfalls, an outline of threats and risks and how they are being addressed. LIP submissions missing the "Security Considerations" section will be rejected. An LIP cannot proceed to status "Final" without a Security Considerations discussion deemed sufficient by the reviewers.
- Copyright Waiver - All LIPs must be in the public domain. See the bottom of this LIP for an example copyright waiver.

## LIP Formats and Templates

LIPs should be written in [markdown] format. There is a [template](https://github.com/Libertyswap/LIPs/blob/master/LIP-template.md) to follow.

## LIP Header Preamble

Each LIP must begin with an [RFC 822](https://www.ietf.org/rfc/rfc822.txt) style header preamble, preceded and followed by three hyphens (`---`). The headers must appear in the following order. Headers marked with "*" are optional and are described below. All other headers are required.

` LIP:` *LIP number* (this is determined by the LIP editor)

` title:` *LIP title*

` author:` *a list of the author's or authors' name(s) and/or username(s), or name(s) and email(s). Details are below.*

` * discussions-to:` *a url pointing to the official discussion thread*

` status:` *Draft, Review, Last Call, Final, Stagnant, Withdrawn, Living*

`* review-period-end:` *date review period ends*

` type:` *Standards Track, Meta, or Informational*

` * category:` *Core, Networking, Interface, or ERC* (fill out for Standards Track LIPs only)

` created:` *date created on*

` * updated:` *comma separated list of dates*

` * requires:` *LIP number(s)*

` * replaces:` *LIP number(s)*

` * superseded-by:` *LIP number(s)*

` * resolution:` *a url pointing to the resolution of this LIP*

Headers that permit lists must separate elements with commas.

Headers requiring dates will always do so in the format of ISO 8601 (yyyy-mm-dd).

#### `author` header

The `author` header lists the names, email addresses or usernames of the authors/owners of the LIP. Those who prefer anonymity may use a username only, or a first name and a username. The format of the `author` header value must be:

> Random J. User &lt;address@dom.ain&gt;

or

> Random J. User (@username)

if the email address or GitHub username is included, and

> Random J. User

if the email address is not given.

It is not possible to use both an email and a GitHub username at the same time. If important to include both, one could include their name twice, once with the GitHub username, and once with the email.

At least one author must use a GitHub username, in order to get notified on change requests and have the capability to approve or reject them.

#### `resolution` header

The `resolution` header is required for Standards Track LIPs only. It contains a URL that should point to an email message or other web resource where the pronouncement about the LIP is made.

#### `discussions-to` header

While an LIP is a draft, a `discussions-to` header will indicate the mailing list or URL where the LIP is being discussed. 
No `discussions-to` header is necessary if the LIP is being discussed privately with the author.

As a single exception, `discussions-to` cannot point to GitHub pull requests.

#### `type` header

The `type` header specifies the type of LIP: Standards Track, Meta, or Informational. If the track is Standards please include the subcategory (core, networking, interface, or ERC).

#### `category` header

The `category` header specifies the LIP's category. This is required for standards-track LIPs only.

#### `created` header

The `created` header records the date that the LIP was assigned a number. Both headers should be in yyyy-mm-dd format, e.g. 2001-08-14.

#### `updated` header

The `updated` header records the date(s) when the LIP was updated with "substantial" changes. This header is only valid for LIPs of Draft and Active status.

#### `requires` header

LIPs may have a `requires` header, indicating the LIP numbers that this LIP depends on.

#### `superseded-by` and `replaces` headers

LIPs may also have a `superseded-by` header indicating that an LIP has been rendered obsolete by a later document; the value is the number of the LIP that replaces the current document. The newer LIP must have a `replaces` header containing the number of the LIP that it rendered obsolete.

## Linking to other LIPs

References to other LIPs should follow the format `LIP-N` where `N` is the LIP number you are referring to.  Each LIP that is referenced in an LIP **MUST** be accompanied by a relative markdown link the first time it is referenced, and **MAY** be accompanied by a link on subsequent references.  The link **MUST** always be done via relative paths so that the links work in this GitHub repository, forks of this repository, the main LIPs site, mirrors of the main LIP site, etc.  For example, you would link to this LIP with `[LIP-1](./LIP-1.md)`.

## Auxiliary Files

Images, diagrams and auxiliary files should be included in a subdirectory of the `assets` folder for that LIP as follows: `assets/LIP-N` (where **N** is to be replaced with the LIP number). When linking to an image in the LIP, use relative links such as `../assets/LIP-1/image.png`.

## Transferring LIP Ownership

It occasionally becomes necessary to transfer ownership of LIPs to a new champion. In general, we'd like to retain the original author as a co-author of the transferred LIP, but that's really up to the original author. A good reason to transfer ownership is because the original author no longer has the time or interest in updating it or following through with the LIP process, or has fallen off the face of the 'net (i.e. is unreachable or isn't responding to email). A bad reason to transfer ownership is because you don't agree with the direction of the LIP. We try to build consensus around an LIP, but if that's not possible, you can always submit a competing LIP.

If you are interested in assuming ownership of an LIP, send a message asking to take over, addressed to both the original author and the LIP editor. If the original author doesn't respond to the email in a timely manner, the LIP editor will make a unilateral decision (it's not like such decisions can't be reversed :)).

## LIP Editors

The current LIP editors are

- James (@James)

## LIP Editor Responsibilities

For each new LIP that comes in, an editor does the following:

- Read the LIP to check if it is ready: sound and complete. The ideas must make technical sense, even if they don't seem likely to get to final status.
- The title should accurately describe the content.
- Check the LIP for language (spelling, grammar, sentence structure, etc.), markup (GitHub flavored Markdown), code style

If the LIP isn't ready, the editor will send it back to the author for revision, with specific instructions.

Once the LIP is ready for the repository, the LIP editor will:

- Assign an LIP number (generally the PR number or, if preferred by the author, the Issue # if there was discussion in the Issues section of this repository about this LIP)

- Merge the corresponding pull request

- Send a message back to the LIP author with the next step.

Many LIPs are written and maintained by developers with write access to the Libertyswap codebase. The LIP editors monitor LIP changes, and correct any structure, grammar, spelling, or markup mistakes we see.

The editors don't pass judgment on LIPs. We merely do the administrative & editorial part.

## Style Guide

When referring to an LIP by number, it should be written in the hyphenated form `LIP-X` where `X` is the LIP's assigned number.

## History

This document was derived heavily from [Bitcoin's BIP-0001] written by Amir Taaki which in turn was derived from [Python's PEP-0001]. In many places text was simply copied and modified. Although the PEP-0001 text was written by Barry Warsaw, Jeremy Hylton, and David Goodger, they are not responsible for its use in the Libertyswap Improvement Process, and should not be bothered with technical questions specific to Libertyswap or the LIP. Please direct all comments to the LIP editors.

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
