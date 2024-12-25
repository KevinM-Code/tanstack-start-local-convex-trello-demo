# Trello-like example using Convex DB

This is a TanStack Start demo using Convex as the database.
It is similar to the [start-trellaux](https://github.com/TanStack/router/tree/main/examples/react/start-trellaux) example but uses a cloud Convex deploymnet instead of an in-memory database.

To run this example:

Goto https://github.com/get-convex/convex-backend/releases/latest

* Download the zip file for your OS (e.g. convex-local-backend-x86_64-unknown-linux-gnu.zip for me)
* Unzip it
* Go into the directory and copy paste the binary file into the root directory of the project

```sh
curl https://sh.rustup.rs -sSf | sh
pnpm install
./convex-local-backend
cargo install just
just convex dev 
pnpm dev:web
```

# Convex

Convex is an open source Reactive backend made by [convex.dev](https://convex.dev/?utm_source=tanstack), a sponsor of TanStack Start.

This example uses Convex with TanStack Query and TanStack Start to provide

- Typesafe TanStack Query options factories like `convexQuery` for use with `useQuery`, `useSuspenseQuery` etc.
- Live-updating queries: updates come in over a WebSocket instead of requiring polling
- Automatic query invalidation: when a mutation succeeds all queries it affects update automatically
- Selective optimistic update rollback: when a mutation succeeds only its update will be rolled back, with other optimistic updates reapplied
- Consistent snapshot reads of database state: /messages will never return a foreign key for a /user that doesn't exist until the next fetch
