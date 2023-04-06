# TDB Developer Docs: Glossary

## Decentralized Web Node (DWN)
A Decentralized Web Node is a personal data store in a decentralized network that stores and shares information, serves as a communication channel, and executes transactions in a distributed manner, without relying on a centralized server, thereby enhancing security, privacy, and resilience of the network.

## Key Store

## Identity Vault

## Centralized Authority
A single entity or organization that has control over the network and its operations, potentially posing a risk to the principles of decentralization and autonomy.

## Decentralized Identifier (DID)
(From the spec) A globally unique persistent identifier that does not require a centralized registration authority and is often generated and/or registered cryptographically.

## DID Document
A DID Document is a small json object that has a field for your DID, called id.

{
  "@context": [
    "https://www.w3.org/ns/did/v1"
  ],
  "id": "did:example:123456789abcdefghi"
}
Every DID can be resolved to a corresponding DID document. A DID resolver is a mechanism that allows you to look up and retrieve the DID document associated with a particular DID.

If you type a URL into your browser, it resolves to a web page. Similarly, you can use a service to resolve a DID to a DID document. The document includes fields that help authenticate interactions with the DID.

## Did:Key
The did:key method is a simple, lightweight way to create a DID. It is based on a public key, and it is self-contained, meaning it does not rely on any external blockchain or registry. This makes did:key a convenient method for use cases that don't require the complexity and additional features provided by other DID methods.

## DID Method
A specific scheme for creating, resolving, updating, and deactivating DIDs and their associated documents, as outlined in a DID method specification which provides detailed instructions on these operations.

## Sidetree Protocol
The Sidetree protocol is a decentralized and blockchain-agnostic protocol that enables the creation and management of decentralized identifiers (DIDs) and their associated data off-chain, while utilizing the blockchain as a trust anchor for anchoring DID operations, thereby reducing the load on the blockchain and enhancing scalability.
