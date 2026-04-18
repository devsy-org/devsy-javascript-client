# devsy-javascript-client

## Setup

Add this repository as a dependency to your `package.json` file:
npm
`npm install https://github.com/devsy-org/devsy-javascript-client`

yarn
`yarn add https://github.com/devsy-org/devsy-javascript-client`

pnpm
`pnpm install https://github.com/devsy-org/devsy-javascript-client`

## Usage

The client can be imported `@devsy/client`.
It's a singleton instance that doesn't require further configuration and can be used like so:

```typescript
import { Client, Resources } from "@devsy/client"

// init client
const client = new Client("MY_ACCESS_KEY", "https://path-to-devsy")

// use client
const result = await client.management(Resources.ManagementV1VirtualClusterInstance).List()
if (result.err) {
  console.error(result)
} else {
  // print all virtual clusters
  console.info(result.val.items)
}
```

If you need to access the generated models outside of the client and `Resources`, you need to import them from the `gen` subfolder:

```typescript
import { ClusterV1VirtualCluster } from "@devsy/client/gen/models/ClusterV1VirtualCluster"
```
