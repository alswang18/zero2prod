```bash
# Run a single test with error logging enabled.
export RUST_LOG="sqlx=error,info"
export TEST_LOG=true
cargo t subscribe_fails_if_there_is_a_fatal_database_error | bunyan
```

```bash
# Generate sqlx queries when running checks with no database available.
cargo sqlx prepare --workspace -- --all-targets
```

```bash
# Adding a new migration.
cargo sqlx migrate add <migration_name>
# Edit the generated file with your sql changes.
# Run the migration.
cargo sqlx migrate run
```

```bash
# Watch for changes while developing backend.
cargo watch -x check -x test -x run | bunyan
```