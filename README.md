# FIRST ITERATION 

## Understanding Mina's Architectural Design and zkApp-chain framework-Protokit

# Mina is a layer-1 blockchain with a 22KB blockchain & zero knowledge smart contracts (“zkApps”) written in TypeScript.

### Mina uses infinitely recursive zero knowledge proofs to create a 22KB blockchain for proving anything and enabling privacy-first applications.


# What is a zero knowledge proof?

### A cryptographic technique that allows one party to prove the truth of a statement to another party without revealing any specific details about the statement.


# What are the key features and benefits of using Protokit for building zk-rollups? 

## Protokit is a developer toolkit that helps simplify the process of building zk-rollup solutions. Here are some of the key features and benefits of using Protokit:

### Abstraction layers: Protokit provides high-level abstraction layers that handle the complex technical details of zk-rollups, allowing developers to focus on building their application logic rather than dealing with the underlying complexities.

### Modular design: The toolkit has a modular design, which means developers can pick and choose the components they need, making it flexible and customizable to their specific requirements.

### Developer tooling: The toolkit includes a range of developer tools, such as libraries, debugging utilities, and deployment scripts, which streamline the development and deployment process.

### Security: Protokit leverages the inherent security benefits of zk-rollups, which use cryptographic proofs to ensure the validity of transactions without revealing sensitive information.

### 6. Scalability: By leveraging zk-rollup technology, Protokit-based solutions can achieve significantly higher transaction throughput and lower gas costs compared to base-layer blockchain transactions.

# How does Protokit's hybrid execution model, combining on-chain and off-chain logic, help address the precondition problem in traditional smart contracts? 

## 1. Separation of Concerns:
    * By separating the on-chain and off-chain components, Protokit allows for a more modular and manageable approach to smart contract development.
    * The on-chain component can focus on the core blockchain-based logic, while the off-chain component can handle the more complex or dynamic preconditions.

## 2. Dynamic Precondition Evaluation:
    * The off-chain component of Protokit's hybrid model can evaluate complex or dynamic preconditions that may be difficult or impractical to implement entirely on-chain.
    * This allows for more flexible and adaptable precondition checks, which can be updated or modified without the need to redeploy the entire smart contract.

## 3. Reduced On-chain Complexity:
    * By offloading some of the precondition logic to the off-chain component, Protokit can help reduce the overall complexity of the on-chain smart contract.
    * This can lead to smaller and more efficient on-chain code, which can be easier to audit, maintain, and deploy.

## 4. Improved Gas Efficiency:
    * The off-chain component of Protokit's hybrid model can perform precondition checks without incurring the high gas costs associated with on-chain computation.
    * This can result in more gas-efficient smart contract interactions, as the on-chain component only needs to execute the core logic once the preconditions have been verified off-chain.


# The main components of a Protokit application chain are:

## 1. Front-end Application: This is the user-facing part of the application that provides the interface and interacts with the user. It can be built using various web frameworks like React, Vue.js, or Angular.

## 2. Protokit SDK: The Protokit SDK is a set of libraries and tools that enable the front-end application to interact with the Protokit network. It provides APIs for tasks such as wallet management, transaction signing, and data fetching.

## 3. Protokit Node: The Protokit node is the backend component that serves as the gateway to the Protokit network. It handles tasks such as transaction validation, block production, and data storage.

## 4. Protokit Network: The Protokit network is the underlying blockchain infrastructure that powers the entire application chain. It provides the decentralized and secure foundation for the application.


# Here's how these components work together to provide a seamless user experience:

## 1. Front-end Application: The front-end application presents the user interface and handles user interactions. It utilizes the Protokit SDK to interact with the Protokit network.

## 2. Protokit SDK: The Protokit SDK acts as the bridge between the front-end application and the Protokit network. It provides easy-to-use APIs that allow the front-end to perform tasks such as wallet management, transaction signing, and data fetching.

## 3. Protokit Node: The Protokit node serves as the gateway to the Protokit network. It receives requests from the front-end application (via the Protokit SDK) and interacts with the underlying blockchain to fulfill those requests. This includes tasks like transaction validation, block production, and data storage.

## 4. Protokit Network: The Protokit network is the decentralized infrastructure that underpins the entire application chain. It provides the necessary blockchain-based services, such as consensus, security, and data storage, to support the Protokit node and the overall application.

# Protokit starter-kit

This repository is a monorepo aimed at kickstarting application chain development using the Protokit framework.

## Quick start

The monorepo contains 1 package and 1 app:

- `packages/chain` contains everything related to your app-chain
- `apps/web` contains a demo UI that connects to your locally hosted app-chain sequencer

**Prerequisites:**

- Node.js v18
- pnpm
- nvm

> If you're on windows, please use Docker until we find a more suitable solution to running the `@proto-kit/cli`. 
> Run the following command and then proceed to "Running the sequencer & UI":
>
> `docker run -it --rm -p 3000:3000 -p 8080:8080 -v %cd%:/starter-kit -w /starter-kit gplane/pnpm:node18 bash`


### Setup

```zsh
git clone https://github.com/proto-kit/starter-kit my-chain
cd my-chain

# ensures you have the right node.js version
nvm use
pnpm install
```

### Running the sequencer & UI

```zsh
# starts both UI and sequencer locally
pnpm dev

# starts UI only
pnpm dev -- --filter web
# starts sequencer only
pnpm dev -- --filter chain
```

### Running tests
```zsh
# run and watch tests for the `chain` package
pnpm run test --filter=chain -- --watchAll
```

Navigate to `localhost:3000` to see the example UI, or to `localhost:8080/graphql` to see the GQL interface of the locally running sequencer.
