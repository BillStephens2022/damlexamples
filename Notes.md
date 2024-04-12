# DAML Data Types

## Primitive Data Types
  -- Int
  -- Decimal
  -- Text
  -- Bool
  -- Date
  -- Time
  -- RelTime (differences between 2 time values)

## Contract Related Data Types
  -- Party - identity of an entity that may have rights and obligations relating to contracts on the ledger
      
      usage:  allocateParty : HasCallStack => Text -> Script Party
              alice <- allocationParty "Alice"

  -- ContractId a - Opaque data type; reference to a contract of template "a"

      usage:  create : t -> Update (ContractId t)
              exercise: ContractId t -> c -> Update r

  -- Update a - update or query the ledger, before returning a value of type a

      usage:  create, exercise, fetch

  -- Script a - defining test scripts

      usage:  script, submit, query

  -- Commands a - a set of commands that are submitted as a single transaction

      usage:  createCmd, exerciseCmd
              submit: Party -> cmds a -> m a