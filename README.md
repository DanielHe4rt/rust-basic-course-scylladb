# Rust Course with ScyllaDB

Welcome to the 'How to Write Basic Apps Course' featuring the Rust programming language!

Start by running the following command to bring up the cluster:

```bash
docker-compose up -d
```

Ensure it's running by accessing the CQL shell and querying the authenticated users:

```bash
docker exec -it uni-scylla-1 cqlsh
```

```sql
SELECT username, driver_name from system.clients;
```

## Prerequisites

The ScyllaDB driver is built on top of the Tokio crate, so it will be a dependency. In this session, we’ll use three
primary crates:

- **Tokio** – Provides the async runtime for executing database queries.
- **Scylla** – The Rust driver for ScyllaDB and Cassandra.
- **Anyhow** – Simplifies error handling.

```toml
[dependencies]
tokio = { version = "1", features = ["full"] }
scylla = "0.14.0"
anyhow = "1.0"
```

After setting up your dependencies, convert the main function to be asynchronous using the Tokio macro.

```rust
#[tokio::main]
async fn main() -> anyhow::Result<()> {
    println!("Hello, world!");
    Ok(())
}
```

With the basis settled, take the course instructions and good luck!

