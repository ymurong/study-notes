




# Table of Content
## Why duckdb

## Storage Model
### DuckDB 
- use column-store
- Good for column aggregation

### Sqlite 
- use row-store
- all columns must be fetched 
- not optimized for analytical requirements

## Query Execution
### Sqlite
- Tuple-at-a-Time (process one row at a time)
  - optimize for low memory footprint
  - only need to keep single row in memory
- comes from a time when memory was expensive but high CPU overhead per tuple


### Numpy/R
- column-at-a time processing (process entire columns at once)
  - better CPU utilization, allows for SIMD (single instruction, multiple data)
  - materialize large intermediates in memory
- problematic when data size are large


### DuckDB
- vectorized processing (batch small)
- process batches of columns at a time
- optimized for CPU cache locality
- SIMD instructions - Pipeling (????)
- small intermediates (ideally fit in L1 cache)
