# Baku

## Capability developer

`capabilities` repo depends on the platform (`chainlink`) repo. The platform defines and operates on the interfaces.

```bash
- capabilities
    - triggers
    - actions
    - consensuses
    - targets
        - write-evm-chain
            - module # Code that compiles to a LOOPP binary
                - contract-wrappers # Generated
                - docs # Generated from *_validation.go files
                    - node # Configuration options
                    - workflow # Inputs + outputs
                - mocks
                    # Configuration that starts the capability
                    # NOP-facing; generated
                    capability_spec.toml
                - src
                    capability_spec_validation.go
                    workflow_config_validation.go
                    execute_test.go
                    execute.go
                    metadata.go # For CapabilitiesRegistry
                go.mod
                go.sum
            - contracts
                - src
                    Forwarder.sol
                - tests
                    - mocks
                        Receiver.sol
                    BaseTest.t.sol
                    Configuration_beforeCapabilityConfigSet.t.sol
                    Forwarder_SetConfig.t.sol
                    Forwarder_Report.t.sol
                foundry.toml
            - operations
                - src
                    Forwarder-Deploy.command.ts
                    Forwarder-SetConfig.command.ts
                    Forwarder-GetTransmissionState.query.ts
                - tests
                package.json
                ...
            - integration-tests # Tests module, contracts & ops
            - alerts
        - write-aptos-chain
            - module
            - contracts
                - src
                    Forwarder.move
                move.toml
- libs
    - values
        values.go
    - types
        capabilities.go
```
