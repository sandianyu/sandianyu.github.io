### 添加控制者
dfx canister --network=xxx --wallet=$(dfx identity --network=xxx get-wallet) update-settings --add-controller xxx(principal) xxx (canister id or --all 表示全部canister)

### 删除控制者
dfx canister --network=xxx --wallet=$(dfx identity --network=xxx get-wallet) update-settings --remove-controller xxx(principal) xxx (canister id or --all 表示全部canister)

### 通过ledger创建容器部署wallet

dfx ledger --network=ic create-canister xxx(控制者) --amount xxx(icp 数量)


