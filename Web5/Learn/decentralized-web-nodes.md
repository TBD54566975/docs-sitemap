
## Decentralized Web Nodes 

A Decentralized Web Node is a data storage and message relay mechanism that entities can use to locate public or private permissioned data related to a given DID.

[diagram expressing all of these concepts]


### Personal Data Store
A DWN is a personal data store. This means you can:
- **Own your data:** You decide where to host your node. You control who has access.
- **Back up your data:** Host multiple nodes in different places, keep them all synced. If one goes down, you have your back up. When it comes back up, the sync is effortless.
- **Send and receive data:** Alice controls her DWN using her DID. Bob controls his DWN with his DID. Alice can send data to Bob just by resolving his DID.

[image of Alice sending Bob data]

### Authorization
* Note: Revisit in more detail: permissions are explicit and manual vs protocols are descriptive, syntactic, and contractual

DWNs have two mechanisms to allow others access to read, write, or delete data on you node.
- **Permissions:** Allow someone access to read, write, or delete specific data records on your node.
- **Protocols:** Install a protocol that lets you define data types and authorization for a decentralized web app.

### Data Model
Data types are bound to known schemas, letting applications agree on data models. This opens the door to applications working together in ways that's been much more difficult in traditional development platform.

### Messaging
* Note: Might add code example of message structure here

All communication is done through simple messages. Web5 makes this easy, erasing the messy mechanics of decentralized messaging. DWN Messages follow a general structure, for example a DWN requesting containing multiple messages will have a the following shape. See the [DWN spec](https://identity.foundation/decentralized-web-node/spec/#messages) for a detailed explanation of each field.

```json 
{  // Request Object
  "messages": [  // Message Objects
    {
      "recordId": GENERATED_CID_STRING,
      "descriptor": {
        "interface": INTERFACE_STRING,
        "method": METHOD_STRING,
        "dataCid": DATA_CID_STRING,
        "dataFormat": DATA_FORMAT_STRING,
      }
    },
    {...}
  ]
}
```
