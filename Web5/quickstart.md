# Quickstart Web5

## Web5 in 5️⃣ minutes

We’re going to build a decentralized application on the Web5 platform - in under 5 minutes.

We’ll show you how to use features like messaging, reading, and writing to your personal data store. (do we need this sentence?)

Let’s go! 🚀

# Prerequisites

[Node Package Manager - NPM](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm)
Used to obtain the Web5 SDK, a JavaScript library

## Installation
This will install the Web5 module into your project using NPM. From the shell:
`$> npm install @tbd54566975/web5`

`Details element example (ALR note change this when the docs is in Docusaurus and we’ve got those features enabled)`

# Quickstart

1. Import the Web5 API into your application:

`import { Web5 } from '@tbd54566975/web5'`

2. Create Web5 instance:

There’s only one class for all Web5 operations

`const web5 = new Web5`

3. Create a Decentralized Identifier (DID):

In the world of Web5, your unique identifier, like an email address, is called a DID.

:Note: Learn more here(linked to DID page). (as a collapsable widget if we can)

`let did = await web5.did.create('ion');`

:Note: You are required to pass a method name when you create a DID. We’re defaulting to ion for this example but you can learn more about other method names here(Link to Learn Section).

Play with creating DIDs here:

[DEVIN’S WIDGET]

4. Register your DID:

Registering your DID gives others a way to find you, message you, and send you data (provided they have permissions).

```
await web5.did.register({
    connected: true,
    did: did.id,
    endpoint: 'app://dwn',
    keys: did.keys[0].keypair,
});
```

Register your DID from step one here:

[DEVIN’S WIDGET]

5. Now you’re able to write / store your data in a Decentralized Web Node (DWN):

The DWN is your personal data store - a home for messages, pictures, videos, and more. It’s how you retain ownership over your information. Later on you’ll have the opportunity to replicate it for redundancy. It can be hosted by others, but because the private information in your DWN is encrypted with your key - you’re in charge, and all your information is secure.

```
const data = 'Hello Web5';
console.log('write data', data);

let writeResult = await web5.dwn.records.write(did.id, {
    author: did.id,
    data,
    message: {
        schema: 'test',
        dataFormat: 'text/plain',
    },
});
console.log('write result', writeResult);
```

Practice writing something:

[DEVIN’S WIDGET]

6. Query

Here’s how you’re able to query anything you've saved in your DWN.

:note: The dataFormat value isn’t limited to image/png; it can be any MIME type.

```
let queryResult = await
    web5.dwn.records.query(did.id, {
        author: did.id,
        message: {
            filter: {
            schema: 'test',
        },
    },
});
console.log('query result', queryResult);
```

Now let's find some information about the data you just wrote:

[DEVIN’S WIDGET]

7. Reading your messages in DWN

```
let readResult = await web5.dwn.records.read(did.id, {
    author: did.id,
    message: {
        recordId: queryResult.entries[0].recordId,
    },
});
console.log('read result', readResult);
console.log('read data',
web5.dwn.SDK.Encoder.bytesToString(await web5.dwn.SDK.DataStream.toBytes(readResult.data)));
```

Now let's get the actual data for the information we just got (edit this sentence):

[DEVIN’S WIDGET]

8. Deleting messages in your DWN

let deleteResult = await web5.dwn.records.delete(did.id, {
    author: did.id,
    message: {
        recordId: queryResult.entries[0].recordId,
    },
});
console.log('delete result', deleteResult);

[DEVIN’S WIDGET]

Next Steps:
1. Learn more about DIDs (link to DID page)
2. Build your first ToDo app (link coming soon)
3. Learn what to do with a DID externally(linked in build>DID>how-to-use-externa..)