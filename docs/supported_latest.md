# Unique 3.937052.x

## System

| Name                    | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                         |
| ----------------------- | ------ | --------- | --------- | ------- | --------------------------------- |
| Remark                  |        |           |           |         | `Bytes`remark<br/>                |
| Set heap pages          |        |           |           |         | `u64`pages<br/>                   |
| Set code                |        |           |           |         | `Vecu8`code<br/>                  |
| Set code without checks |        |           |           |         | `Vecu8`code<br/>                  |
| Set storage             |        |           |           |         | `VecKeyValue`items<br/>           |
| Kill storage            |        |           |           |         | `VecKey`keys<br/>                 |
| Kill prefix             |        |           |           |         | `Key`prefix<br/>`u32`subkeys<br/> |
| Remark with event       |        |           |           |         | `Bytes`remark<br/>                |

## ParachainSystem

| Name                     | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                        |
| ------------------------ | ------ | --------- | --------- | ------- | -------------------------------- |
| Set validation data      |        |           |           |         | `ParachainInherentData`data<br/> |
| Sudo send upward message |        |           |           |         | `UpwardMessage`message<br/>      |
| Authorize upgrade        |        |           |           |         | `Hash`code_hash<br/>             |
| Enact authorized upgrade |        |           |           |         | `Vecu8`code<br/>                 |

## Balances

| Name                | Nano S             | Nano S XL          | Nano SP/X          | Nesting            | Arguments                                                                                  |
| ------------------- | ------------------ | ------------------ | ------------------ | ------------------ | ------------------------------------------------------------------------------------------ |
| Transfer            | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | `AccountIdLookupOfT`dest<br/>`CompactBalance`amount<br/>                                   |
| Set balance         |                    | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | `AccountIdLookupOfT`who<br/>`CompactBalance`new_free<br/>`CompactBalance`new_reserved<br/> |
| Force transfer      | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | `AccountIdLookupOfT`source<br/>`AccountIdLookupOfT`dest<br/>`CompactBalance`amount<br/>    |
| Transfer keep alive | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | `AccountIdLookupOfT`dest<br/>`CompactBalance`amount<br/>                                   |
| Transfer all        | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |                    | `AccountIdLookupOfT`dest<br/>`bool`keep_alive<br/>                                         |
| Force unreserve     |                    | :heavy_check_mark: | :heavy_check_mark: |                    | `AccountIdLookupOfT`who<br/>`Balance`amount<br/>                                           |

## Timestamp

| Name | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments            |
| ---- | ------ | --------- | --------- | ------- | -------------------- |
| Set  |        |           |           |         | `Compactu64`now<br/> |

## Treasury

| Name             | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                       |
| ---------------- | ------ | --------- | --------- | ------- | --------------------------------------------------------------- |
| Propose spend    |        |           |           |         | `CompactBalance`amount<br/>`AccountIdLookupOfT`beneficiary<br/> |
| Reject proposal  |        |           |           |         | `Compactu32`proposal_id<br/>                                    |
| Approve proposal |        |           |           |         | `Compactu32`proposal_id<br/>                                    |
| Spend            |        |           |           |         | `CompactBalance`amount<br/>`AccountIdLookupOfT`beneficiary<br/> |
| Remove approval  |        |           |           |         | `Compactu32`proposal_id<br/>                                    |

## Sudo

| Name                  | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                   |
| --------------------- | ------ | --------- | --------- | ------- | ------------------------------------------- |
| Sudo                  |        |           |           |         | `Call`call<br/>                             |
| Sudo unchecked weight |        |           |           |         | `Call`call<br/>`Weight`weight<br/>          |
| Set key               |        |           |           |         | `AccountIdLookupOfT`new\_<br/>              |
| Sudo as               |        |           |           |         | `AccountIdLookupOfT`who<br/>`Call`call<br/> |

## Vesting

| Name                     | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                                        |
| ------------------------ | ------ | --------- | --------- | ------- | -------------------------------------------------------------------------------- |
| Claim                    |        |           |           |         |                                                                                  |
| Vested transfer          |        |           |           |         | `LookupasStaticLookupSource`dest<br/>`VestingScheduleOf`schedule<br/>            |
| Update vesting schedules |        |           |           |         | `LookupasStaticLookupSource`who<br/>`VecVestingScheduleOf`vesting_schedules<br/> |
| Claim for                |        |           |           |         | `LookupasStaticLookupSource`dest<br/>                                            |

## XTokens

| Name                         | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                                                                                                 |
| ---------------------------- | ------ | --------- | --------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| Transfer                     |        |           |           |         | `CurrencyId`currency_id<br/>`Balance`amount<br/>`BoxVersionedMultiLocation`dest<br/>`WeightLimit`dest_weight_limit<br/>                   |
| Transfer multiasset          |        |           |           |         | `BoxVersionedMultiAsset`asset<br/>`BoxVersionedMultiLocation`dest<br/>`WeightLimit`dest_weight_limit<br/>                                 |
| Transfer with fee            |        |           |           |         | `CurrencyId`currency_id<br/>`Balance`amount<br/>`Balance`fee<br/>`BoxVersionedMultiLocation`dest<br/>`WeightLimit`dest_weight_limit<br/>  |
| Transfer multiasset with fee |        |           |           |         | `BoxVersionedMultiAsset`asset<br/>`BoxVersionedMultiAsset`fee<br/>`BoxVersionedMultiLocation`dest<br/>`WeightLimit`dest_weight_limit<br/> |
| Transfer multicurrencies     |        |           |           |         | `VecTupleCurrencyIdBalance`currencies<br/>`u32`fee_item<br/>`BoxVersionedMultiLocation`dest<br/>`WeightLimit`dest_weight_limit<br/>       |
| Transfer multiassets         |        |           |           |         | `BoxVersionedMultiAssets`assets<br/>`u32`fee_item<br/>`BoxVersionedMultiLocation`dest<br/>`WeightLimit`dest_weight_limit<br/>             |

## Tokens

| Name                | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                                                                                           |
| ------------------- | ------ | --------- | --------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| Transfer            |        |           |           |         | `LookupasStaticLookupSource`dest<br/>`CurrencyId`currency_id<br/>`CompactBalance`amount<br/>                                        |
| Transfer all        |        |           |           |         | `LookupasStaticLookupSource`dest<br/>`CurrencyId`currency_id<br/>`bool`keep_alive<br/>                                              |
| Transfer keep alive |        |           |           |         | `LookupasStaticLookupSource`dest<br/>`CurrencyId`currency_id<br/>`CompactBalance`amount<br/>                                        |
| Force transfer      |        |           |           |         | `LookupasStaticLookupSource`source<br/>`LookupasStaticLookupSource`dest<br/>`CurrencyId`currency_id<br/>`CompactBalance`amount<br/> |
| Set balance         |        |           |           |         | `LookupasStaticLookupSource`who<br/>`CurrencyId`currency_id<br/>`CompactBalance`new_free<br/>`CompactBalance`new_reserved<br/>      |

## XcmpQueue

| Name                              | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                               |
| --------------------------------- | ------ | --------- | --------- | ------- | ------------------------------------------------------- |
| Service overweight                |        |           |           |         | `OverweightIndex`index<br/>`XcmWeight`weight_limit<br/> |
| Suspend xcm execution             |        |           |           |         |                                                         |
| Resume xcm execution              |        |           |           |         |                                                         |
| Update suspend threshold          |        |           |           |         | `u32`new\_<br/>                                         |
| Update drop threshold             |        |           |           |         | `u32`new\_<br/>                                         |
| Update resume threshold           |        |           |           |         | `u32`new\_<br/>                                         |
| Update threshold weight           |        |           |           |         | `XcmWeight`new\_<br/>                                   |
| Update weight restrict decay      |        |           |           |         | `XcmWeight`new\_<br/>                                   |
| Update xcmp max individual weight |        |           |           |         | `XcmWeight`new\_<br/>                                   |

## PolkadotXcm

| Name                             | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                                                                                                                                 |
| -------------------------------- | ------ | --------- | --------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Send                             |        |           |           |         | `BoxVersionedMultiLocation`dest<br/>`BoxVersionedXcmTuple`message<br/>                                                                                                    |
| Teleport assets                  |        |           |           |         | `BoxVersionedMultiLocation`dest<br/>`BoxVersionedMultiLocation`beneficiary<br/>`BoxVersionedMultiAssets`assets<br/>`u32`fee_asset_item<br/>                               |
| Reserve transfer assets          |        |           |           |         | `BoxVersionedMultiLocation`dest<br/>`BoxVersionedMultiLocation`beneficiary<br/>`BoxVersionedMultiAssets`assets<br/>`u32`fee_asset_item<br/>                               |
| Execute                          |        |           |           |         | `BoxVersionedXcmTasSysConfigRuntimeCall`message<br/>`XcmWeight`max_weight<br/>                                                                                            |
| Force xcm version                |        |           |           |         | `BoxMultiLocation`location<br/>`XcmVersion`xcm_version<br/>                                                                                                               |
| Force default xcm version        |        |           |           |         | `OptionXcmVersion`maybe_xcm_version<br/>                                                                                                                                  |
| Force subscribe version notify   |        |           |           |         | `BoxVersionedMultiLocation`location<br/>                                                                                                                                  |
| Force unsubscribe version notify |        |           |           |         | `BoxVersionedMultiLocation`location<br/>                                                                                                                                  |
| Limited reserve transfer assets  |        |           |           |         | `BoxVersionedMultiLocation`dest<br/>`BoxVersionedMultiLocation`beneficiary<br/>`BoxVersionedMultiAssets`assets<br/>`u32`fee_asset_item<br/>`WeightLimit`weight_limit<br/> |
| Limited teleport assets          |        |           |           |         | `BoxVersionedMultiLocation`dest<br/>`BoxVersionedMultiLocation`beneficiary<br/>`BoxVersionedMultiAssets`assets<br/>`u32`fee_asset_item<br/>`WeightLimit`weight_limit<br/> |

## CumulusXcm

| Name | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments |
| ---- | ------ | --------- | --------- | ------- | --------- |

## DmpQueue

| Name               | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                               |
| ------------------ | ------ | --------- | --------- | ------- | ------------------------------------------------------- |
| Service overweight |        |           |           |         | `OverweightIndex`index<br/>`XcmWeight`weight_limit<br/> |

## Inflation

| Name            | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                     |
| --------------- | ------ | --------- | --------- | ------- | --------------------------------------------- |
| Start inflation |        |           |           |         | `BlockNumber`inflation_start_relay_block<br/> |

## Unique

| Name                           | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                                                                                                                                                                        |
| ------------------------------ | ------ | --------- | --------- | ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Create collection              |        |           |           |         | `BoundedVecu16ConstU32MAX_COLLECTION_NAME_LENGTH`collection_name<br/>`BoundedVecu16ConstU32MAX_COLLECTION_DESCRIPTION_LENGTH`collection_description<br/>`BoundedVecu8`token_prefix<br/>`CollectionMode`mode<br/> |
| Create collection ex           |        |           |           |         | `CreateCollectionDataAccountId`data<br/>                                                                                                                                                                         |
| Destroy collection             |        |           |           |         | `CollectionId`collection_id<br/>                                                                                                                                                                                 |
| Add to allow list              |        |           |           |         | `CollectionId`collection_id<br/>`CrossAccountId`address<br/>                                                                                                                                                     |
| Remove from allow list         |        |           |           |         | `CollectionId`collection_id<br/>`CrossAccountId`address<br/>                                                                                                                                                     |
| Change collection owner        |        |           |           |         | `CollectionId`collection_id<br/>`AccountId`new_owner<br/>                                                                                                                                                        |
| Add collection admin           |        |           |           |         | `CollectionId`collection_id<br/>`CrossAccountId`new_admin_id<br/>                                                                                                                                                |
| Remove collection admin        |        |           |           |         | `CollectionId`collection_id<br/>`CrossAccountId`account_id<br/>                                                                                                                                                  |
| Set collection sponsor         |        |           |           |         | `CollectionId`collection_id<br/>`AccountId`new_sponsor<br/>                                                                                                                                                      |
| Confirm sponsorship            |        |           |           |         | `CollectionId`collection_id<br/>                                                                                                                                                                                 |
| Remove collection sponsor      |        |           |           |         | `CollectionId`collection_id<br/>                                                                                                                                                                                 |
| Create item                    |        |           |           |         | `CollectionId`collection_id<br/>`CrossAccountId`owner<br/>`CreateItemData`data<br/>                                                                                                                              |
| Create multiple items          |        |           |           |         | `CollectionId`collection_id<br/>`CrossAccountId`owner<br/>`VecCreateItemData`items_data<br/>                                                                                                                     |
| Set collection properties      |        |           |           |         | `CollectionId`collection_id<br/>`VecProperty`properties<br/>                                                                                                                                                     |
| Delete collection properties   |        |           |           |         | `CollectionId`collection_id<br/>`VecPropertyKey`property_keys<br/>                                                                                                                                               |
| Set token properties           |        |           |           |         | `CollectionId`collection_id<br/>`TokenId`token_id<br/>`VecProperty`properties<br/>                                                                                                                               |
| Delete token properties        |        |           |           |         | `CollectionId`collection_id<br/>`TokenId`token_id<br/>`VecPropertyKey`property_keys<br/>                                                                                                                         |
| Set token property permissions |        |           |           |         | `CollectionId`collection_id<br/>`VecPropertyKeyPermission`property_permissions<br/>                                                                                                                              |
| Create multiple items ex       |        |           |           |         | `CollectionId`collection_id<br/>`CreateItemExDataCrossAccountId`data<br/>                                                                                                                                        |
| Set transfers enabled flag     |        |           |           |         | `CollectionId`collection_id<br/>`bool`value<br/>                                                                                                                                                                 |
| Burn item                      |        |           |           |         | `CollectionId`collection_id<br/>`TokenId`item_id<br/>`u128`value<br/>                                                                                                                                            |
| Burn from                      |        |           |           |         | `CollectionId`collection_id<br/>`CrossAccountId`from<br/>`TokenId`item_id<br/>`u128`value<br/>                                                                                                                   |
| Transfer                       |        |           |           |         | `CrossAccountId`recipient<br/>`CollectionId`collection_id<br/>`TokenId`item_id<br/>`u128`value<br/>                                                                                                              |
| Approve                        |        |           |           |         | `CrossAccountId`spender<br/>`CollectionId`collection_id<br/>`TokenId`item_id<br/>`u128`amount<br/>                                                                                                               |
| Approve from                   |        |           |           |         | `CrossAccountId`from<br/>`CrossAccountId`to<br/>`CollectionId`collection_id<br/>`TokenId`item_id<br/>`u128`amount<br/>                                                                                           |
| Transfer from                  |        |           |           |         | `CrossAccountId`from<br/>`CrossAccountId`recipient<br/>`CollectionId`collection_id<br/>`TokenId`item_id<br/>`u128`value<br/>                                                                                     |
| Set collection limits          |        |           |           |         | `CollectionId`collection_id<br/>`CollectionLimits`new_limit<br/>                                                                                                                                                 |
| Set collection permissions     |        |           |           |         | `CollectionId`collection_id<br/>`CollectionPermissions`new_permission<br/>                                                                                                                                       |
| Repartition                    |        |           |           |         | `CollectionId`collection_id<br/>`TokenId`token_id<br/>`u128`amount<br/>                                                                                                                                          |
| Set allowance for all          |        |           |           |         | `CollectionId`collection_id<br/>`CrossAccountId`operator<br/>`bool`approve<br/>                                                                                                                                  |
| Force repair collection        |        |           |           |         | `CollectionId`collection_id<br/>                                                                                                                                                                                 |
| Force repair item              |        |           |           |         | `CollectionId`collection_id<br/>`TokenId`item_id<br/>                                                                                                                                                            |

## Configuration

| Name                                     | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                           |
| ---------------------------------------- | ------ | --------- | --------- | ------- | ------------------------------------------------------------------- |
| Set weight to fee coefficient override   |        |           |           |         | `Optionu64`coeff<br/>                                               |
| Set min gas price override               |        |           |           |         | `Optionu64`coeff<br/>                                               |
| Set xcm allowed locations                |        |           |           |         | `OptionBoundedVecMultiLocationMaxXcmAllowedLocations`locations<br/> |
| Set app promotion configuration override |        |           |           |         | `AppPromotionConfigurationBlockNumber`configuration<br/>            |
| Set collator selection desired collators |        |           |           |         | `Optionu32`max<br/>                                                 |
| Set collator selection license bond      |        |           |           |         | `OptionBalance`amount<br/>                                          |
| Set collator selection kick threshold    |        |           |           |         | `OptionBlockNumber`threshold<br/>                                   |

## Charging

| Name | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments |
| ---- | ------ | --------- | --------- | ------- | --------- |

## Structure

| Name | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments |
| ---- | ------ | --------- | --------- | ------- | --------- |

## ForeignAssets

| Name                   | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                                                                              |
| ---------------------- | ------ | --------- | --------- | ------- | ---------------------------------------------------------------------------------------------------------------------- |
| Register foreign asset |        |           |           |         | `AccountId`owner<br/>`BoxVersionedMultiLocation`location<br/>`BoxAssetMetadataBalanceOfT`metadata<br/>                 |
| Update foreign asset   |        |           |           |         | `ForeignAssetId`foreign_asset_id<br/>`BoxVersionedMultiLocation`location<br/>`BoxAssetMetadataBalanceOfT`metadata<br/> |

## EVM

| Name     | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                                                                                                                                                                                            |
| -------- | ------ | --------- | --------- | ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Withdraw |        |           |           |         | `H160`address<br/>`Balance`amount<br/>                                                                                                                                                                               |
| Call     |        |           |           |         | `H160`source<br/>`H160`target<br/>`Vecu8`input<br/>`U256`value<br/>`u64`gas_limit<br/>`U256`max_fee_per_gas<br/>`OptionU256`max_priority_fee_per_gas<br/>`OptionU256`nonce<br/>`VecTupleH160VecH256`access_list<br/> |
| Create   |        |           |           |         | `H160`source<br/>`Vecu8`init<br/>`U256`value<br/>`u64`gas_limit<br/>`U256`max_fee_per_gas<br/>`OptionU256`max_priority_fee_per_gas<br/>`OptionU256`nonce<br/>`VecTupleH160VecH256`access_list<br/>                   |
| Create2  |        |           |           |         | `H160`source<br/>`Vecu8`init<br/>`H256`salt<br/>`U256`value<br/>`u64`gas_limit<br/>`U256`max_fee_per_gas<br/>`OptionU256`max_priority_fee_per_gas<br/>`OptionU256`nonce<br/>`VecTupleH160VecH256`access_list<br/>    |

## Ethereum

| Name     | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                     |
| -------- | ------ | --------- | --------- | ------- | ----------------------------- |
| Transact |        |           |           |         | `Transaction`transaction<br/> |

## EvmMigration

| Name            | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments                                     |
| --------------- | ------ | --------- | --------- | ------- | --------------------------------------------- |
| Begin           |        |           |           |         | `H160`address<br/>                            |
| Set data        |        |           |           |         | `H160`address<br/>`VecTupleH256H256`data<br/> |
| Finish          |        |           |           |         | `H160`address<br/>`Vecu8`code<br/>            |
| Insert eth logs |        |           |           |         | `VecethereumLog`logs<br/>                     |
| Insert events   |        |           |           |         | `VecVecu8`events<br/>                         |

## Maintenance

| Name    | Nano S | Nano S XL | Nano SP/X | Nesting | Arguments |
| ------- | ------ | --------- | --------- | ------- | --------- |
| Enable  |        |           |           |         |           |
| Disable |        |           |           |         |           |
