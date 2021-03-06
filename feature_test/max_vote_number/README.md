
## 启动节点  
**单节点本地测试**，使用当前目录下的配置, 启动链和节点，参考README.md
### 链和钱包初始化
``` shell
python3 main.py init

python3 main.py wallet init

```

### 节点和钱包重启操作
``` shell
python3 main.py 

python3 main.py wallet
```


## 测试

### 接口测试
#### cli_wallet api
``` shell
curl http://127.0.0.1:8048 -d '{"id":1, "method":"get_global_extensions_properties", "params":[]}' && echo ""
```

#### chain api
``` shell
curl http://127.0.0.1:8059 -d '{"id":1, "method":"call", "params":[0, "get_global_property_extensions", []]}' && echo ""
```

### 发起修改参数提案, 批准  
``` shell
python3 vote.py

```

**注意** : 提案review时间应该大于当前时间到链维护的间隔，否则提案失败，这种情况执行会有提示，`Please wait for the next maintenance`, 可以根据需要修改vote.py逻辑，`sleep(delta_time)`

**执行结果**: 
``` text
dev@ubuntu:~/test/python3 vote.py 

``` json
>> get_dynamic_global_properties []
{'jsonrpc': '2.0', 'result': {'witness_budget': 2790000000, 'time': '2020-05-26T07:30:52', 'dynamic_flags': 0, 'accounts_registered_this_interval': 0, 'current_aslot': 18497042, 'id': '2.1.0', 'current_witness': '1.6.2', 'head_block_id': '00004bd777daf10e8a83bb476ec31dd9bd0b7c44', 'head_block_number': 19415, 'last_irreversible_block_num': 19408, 'next_maintenance_time': '2020-05-26T07:40:00', 'last_budget_time': '2020-05-26T07:30:00', 'recently_missed_count': 575693, 'current_transaction_count': 0, 'recent_slots_filled': '340261577449851944168328090111577157119'}, 'id': 1}

next_maintenance_time: 2020-05-26T07:40:00, now time: 2020-05-26T07:30:52
time_delta: 548
>> get_global_properties []
{'jsonrpc': '2.0', 'result': {'parameters': {'crontab_suspend_threshold': 3, 'maximum_proposal_lifetime': 2419200, 'max_authority_depth': 2, 'maximum_block_size': 2000000, 'maintenance_interval': 600, 'block_interval': 2, 'committee_candidate_freeze': '5000000000000', 'maximum_asset_feed_publishers': 10, 'accounts_per_fee_scale': 1000, 'maximum_authority_membership': 10, 'assigned_task_life_cycle': 300, 'witness_number_of_election': 11, 'crontab_suspend_expiration': 2592000, 'current_fees': {'parameters': [[0, {'price_per_kbyte': 1000000, 'fee': 2000000}], [1, {'fee': 500000}], [2, {'fee': 0}], [3, {'fee': 2000000}], [4, {}], [5, {'price_per_kbyte': 100000, 'basic_fee': 500000, 'premium_fee': 200000000}], [6, {'price_per_kbyte': 100000, 'fee': 2000000}], [7, {'membership_lifetime_fee': 1000000000, 'membership_annual_fee': 200000000}], [8, {'price_per_kbyte': 10, 'long_symbol': 500000000, 'symbol3': '50000000000', 'symbol4': '30000000000'}], [9, {'price_per_kbyte': 10, 'fee': 50000000}], [10, {'price_per_kbyte': 100000, 'fee': 2000000}], [11, {'fee': 50000000}], [12, {'fee': 50000000}], [13, {'price_per_kbyte': 100000, 'fee': 2000000}], [14, {'fee': 2000000}], [15, {'fee': 10000000}], [16, {'fee': 50000000}], [17, {'fee': 100000}], [18, {'fee': 500000000}], [19, {'fee': 2000000}], [20, {'price_per_kbyte': 10, 'fee': 2000000}], [21, {'price_per_kbyte': 10, 'fee': 2000000}], [22, {'fee': 100000}], [23, {'fee': 500000000}], [24, {'fee': 2000000}], [25, {'fee': 100000}], [26, {'fee': 100000}], [27, {'fee': 2000000}], [28, {'fee': 100000}], [29, {}], [30, {}], [31, {'fee': 2000000}], [32, {'fee': 2000000}], [33, {}], [34, {'price_per_kbyte': 1000000, 'fee': 2000000}], [35, {'price_per_millisecond': 1000000, 'price_per_kbyte': 1000000, 'fee': 2000000}], [36, {'price_per_kbyte': 1000000, 'fee': 2000000}], [37, {'fee': 100000}], [38, {'fee': 100000}], [39, {'fee': 100000}], [40, {'fee': 100000}], [41, {'fee': 100000}], [42, {'fee': 100000}], [43, {'fee': 100000}], [44, {'fee': 0}], [45, {'fee': 0}], [46, {'price_per_kbyte': 1000000, 'fee': 100000}], [47, {'price_per_related_account': 100000}], [48, {'price_per_kbyte': 1000000, 'fee': 100000}], [49, {'fee': 100000}], [50, {'price_per_kbyte': 1000000, 'fee': 2000000}], [51, {'price_per_kbyte': 10, 'fee': 2000000}], [52, {'fee': 2000000}], [53, {'fee': 2000000}], [54, {'fee': 100000}], [55, {'fee': 50000000}], [56, {'fee': 100000}], [57, {'fee': 100000}]], 'scale': 10000, 'maximun_handling_fee': 10000000}, 'committee_number_of_election': 11, 'account_fee_scale_bitshifts': 4, 'unsuccessful_candidates_percent': 5000, 'worker_budget_per_day': '50000000000', 'maximum_nh_asset_order_expiration': 1209600, 'witness_candidate_freeze': '5000000000000', 'cashback_vb_period_seconds': 86400, 'maintenance_skip_slots': 3, 'witness_pay_per_block': 10000000, 'extensions': [], 'maximum_time_until_expiration': 86400, 'maximum_run_time_ratio': 7500, 'candidate_award_budget': '20000000000', 'cashback_gas_period_seconds': 86400, 'witness_pay_vesting_seconds': 86400, 'cashback_vote_period_seconds': 259200, 'committee_proposal_review_period': 120, 'committee_percent_of_candidate_award': 5500}, 'next_available_vote_id': 22, 'active_committee_members': ['1.5.0', '1.5.1', '1.5.2', '1.5.3', '1.5.4', '1.5.5', '1.5.6', '1.5.7', '1.5.8', '1.5.9', '1.5.10'], 'active_witnesses': ['1.6.1', '1.6.2', '1.6.3', '1.6.4', '1.6.5', '1.6.6', '1.6.7', '1.6.8', '1.6.9', '1.6.10', '1.6.11'], 'id': '2.0.0'}, 'id': 1}

committee_proposal_review_period: 120
expire_time: 2020-05-26T07:35:00
>> propose_extensions_parameter_change ['init0', '2020-05-26T07:35:00', {'committee_max_votes': 9, 'witness_max_votes': 7}, True]
{'jsonrpc': '2.0', 'result': ['402bc6c68d6597e7b2e212c01acf7d3ebacaaf41500233a279eb45e64e1ee55f', {'expiration': '2020-05-26T07:51:22', 'signatures': ['2009ea1294be5b8d46d34340c0e14316978e5a40d71a7e265bb1c33889fa69f86b2bbb6d26d95c10aa076f2c3dccaaa04d658d6c4e76b3d1840dd8aac1d36fc74f'], 'ref_block_prefix': 1895730904, 'operations': [[20, {'extensions': [], 'proposed_ops': [{'op': [57, {'committee_max_votes': 9, 'contract_private_data_size': 3072, 'contract_total_data_size': 10485760, 'contract_max_data_size': 2147483648, 'witness_max_votes': 7}]}], 'expiration_time': '2020-05-26T07:35:00', 'fee_paying_account': '1.2.5', 'review_period_seconds': 120}]], 'ref_block_num': 19407, 'extensions': []}], 'id': 1}

tx_id: 402bc6c68d6597e7b2e212c01acf7d3ebacaaf41500233a279eb45e64e1ee55f
>> get_transaction_in_block_info ['402bc6c68d6597e7b2e212c01acf7d3ebacaaf41500233a279eb45e64e1ee55f']
{'jsonrpc': '2.0', 'result': {'block_num': 19416, 'trx_in_block': 0, 'trx_hash': '402bc6c68d6597e7b2e212c01acf7d3ebacaaf41500233a279eb45e64e1ee55f', 'id': '3.1.115'}, 'id': 1}

>> get_transaction_in_block_info 402bc6c68d6597e7b2e212c01acf7d3ebacaaf41500233a279eb45e64e1ee55f
 {'block_num': 19416, 'trx_in_block': 0, 'trx_hash': '402bc6c68d6597e7b2e212c01acf7d3ebacaaf41500233a279eb45e64e1ee55f', 'id': '3.1.115'}

>> get_block [19416]
{'jsonrpc': '2.0', 'result': {'previous': '00004bd777daf10e8a83bb476ec31dd9bd0b7c44', 'transaction_merkle_root': '140b770627fbc7c6bd40e31c3d9967ec03373588', 'timestamp': '2020-05-26T07:30:54', 'block_id': '00004bd8a9764e2c922742f429d72b1228dcd6fd', 'witness_signature': '20740bc15630dc219ac2a63bbd21668c36cc1093714711783b72915ae1a06315dd4eac782c33125cf4fbcab9e2783ac5c3a3539c566d5efaef22e326ed44fd9473', 'witness': '1.6.5', 'transactions': [['402bc6c68d6597e7b2e212c01acf7d3ebacaaf41500233a279eb45e64e1ee55f', {'expiration': '2020-05-26T07:51:22', 'signatures': ['2009ea1294be5b8d46d34340c0e14316978e5a40d71a7e265bb1c33889fa69f86b2bbb6d26d95c10aa076f2c3dccaaa04d658d6c4e76b3d1840dd8aac1d36fc74f'], 'ref_block_prefix': 1895730904, 'operation_results': [[2, {'fees': [{'amount': 2000000, 'asset_id': '1.3.0'}], 'real_running_time': 178, 'result': '1.10.10'}]], 'operations': [[20, {'extensions': [], 'proposed_ops': [{'op': [57, {'committee_max_votes': 9, 'contract_private_data_size': 3072, 'contract_total_data_size': 10485760, 'contract_max_data_size': 2147483648, 'witness_max_votes': 7}]}], 'expiration_time': '2020-05-26T07:35:00', 'fee_paying_account': '1.2.5', 'review_period_seconds': 120}]], 'ref_block_num': 19407, 'extensions': []}]]}, 'id': 1}

block: {'previous': '00004bd777daf10e8a83bb476ec31dd9bd0b7c44', 'transaction_merkle_root': '140b770627fbc7c6bd40e31c3d9967ec03373588', 'timestamp': '2020-05-26T07:30:54', 'block_id': '00004bd8a9764e2c922742f429d72b1228dcd6fd', 'witness_signature': '20740bc15630dc219ac2a63bbd21668c36cc1093714711783b72915ae1a06315dd4eac782c33125cf4fbcab9e2783ac5c3a3539c566d5efaef22e326ed44fd9473', 'witness': '1.6.5', 'transactions': [['402bc6c68d6597e7b2e212c01acf7d3ebacaaf41500233a279eb45e64e1ee55f', {'expiration': '2020-05-26T07:51:22', 'signatures': ['2009ea1294be5b8d46d34340c0e14316978e5a40d71a7e265bb1c33889fa69f86b2bbb6d26d95c10aa076f2c3dccaaa04d658d6c4e76b3d1840dd8aac1d36fc74f'], 'ref_block_prefix': 1895730904, 'operation_results': [[2, {'fees': [{'amount': 2000000, 'asset_id': '1.3.0'}], 'real_running_time': 178, 'result': '1.10.10'}]], 'operations': [[20, {'extensions': [], 'proposed_ops': [{'op': [57, {'committee_max_votes': 9, 'contract_private_data_size': 3072, 'contract_total_data_size': 10485760, 'contract_max_data_size': 2147483648, 'witness_max_votes': 7}]}], 'expiration_time': '2020-05-26T07:35:00', 'fee_paying_account': '1.2.5', 'review_period_seconds': 120}]], 'ref_block_num': 19407, 'extensions': []}]]}

tx_pair: ['402bc6c68d6597e7b2e212c01acf7d3ebacaaf41500233a279eb45e64e1ee55f', {'expiration': '2020-05-26T07:51:22', 'signatures': ['2009ea1294be5b8d46d34340c0e14316978e5a40d71a7e265bb1c33889fa69f86b2bbb6d26d95c10aa076f2c3dccaaa04d658d6c4e76b3d1840dd8aac1d36fc74f'], 'ref_block_prefix': 1895730904, 'operation_results': [[2, {'fees': [{'amount': 2000000, 'asset_id': '1.3.0'}], 'real_running_time': 178, 'result': '1.10.10'}]], 'operations': [[20, {'extensions': [], 'proposed_ops': [{'op': [57, {'committee_max_votes': 9, 'contract_private_data_size': 3072, 'contract_total_data_size': 10485760, 'contract_max_data_size': 2147483648, 'witness_max_votes': 7}]}], 'expiration_time': '2020-05-26T07:35:00', 'fee_paying_account': '1.2.5', 'review_period_seconds': 120}]], 'ref_block_num': 19407, 'extensions': []}]
[0]: 402bc6c68d6597e7b2e212c01acf7d3ebacaaf41500233a279eb45e64e1ee55f

tx: {'expiration': '2020-05-26T07:51:22', 'signatures': ['2009ea1294be5b8d46d34340c0e14316978e5a40d71a7e265bb1c33889fa69f86b2bbb6d26d95c10aa076f2c3dccaaa04d658d6c4e76b3d1840dd8aac1d36fc74f'], 'ref_block_prefix': 1895730904, 'operation_results': [[2, {'fees': [{'amount': 2000000, 'asset_id': '1.3.0'}], 'real_running_time': 178, 'result': '1.10.10'}]], 'operations': [[20, {'extensions': [], 'proposed_ops': [{'op': [57, {'committee_max_votes': 9, 'contract_private_data_size': 3072, 'contract_total_data_size': 10485760, 'contract_max_data_size': 2147483648, 'witness_max_votes': 7}]}], 'expiration_time': '2020-05-26T07:35:00', 'fee_paying_account': '1.2.5', 'review_period_seconds': 120}]], 'ref_block_num': 19407, 'extensions': []}

operation_results: [[2, {'fees': [{'amount': 2000000, 'asset_id': '1.3.0'}], 'real_running_time': 178, 'result': '1.10.10'}]]
propose_id: 1.10.10
>> get_object ['1.10.10']
{'jsonrpc': '2.0', 'result': [{'review_period_time': '2020-05-26T07:33:00', 'proposed_transaction': {'operations': [[57, {'committee_max_votes': 9, 'contract_private_data_size': 3072, 'contract_total_data_size': 10485760, 'contract_max_data_size': 2147483648, 'witness_max_votes': 7}]], 'expiration': '2020-05-26T07:35:00', 'ref_block_num': 0, 'ref_block_prefix': 0, 'extensions': ['1.10.10']}, 'allow_execution': False, 'available_active_approvals': [], 'available_owner_approvals': [], 'id': '1.10.10', 'available_key_approvals': [], 'required_owner_approvals': [], 'expiration_time': '2020-05-26T07:35:00', 'trx_hash': '402bc6c68d6597e7b2e212c01acf7d3ebacaaf41500233a279eb45e64e1ee55f', 'required_active_approvals': ['1.2.0']}], 'id': 1}

>> get_object 1.10.10
 [{'review_period_time': '2020-05-26T07:33:00', 'proposed_transaction': {'operations': [[57, {'committee_max_votes': 9, 'contract_private_data_size': 3072, 'contract_total_data_size': 10485760, 'contract_max_data_size': 2147483648, 'witness_max_votes': 7}]], 'expiration': '2020-05-26T07:35:00', 'ref_block_num': 0, 'ref_block_prefix': 0, 'extensions': ['1.10.10']}, 'allow_execution': False, 'available_active_approvals': [], 'available_owner_approvals': [], 'id': '1.10.10', 'available_key_approvals': [], 'required_owner_approvals': [], 'expiration_time': '2020-05-26T07:35:00', 'trx_hash': '402bc6c68d6597e7b2e212c01acf7d3ebacaaf41500233a279eb45e64e1ee55f', 'required_active_approvals': ['1.2.0']}]

propose object: [{'review_period_time': '2020-05-26T07:33:00', 'proposed_transaction': {'operations': [[57, {'committee_max_votes': 9, 'contract_private_data_size': 3072, 'contract_total_data_size': 10485760, 'contract_max_data_size': 2147483648, 'witness_max_votes': 7}]], 'expiration': '2020-05-26T07:35:00', 'ref_block_num': 0, 'ref_block_prefix': 0, 'extensions': ['1.10.10']}, 'allow_execution': False, 'available_active_approvals': [], 'available_owner_approvals': [], 'id': '1.10.10', 'available_key_approvals': [], 'required_owner_approvals': [], 'expiration_time': '2020-05-26T07:35:00', 'trx_hash': '402bc6c68d6597e7b2e212c01acf7d3ebacaaf41500233a279eb45e64e1ee55f', 'required_active_approvals': ['1.2.0']}]
>> transfer ['init0', 'committee-account', 3, 'COCOS', ['', False], True]
{'jsonrpc': '2.0', 'result': ['62dcee48dcaca61ff9096baf1421d0f1ffd8a0c9e89290300933f7557e18c5d4', {'expiration': '2020-05-26T07:51:24', 'signatures': ['1f3b80b3ba122392148ab98afc60ecc5359844c48ba5f81c598e87814f5880dc3f01cc39fb080abd9df3d02320ae7807bfb2eb79e7ce856c32a4d5fdcd6f47b48c'], 'ref_block_prefix': 1848520574, 'operations': [[0, {'to': '1.2.0', 'extensions': [], 'amount': {'amount': 300000, 'asset_id': '1.3.0'}, 'from': '1.2.5'}]], 'ref_block_num': 19408, 'extensions': []}], 'id': 1}

>> approve_proposal ['init0', '1.10.10', {'active_approvals_to_add': ['init0']}, True]
 ['cd9a1e5e67e2a30fda95aa671f5410d166bf94a5a928566a3afd84bc847e8c15', {'expiration': '2020-05-26T07:51:24', 'signatures': ['2027f9bbb7e30f03fbc838c052a78f20afe606705d5bf16140a2ae4f1816daafbd493e5efac85f7c24567dbdd53ac4697c2ec3fe00ed0bb0ca94306b1830be9dab'], 'ref_block_prefix': 1848520574, 'operations': [[21, {'owner_approvals_to_add': [], 'owner_approvals_to_remove': [], 'active_approvals_to_add': ['1.2.5'], 'fee_paying_account': '1.2.5', 'proposal': '1.10.10', 'key_approvals_to_add': [], 'active_approvals_to_remove': [], 'key_approvals_to_remove': [], 'extensions': []}]], 'ref_block_num': 19408, 'extensions': []}]

>> approve_proposal ['init1', '1.10.10', {'active_approvals_to_add': ['init1']}, True]
 ['1af97b94c49412cff436ba107aafc95cbb2f819d0361bcaef2160c7ce1519a97', {'expiration': '2020-05-26T07:51:24', 'signatures': ['1f5766bf1b8eb5cc1dd7350b5847637667d105d439ccdf17497ac7c0bf928f03fa6f4735b168a37c8bac0f42f93553baf7f1ffba8fe66a83b7c5e12a099c94af31'], 'ref_block_prefix': 1848520574, 'operations': [[21, {'owner_approvals_to_add': [], 'owner_approvals_to_remove': [], 'active_approvals_to_add': ['1.2.6'], 'fee_paying_account': '1.2.6', 'proposal': '1.10.10', 'key_approvals_to_add': [], 'active_approvals_to_remove': [], 'key_approvals_to_remove': [], 'extensions': []}]], 'ref_block_num': 19408, 'extensions': []}]

>> approve_proposal ['init2', '1.10.10', {'active_approvals_to_add': ['init2']}, True]
 ['7871395fa4a47cbc904e784aa3b0a48c9d24c74c3d3b4b17b30769f45a10d8b4', {'expiration': '2020-05-26T07:51:24', 'signatures': ['1f5c3c5c4fb033f8eb0186f7d23692df6caed3a352256a73e11ae6f910fa7e9f255376f380468007c397b2e383ec06c64c3ebf7a147c3874859e8bb555238e2e91'], 'ref_block_prefix': 1848520574, 'operations': [[21, {'owner_approvals_to_add': [], 'owner_approvals_to_remove': [], 'active_approvals_to_add': ['1.2.7'], 'fee_paying_account': '1.2.7', 'proposal': '1.10.10', 'key_approvals_to_add': [], 'active_approvals_to_remove': [], 'key_approvals_to_remove': [], 'extensions': []}]], 'ref_block_num': 19408, 'extensions': []}]

>> approve_proposal ['init3', '1.10.10', {'active_approvals_to_add': ['init3']}, True]
 ['722dc6e1e8da23a86ab11dd244b1442639e0af7883621fe2fcc580a8d8b91376', {'expiration': '2020-05-26T07:51:24', 'signatures': ['202687c9b597a4787202d5f4c03c9b34ba9cfb1c60c19cbd5eef323932f4c6cd0c345f82c4db160e0ed0dff24790495c550009a76225784ead4d84859c9a5dd7d1'], 'ref_block_prefix': 1848520574, 'operations': [[21, {'owner_approvals_to_add': [], 'owner_approvals_to_remove': [], 'active_approvals_to_add': ['1.2.8'], 'fee_paying_account': '1.2.8', 'proposal': '1.10.10', 'key_approvals_to_add': [], 'active_approvals_to_remove': [], 'key_approvals_to_remove': [], 'extensions': []}]], 'ref_block_num': 19408, 'extensions': []}]

>> approve_proposal ['init4', '1.10.10', {'active_approvals_to_add': ['init4']}, True]
 ['526b03bb50567976fc6e51abf85e1f8203c2248a299db30ac790a97c81983ecd', {'expiration': '2020-05-26T07:51:24', 'signatures': ['1f749ae1a396edf74b333f11618f3549d539826f1f28ba599718824906e27fb8687f14377baf69458c87e5df9b3fd6a63ede156cab9894d6ec0d55e8d67b548bb0'], 'ref_block_prefix': 1848520574, 'operations': [[21, {'owner_approvals_to_add': [], 'owner_approvals_to_remove': [], 'active_approvals_to_add': ['1.2.9'], 'fee_paying_account': '1.2.9', 'proposal': '1.10.10', 'key_approvals_to_add': [], 'active_approvals_to_remove': [], 'key_approvals_to_remove': [], 'extensions': []}]], 'ref_block_num': 19408, 'extensions': []}]

>> approve_proposal ['init5', '1.10.10', {'active_approvals_to_add': ['init5']}, True]
 ['feff9c19101ca1c2762dab495c6ca76ebfffc988cadebd7cccdd464f366460e9', {'expiration': '2020-05-26T07:51:24', 'signatures': ['2042ae323ed94b27fb8c22776eeac567c6f3aeaf4cc9a8fb5083cbbba2d0d62ff2282ae4c2bf374d68781a53cbc3ecf68fc6956b84863f24a74fcc3a48952fce92'], 'ref_block_prefix': 1848520574, 'operations': [[21, {'owner_approvals_to_add': [], 'owner_approvals_to_remove': [], 'active_approvals_to_add': ['1.2.10'], 'fee_paying_account': '1.2.10', 'proposal': '1.10.10', 'key_approvals_to_add': [], 'active_approvals_to_remove': [], 'key_approvals_to_remove': [], 'extensions': []}]], 'ref_block_num': 19408, 'extensions': []}]

>> approve_proposal ['init6', '1.10.10', {'active_approvals_to_add': ['init6']}, True]
 ['f3769fd1d5a95d490da835f2fc42ae6f4f88f4fe294a5dd7ee904139da5a7b2f', {'expiration': '2020-05-26T07:51:24', 'signatures': ['200dc60273dede80ebcec40d4f89e6d5fa296c6a41df50563198b57838d6d3a7fb763cbbf70d733999e7d8d97261fb136e77adea9b25c747d7194a51055c11cf87'], 'ref_block_prefix': 1848520574, 'operations': [[21, {'owner_approvals_to_add': [], 'owner_approvals_to_remove': [], 'active_approvals_to_add': ['1.2.11'], 'fee_paying_account': '1.2.11', 'proposal': '1.10.10', 'key_approvals_to_add': [], 'active_approvals_to_remove': [], 'key_approvals_to_remove': [], 'extensions': []}]], 'ref_block_num': 19408, 'extensions': []}]

>> approve_proposal ['init7', '1.10.10', {'active_approvals_to_add': ['init7']}, True]
 ['f52ae599fda2ebaec442f98d61c9f8226928f311b273deb6ed07fb589dd36470', {'expiration': '2020-05-26T07:51:24', 'signatures': ['205aa2080958e7437ffe8ea0c1cd6aab39f635d8672e1ce01d14f28eaab7c4412c712ec1b60d3d8197d47ceb54627645174ab4e11098d7259b50b2818de2cf313c'], 'ref_block_prefix': 1848520574, 'operations': [[21, {'owner_approvals_to_add': [], 'owner_approvals_to_remove': [], 'active_approvals_to_add': ['1.2.12'], 'fee_paying_account': '1.2.12', 'proposal': '1.10.10', 'key_approvals_to_add': [], 'active_approvals_to_remove': [], 'key_approvals_to_remove': [], 'extensions': []}]], 'ref_block_num': 19408, 'extensions': []}]

>> approve_proposal ['init8', '1.10.10', {'active_approvals_to_add': ['init8']}, True]
 ['be9c49e70455fb05d73a4eeda9d0ef44ac833bb9502d483bc182eb0f5c7d5663', {'expiration': '2020-05-26T07:51:24', 'signatures': ['204b0c33689df25aed4362ab9a584398ccd14f818ae0aac4e8b73a4c8fa4a78f616fedededd674650c2cd85498ee1bb448c57c857f5ff9c3a5f46447d62486db65'], 'ref_block_prefix': 1848520574, 'operations': [[21, {'owner_approvals_to_add': [], 'owner_approvals_to_remove': [], 'active_approvals_to_add': ['1.2.13'], 'fee_paying_account': '1.2.13', 'proposal': '1.10.10', 'key_approvals_to_add': [], 'active_approvals_to_remove': [], 'key_approvals_to_remove': [], 'extensions': []}]], 'ref_block_num': 19408, 'extensions': []}]

>> approve_proposal ['init9', '1.10.10', {'active_approvals_to_add': ['init9']}, True]
 ['3ef53ab9c9f7c5792a54bb5a3f4ce3ebb1613bc4c3e7bb3ad17752a91fd0cb6c', {'expiration': '2020-05-26T07:51:24', 'signatures': ['2055832a817d75bafcd079b404feb07b2d9f0e7537324b49f1e7855cfe5dee32651f2a9adee965ef2edb4a8dc316ef1d997655ab72cd765509430d1a1ebc8cee83'], 'ref_block_prefix': 1848520574, 'operations': [[21, {'owner_approvals_to_add': [], 'owner_approvals_to_remove': [], 'active_approvals_to_add': ['1.2.14'], 'fee_paying_account': '1.2.14', 'proposal': '1.10.10', 'key_approvals_to_add': [], 'active_approvals_to_remove': [], 'key_approvals_to_remove': [], 'extensions': []}]], 'ref_block_num': 19408, 'extensions': []}]

>> approve_proposal ['init10', '1.10.10', {'active_approvals_to_add': ['init10']}, True]
 ['2cafa65661531b0378c43d256c696e8e10e703e27feef1fb46ff588c22e38f48', {'expiration': '2020-05-26T07:51:24', 'signatures': ['2040c7e2e0d05b98e97a18a4858507f931c29facf0d07a1c3254f6387c4c64aa7c5bf90f7f88c5fb8fbec036c2ed1d222b82e22233ce4a28518c1310a33b690cd5'], 'ref_block_prefix': 1848520574, 'operations': [[21, {'owner_approvals_to_add': [], 'owner_approvals_to_remove': [], 'active_approvals_to_add': ['1.2.15'], 'fee_paying_account': '1.2.15', 'proposal': '1.10.10', 'key_approvals_to_add': [], 'active_approvals_to_remove': [], 'key_approvals_to_remove': [], 'extensions': []}]], 'ref_block_num': 19408, 'extensions': []}]

>> get_object ['1.10.10']
{'jsonrpc': '2.0', 'result': [{'review_period_time': '2020-05-26T07:33:00', 'proposed_transaction': {'operations': [[57, {'committee_max_votes': 9, 'contract_private_data_size': 3072, 'contract_total_data_size': 10485760, 'contract_max_data_size': 2147483648, 'witness_max_votes': 7}]], 'expiration': '2020-05-26T07:40:00', 'ref_block_num': 19416, 'ref_block_prefix': 743339689, 'extensions': ['1.10.10']}, 'allow_execution': True, 'available_active_approvals': ['1.2.5', '1.2.6', '1.2.7', '1.2.8', '1.2.9', '1.2.10', '1.2.11', '1.2.12', '1.2.13', '1.2.14', '1.2.15'], 'available_owner_approvals': [], 'id': '1.10.10', 'available_key_approvals': [], 'required_owner_approvals': [], 'expiration_time': '2020-05-26T07:35:00', 'trx_hash': '402bc6c68d6597e7b2e212c01acf7d3ebacaaf41500233a279eb45e64e1ee55f', 'required_active_approvals': ['1.2.0']}], 'id': 1}

>> get_object 1.10.10
 [{'review_period_time': '2020-05-26T07:33:00', 'proposed_transaction': {'operations': [[57, {'committee_max_votes': 9, 'contract_private_data_size': 3072, 'contract_total_data_size': 10485760, 'contract_max_data_size': 2147483648, 'witness_max_votes': 7}]], 'expiration': '2020-05-26T07:40:00', 'ref_block_num': 19416, 'ref_block_prefix': 743339689, 'extensions': ['1.10.10']}, 'allow_execution': True, 'available_active_approvals': ['1.2.5', '1.2.6', '1.2.7', '1.2.8', '1.2.9', '1.2.10', '1.2.11', '1.2.12', '1.2.13', '1.2.14', '1.2.15'], 'available_owner_approvals': [], 'id': '1.10.10', 'available_key_approvals': [], 'required_owner_approvals': [], 'expiration_time': '2020-05-26T07:35:00', 'trx_hash': '402bc6c68d6597e7b2e212c01acf7d3ebacaaf41500233a279eb45e64e1ee55f', 'required_active_approvals': ['1.2.0']}]

dev@ubuntu:~/test/$ 
```

