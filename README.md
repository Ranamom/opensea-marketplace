[![Puppycat_pose](https://emoji.gg/assets/emoji/8285-puppycat-pose.png)](https://emoji.gg/emoji/8285-puppycat-pose)

## Build OpenSea Blockchain Web 3.0 App with Next.js | Sanity.io | thirdweb

#### [check the video tutorial here](https://youtu.be/x3eRXeMB-4k)

<br>

#### Check this other tutorial for more details on this <u>Topic</u>

##### [Build your own NFT marketplace like OpenSea clone with solidity,openzeppelin and polygon (SUBSCRIBE)](https://youtu.be/7Q5E6RvLlUw)

<br>

---

<br>

# Docs

> **Blockchain development:** Smart Contracts, security, IDE, Truffle & hardhat, Etherscan, Dapp | **NFT:** ERC's ... [all here](./z_articles.md) ✋

<br>
<br>

## Interesting articles & links:

##### How to make money with NFT as a developer?

[How to make money with NFT as a developer?](https://youtu.be/5_Wu_X4LnAw)

<br>

##### NFT Marketplaces

> NFT marketplace rankings and analysis. Find non-fungible token trading volumes, number of traders per NFT marketplace and more key metrics.

[NFT Marketplaces](https://dappradar.com/nft/marketplaces) ✋

<br>

---

<br>

# Login:

#### Login in Metamask : [metamask](https://metamask.io/)

#### Login in ThirdWeb : [Thirdweb](https://bit.ly/3EJLftx)

#### Login [Opensea](https://testnets.opensea.io/)

 <br>

> **yarn dev** to start server on 3000 and **sanity start** to start server sanity on 3333 🌵

## <br>

<br>
<br>
<!-- [<img src="./z_img-read/toaster-notification-in-action.gif"/>]() -->
# 🍨 🥭

<br>

# Collections

#### Now we need to get back to the collections, if you remember we already started it a bit [Here](https://github.com/nadiamariduena/opensea-marketplace/tree/4-header-tailwing-routing), so now we need to make it work:

- SO this is what we have in collections

```javascript
import React from 'react'
import { useRouter } from 'next/router'
import Link from 'next/link'

const collection = () => {
  const router = useRouter()
  //
  console.log(router.query)
  console.log(router.query.collectionId)
  return (
    <Link href="/">
      <h2>{router.query.collectionId}</h2>
    </Link>
  )
}

export default collection
```

<br>

### Start by adding the style

```javascript
const style = {
  bannerImageContainer: `h-[20vh] w-screen overflow-hidden flex justify-center items-center`,
  // h-20	height: 5rem; /* 80px */
  //w-screen	width: 100vw;
  //
  bannerImage: `w-full object-cover`,
  // w-full	width: 100%;  object-cover https://tailwindcss.com/docs/object-fit
  //
  infoContainer: `w-screen px-4`,
  // w-screen	width: 100vw;
  //
  //
  midRow: `w-full flex justify-center text-white`,
  endRow: `w-full flex justify-end text-white`,
  profileImg: `w-40 h-40 object-cover rounded-full border-2 border-[#202225] mt-[-4rem]`,
  //
  //
  socialIconsContainer: `flex text-3xl mb-[-2rem]`,
  //mb = margin-bottom https://shuffle.dev/tailwind/classes/margins/mb-auto
  //
  socialIconsWrapper: `w-44`,
  socialIconsContent: `flex container justify-between text-[1.4rem] border-2 rounded-lg px-2`,
  socialIcon: `my-2`,
  divider: `border-r-2`,
  title: `text-5xl font-bold mb-4`,
  createdBy: `text-lg mb-4`,
  statsContainer: `w-[44vw] flex justify-between py-4 border border-[#151b22] rounded-xl mb-4`,
  collectionStat: `w-1/4`,
  statValue: `text-3xl font-bold w-full flex items-center justify-center`,
  ethLogo: `h-6 mr-2`,
  statName: `text-lg w-full text-center mt-1`,
  description: `text-[#8a939b] text-xl w-max-1/4 flex-wrap mt-4`,
}
```

<br>
<br>

#### Now Add the following:

- Here we will need to add the **provider coming from the web3** , than we will need to add the **collectionId**

```javascript
import React from 'react'
import { useRouter } from 'next/router'
import Link from 'next/link'

//
import { useWeb3 } from '@3rdweb/hooks' ✋
import { client } from '../../lib/sanityClient'  ✋
//
/*



*/
const collection = () => {
  const router = useRouter()

  //
  const { provider } = useWeb3() ✋
  const { collectionId } = router.query ✋
  //
```

<br>

#### Set up an <u>states</u> for collections, nft's & listings coming from the collections we created in the [thirdweb](https://thirdweb.com/dashboard)

- the state is going to give us the possibility to have access to all I mentioned above

```javascript
const [collection, setCollection] = useState({})
const [nfts, setNfts] = useState([])
const [listings, setListings] = useState([])
```

<br>

- the state is going to get **access to all of the below**

<br>

[<img src="./z_img-read/states-to-get-access-thecollection.gif"/>]()
