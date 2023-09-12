# Tide Payment Streaming DAPP

This project is a simple DAPP that allows users to stream payments to each other. It is built using [Soroban](https://soroban.stellar.org/), [Next.js](https://nextjs.org/) and [TypeScript](https://www.typescriptlang.org/).

## Installation

Use yarn to install dependecies.

```bash
yarn
```

### Backend
Follow the steps below to set up the backend. 

```bash
cd backend
```

#### Run the Stream Payment backend
-----------

Make sure to start from a clean setup:
```bash
yarn stream:clean
```

##### Deploy on Futurenet

0. Make sure you have soroban-cli installed, as explained above

1. Deploy the contracts and initialize them

       yarn stream:setup

   This runs `./initialize.sh futurenet` behind the scenes, which will create a `token-admin` identity for you (`soroban config identity create token-admin`) and deploy a Fungible Token contract as well as the [payment stream contract](./contracts/stream), with this account as admin.

2. Select the Futurenet network in your Freighter browser extension

#### Run the Name Service backend
-----------

Make sure to start from a clean setup:
```
yarn sns:clean
```

##### Deploy on Futurenet

0. Make sure you have soroban-cli installed, as explained above

1. Deploy the contracts and initialize them

       yarn sns:setup

   This runs `./initialize_sns.sh futurenet` behind the scenes, which will create a `token-admin` identity for you (`soroban config identity create token-admin`) and deploy the registry, registrar and resolver contrancts.

2. Select the Futurenet network in your Freighter browser extension

### Frontend
Follow the steps beloww to setup the frontend
```bash
cd frontend
```

#### Run the frontend
You need to have deployed the smart contracts first. See above for more details
```bash
yarn dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

## Base structure
The project contains backend and frontend workspaces, together with packages, that can be used to extract some logic there.
```bash
backend/
frontend/
packages/
     .../
     .../
```

## License
[MIT](https://choosealicense.com/licenses/mit/)
