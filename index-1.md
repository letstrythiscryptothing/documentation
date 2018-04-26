# Live Contracts specifications

_Contracts and laws should not be static pieces of paper, full of legal lingo that takes years to learn and understand. It should be dynamic, interactive and understandable for all parties involved._

### Note to Readers

The issues list for this draft can be found at [https://github.com/legalthings/livecontracts-specs/issues](https://github.com/legalthings/livecontracts-specs/issues). For additional information, see [http://livecontracts.io/](http://livecontracts.io/).

To provide feedback, use this issue tracker, the communication methods listed on the homepage, or email the document editors.

### Copyright Notice

Copyright \(c\) 2017 LegalThings One. All rights reserved.

You may use this specification under the [Creative Commons Attribution 4.0 International Public License](https://raw.githubusercontent.com/legalthings/livecontracts-specifications/master/LICENSE).

## General

### Cryptography

Live Contracts uses the `SHA256` to create a cryptographic hashes. The `Blake2b256` and `Keccak256` hashing algorithms are used for creating public/secret key pairs. The `ED25519` scheme is applied to create and verify signatures. `X25519` is used to for asymmetric encryption. For symmetric encrypt use `AES256` in Galois/Counter Mode \(gcm\). `Base58` is used to create the string from of bytes.

[Read more](https://github.com/legalthings/livecontracts-specs/tree/1f2cef267dfdf6fb694c3f8e878eb0af9a5cc284/cryptography.html)

### Network

Live Contracts relies on message brokers to share event chains between nodes. The message broker MUST use the `AMQP 0-9-1` to communicate and SHOULD be available over a secured connection.

[Read more](https://github.com/legalthings/livecontracts-specs/tree/1f2cef267dfdf6fb694c3f8e878eb0af9a5cc284/network.html)

## Specifications

The Live Contracts specifications are described as [JSON schema](http://json-schema.org/).

### 00 - LegalThings Resource Identifier \(LTRI\)

The LTRI follows a RESTful path structure to identify a resource. The resource collection is always plural. The LTRI does not identify the system, but it identifies a resource within a system.

[Read more](https://github.com/legalthings/livecontracts-specs/tree/1f2cef267dfdf6fb694c3f8e878eb0af9a5cc284/00-ltri/README.md)

### 01 - Event chain

The event chain is a miniature blockchain that is shared between parties involved in a contract or process. Each event is signed and that added referencing the previous event, forming a chain. All information of the system is derived from event chains.

[Read more](https://github.com/legalthings/livecontracts-specs/tree/1f2cef267dfdf6fb694c3f8e878eb0af9a5cc284/01-event-chain/README.md)

### 02 - Identity

An identity within the event chain. The identity is used for authentication and authorization. An identity is not a user, a user has an identity for each event chain it's participating in.

[Read more](https://github.com/legalthings/livecontracts-specs/tree/1f2cef267dfdf6fb694c3f8e878eb0af9a5cc284/02-identity/README.md)

### 03 - Template

The Live Contract template can be instantiated to create a contract. It holds a templated version of the natural language text, a form definition to collect the data and links to associated scenarios of the digitized procedures.

[Read more](https://github.com/legalthings/livecontracts-specs/tree/1f2cef267dfdf6fb694c3f8e878eb0af9a5cc284/03-template/README.md)

### 04 - Scenario

A Live Contract scenario is a definition of procedure as a Finite State Machine \(FSM\). As an FSM, the scenario can be visualized as flowchart and instantiated as a process.

[Read more](https://github.com/legalthings/livecontracts-specs/tree/1f2cef267dfdf6fb694c3f8e878eb0af9a5cc284/04-scenario/README.md)

### 05 - Action

In a process an actionmay be performed to trigger a state change or to update the process projection. For each action in the scenario, the `$schema` property MUST be set which is used to execute an action of to display it correctly in the UI.

[Read more](https://github.com/legalthings/livecontracts-specs/tree/1f2cef267dfdf6fb694c3f8e878eb0af9a5cc284/05-action/README.md)

### 06 - Actor

An actor is an identity or a group of identities that participate on a process. The actors are predefined in a scenario and instantiated for the process.

[Read more](https://github.com/legalthings/livecontracts-specs/tree/1f2cef267dfdf6fb694c3f8e878eb0af9a5cc284/06-actor/README.md)

### 07 - Data instruction

Data instructions allow you to dynamically set properties of a state or actions when they are instantiated using data from the projected process.

[Read more](https://github.com/legalthings/livecontracts-specs/tree/1f2cef267dfdf6fb694c3f8e878eb0af9a5cc284/07-data-instruction/README.md)

### 08 - Form

A Live Contracts form defines an input form with steps containing fields. Filling out fields results in a data set. The form and fields can be rendered directly to HTML or to JavaScript enabled widgets as with Angular or React.

[Read more](https://github.com/legalthings/livecontracts-specs/tree/1f2cef267dfdf6fb694c3f8e878eb0af9a5cc284/08-form/README.md)

### 09 - Form external

Forms MAY fetch external data through an HTTP GET request from a JSON REST API.

[Read more](https://github.com/legalthings/livecontracts-specs/tree/1f2cef267dfdf6fb694c3f8e878eb0af9a5cc284/09-form-external/README.md)

### 10 - Document

A document in natural language with related data and procedures.

[Read more](https://github.com/legalthings/livecontracts-specs/tree/1f2cef267dfdf6fb694c3f8e878eb0af9a5cc284/10-document/README.md)

### 11 - Process

A process is an instantation of a scenario. It is traversable, at any moment you are at a specific point in the process. A process is also a deterministic projection, generated by processing responses following the update instructions and transitions of the scenario.

[Read more](https://github.com/legalthings/livecontracts-specs/tree/1f2cef267dfdf6fb694c3f8e878eb0af9a5cc284/11-process/README.md)

### 12 - Response

Executing an action in a process always yields a response. This is regardless of whether the action is performed manually by the user of automatically by the node. A response may update the process projection and/or trigger a state transition.

[Read more](https://github.com/legalthings/livecontracts-specs/tree/1f2cef267dfdf6fb694c3f8e878eb0af9a5cc284/12-response/README.md)

### 13 - Comment

A comment is an arbitrary message that can be added to the event chain. It MAY be used for a chat-like feature, where messages are stored as part of the event chain. Everybody who has access to the event chain can read the comments.

[Read more](https://github.com/legalthings/livecontracts-specs/tree/1f2cef267dfdf6fb694c3f8e878eb0af9a5cc284/13-comment/README.md)

### 14 - Chain request

A node may request a chain or a portion of a chain. When an identity is registers, a node might request the full event chain for that identity. If a node receives an event, but can't find the corresponding previous event, it will request the missing event

[Read more](https://github.com/legalthings/livecontracts-specs/tree/1f2cef267dfdf6fb694c3f8e878eb0af9a5cc284/14-chain-request/README.md)

### 15 - Rejection

A node is required to validate if an event is valid before adding it to the event chain. Events that are invalid may be rejected.

[Read more](https://github.com/legalthings/livecontracts-specs/tree/1f2cef267dfdf6fb694c3f8e878eb0af9a5cc284/15-rejection/README.md)

### 16 - Conflict resolution

In any decentralized system conflicts can arise. Multiple nodes may add an event at the same time or a node might miss an event causing it to branch the chain. Because an event represents something that happened off-chain, we can't simply drop events instead they need to be added in such a way that it's visible that a conflict occurred.

[Read more](https://github.com/legalthings/livecontracts-specs/tree/1f2cef267dfdf6fb694c3f8e878eb0af9a5cc284/16-conflict-resolution/README.md)
