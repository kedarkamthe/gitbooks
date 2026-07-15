# How Mongodb achieves durability using Journaling

MongoDB achieves durability using journaling through the following step-by-step process:

1. **Write to In-Memory Operation Log (Oplog):**
   * When MongoDB receives a write operation, it first records the operation in the in-memory operation log (oplog).
   * This in-memory log is designed for high-speed write operations and serves as a write-ahead log.
2. **Write to Journal:**
   * Simultaneously, the write operation is also logged to the journal (or write-ahead log on disk).
   * The journal is a circular buffer where write operations are sequentially recorded.
3. **Update Data Files:**
   * Once the write operation is successfully logged to the journal, MongoDB updates the corresponding data files on disk.
   * The actual data modifications are applied to the data files.
4. **Checkpoint:**
   * Periodically, MongoDB performs a checkpoint operation to ensure that all in-memory changes are flushed to disk.
   * This checkpoint ensures that the on-disk data files are consistent and up-to-date.
5. **Recovery:**
   * In the event of a server crash or unexpected shutdown, MongoDB can use the journal to recover data and ensure durability.
   * During the restart, MongoDB examines the journal to identify any operations that were not yet applied to the data files at the time of the crash.
   * Unapplied operations from the journal are then replayed to bring the data back to a consistent state.
6. **Journal Commit Interval:**
   * MongoDB allows configuring the journal commit interval, which determines how frequently the changes in the journal are flushed to disk.
   * Shorter intervals improve durability but may impact performance.

By employing this journaling mechanism, MongoDB ensures durability by persistently logging write operations before applying them to the actual data files. In the event of a failure, the journal is used to recover the database to a consistent state, providing a robust and reliable storage mechanism.
