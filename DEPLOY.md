# NFT Deployment Steps

## IPFS Uploader
1. Package bulk images using this command:
  - `npx ipfs-car --pack ./sample-assets/images --wrapWithDirectory false --output ./my_images.car`
2. Update `index.js` with hardcoded data
3. Run `node index.js`
4. Update metadata JSON with generated CID
5. Package bulk metadata using this command:
  - `npx ipfs-car --pack ./sample-assets/metadata --wrapWithDirectory false --output ./my_metadata.car`
  - Upload manually or repeat steps 2 and 3 if too large
6. Undo changes to `index.js` 
7. Delete API key from NFT.Storage account

## Smart Contract
1. Add `.env` file and update values
2. Use Node version 16 and run `yarn`
3. Run `yarn rename-contract LoremIpsum`
4. Update `CollectionConfig.ts`
  - tokenName: 'Lorem Ipsum'
  - tokenSymbol: 'IPSUM'
5. Update `whitelist.json` (at least 2)
6. In separate terminal:
  - Must use same node version as above
  - Run `npx truffle dashboard` then connect wallet
7. Run `yarn deploy --network truffle`
8. Update `CollectionConfig.ts` with contract address
9. Run `yarn verify {contract-address} --network truffle`
10. Run either of the following to open sales:
  - `yarn whitelist-open --network truffle`
  - `yarn presale-open --network truffle`
  - `yarn public-sale-open --network truffle`
11. Mint first token to fully activate contract
12. When ready to reveal, run `yarn reveal --network truffle`
13. To widthdraw funds, perform at Etherscan

## Minting Dapp
1. Use Node latest for and run `yarn`
2. Run `yarn dev-server` to test locally
3. Run `yarn build` and deploy `public` folder

## OpenSea
1. Create new collection and import contract
2. Edit the collection with image, description, and royalty fee
3. Create sales listing from each NFT

---

## NFT Details
- Contract: 0x
- Metadata: ipfs://
- Images: ipfs://