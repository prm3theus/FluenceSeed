# FluenceSeed

A minimal fluence seed implementation as a CRU-based p2p project that uses BuffleDB as a wrapper to a hyper-based db

# How to use
1. First run `npx ts-node poster.ts`
2. Get PEER_ID from output
3. Fling particles `PEER_ID=<peer_id> npx ts-node poster.ts`

## BuffleDB, a promiss-able hypertrie wrapper

Run the tests via the `npx ts-node atlas.js`

```js
const hypertrie = require('hypertrie')
import Buffle from './Buffle'

// Timely chron to post to IPFS and email to vncntvango@gmail.com
const db = hypertrie('./trie.db', {valueEncoding: 'json'})

async function main() {
    const buf = new Buffle(db)

    console.log(await buf.post('peer2:0xC0FFEE', 2))
    console.log(await buf.post('peer2:0xC0FFEE', 5))
    console.log(await buf.post('m0na:0xC0FFEE', 1))

    console.log(await buf.getAll('peer2'))

    console.log(await buf.getReduced('peer2'))
    console.log(await buf.getReduced('m0na'))

    console.log(await buf.duplicate('peer2:C0FFEE'))
    console.log(await buf.duplicate('peer2:0xdeaf'))
}

main()
```

### api
* post(key, value)
* getReduced(key)
* getAll(key)
* duplicate(key)

# Tech stack
* fluence
* hypertrie

🦋
