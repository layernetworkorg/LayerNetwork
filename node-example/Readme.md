# Run a LAYER Validator
## Setting up a node
1. Git clone https://github.com/layernetworkorg/LAYERNetwork.git

2. Copy source form node-example to root folder
```
cp -r LAYERNetwork/node-example/LAYER /root/
```
3. Create an Account

```
cd /root/LAYER
chmod +x openethereum
./openethereum account new --config nodes/validator/node.toml
```
Returned address like that 0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2

Copy result address to mode.toml
Ex:
```
...
[account]
unlock = ["0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"]
password = ["password"]

[mining]
force_sealing = true
engine_signer = "0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"
reseal_on_txs = "none"
...
```
4. Run the authority nodes
```
./openethereum --config ./nodes/validator/node.toml

```
5. Stake

    Stake

    To stake LAYER coin, all you should do is sending your LAYER coin to the LAYER Consensus contract address over the LAYER network from the validator address.
    The LAYER Consensus contract address: 0x76de9222AD65Ab0d491De1A06d29fF33A3870Bd8
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to LAYER and send the LAYER coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /LAYERNetwork/nodes/validator/keys/LAYER/UTC--xxxx
    /LAYERNetwork/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.
