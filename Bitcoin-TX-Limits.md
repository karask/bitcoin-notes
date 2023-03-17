# Bitcoin Transaction Limits


## Transaction size limit
The maximum size for legacy (or non-Segwit) transactions is 1 MB, effectively the whole block. The standardness limit, however, is 100 kBs. For Segwit transactions the maximum size limit is 4 MBs  (the weight limit). Again, standardness rules reduce that to 400 kBs.

The minimum size for legacy transactions is 65 bytes.

## Inputs/Outputs limit
Effectively, as many inputs and outputs as the user wants, provided that it fits in the transaction size limit.

# Bitcoin Script Limits

## Bare scripts limit
Bare scripts have a size limit of 10k bytes by consensus. However, standardness rules explicitly specify the kind of locking scripts allowed and the scripts are much smaller (e.g. P2PKH is 25 bytes, P2SH is 23 bytes, etc).

## P2SH scripts limits
P2SH scripts have a size limit of 10k bytes by consensus. Standardness rules only allow for 520 bytes for the redeem script though, which is enough for a 15-of-15 multisig. The maximum unlocking script (scriptSig) size is 1650 bytes.

## P2WSH (Segwit v0) and P2SH-P2WSH limits
P2WSH scripts have a size limit of 10k bytes by consensus. Standardness rules only allow for 3600 bytes for the script witness. In addition, only 201 non-push opcodes are allowed per script and only 520 bytes can be pushed per stack element.

## P2TR (Segwit v1) limits
As P2WSH but the script witness is now limited only by the transaction size (4MBs by consensus and 400kBs by standardness).

## OP_RETURN DATA limit
The consensus rules have no limit to an OP_RETURN size, i.e. the size of the transaction is the limit. One can also have more than one OP_RETURN in a transaction. However, standardness rules specify that only one OP_RETURN output is allowed per transaction with a maximum data size of 80 bytes.
