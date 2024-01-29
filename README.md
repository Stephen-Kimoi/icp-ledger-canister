# icp_ledger_canister

Command for deploying the canister locally: 
```
dfx deploy --specified-id ryjl3-tyaaa-aaaaa-aaaba-cai icp_ledger_canister --argument "
  (variant {
    Init = record {
      minting_account = \"$MINTER_ACCOUNT_ID\";
      initial_values = vec {
        record {
          \"$DEFAULT_ACCOUNT_ID\";
          record {
            e8s = 10_000_000_000 : nat64;
          };
        };
      };
      send_whitelist = vec {};
      transfer_fee = opt record {
        e8s = 10_000 : nat64;
      };
      token_symbol = opt \"JabaCoin\";
      token_name = opt \"JabaCoin\";
    }
  })
"
```

Full documentation over [here](https://internetcomputer.org/docs/current/tutorials/developer-journey/level-4/4.1-icp-ledger)