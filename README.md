# dbt_demo
name: 'ftaxi_rides_ny'
version: '1.0.0'
config-version: 2

profile: 'bronze-to-silver'

model-paths: ["models"]
analysis-paths: ["analysis"]
test-paths: ["tests"]
seed-paths: ["data"]
macro-paths: ["macros"]
snapshot-paths: ["snapshots"]

target-path: "target"
clean-targets: 
    - "target"
    - "dbt_packages"

models:
  taxi_rides_ny:
    staging:
      materalized: view
    core:
      materalized: table
vars:
  payment_type_values: [1, 2, 3, 4, 5, 6]
