# Ledger_Authz_CLI  
Through this guide you gonna learn how to enable auto compounding with StakeLab using CLI and the Authz module.  
*Note that this is only for users managing their assets with a Ledger device.*  

## Prerequis:  
*  Linux Machine 20.4+  
*  Install few packages:  
```shell
apt update && apt upgrade -y 
```  

```shell
apt install build-essential git ufw curl jq -y
```

```shell
wget -c https://go.dev/dl/go1.18.3.linux-amd64.tar.gz && rm -rf /usr/local/go && tar -C /usr/local -xzf go1.18.3.linux-amd64.tar.gz && rm -rf go1.18.3.linux-amd64.tar.gz
```  

```shell
echo 'export GOROOT=/usr/local/go' >> $HOME/.bash_profile
echo 'export GOPATH=$HOME/go' >> $HOME/.bash_profile
echo 'export GO111MODULE=on' >> $HOME/.bash_profile
echo 'export PATH=$PATH:/usr/local/go/bin:$HOME/go/bin' >> $HOME/.bash_profile && . $HOME/.bash_profile
```  
*  Hm, obviously grab your Ledger device and open the Cosmos application

*Note that if you don't have one, you should buy one to start managing your assets in a secure way, juste [here](https://www.ledger.com)*  

## Direct link to a chain:  
[Akash](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#akash)  
[Asset Mantle](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#asset-mantle)  
[Axelar](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#axelar)  
[Band Protocol](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#band-protocol)  
[Bitcanna](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#bitcanna)  
[Bitsong](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#bitsong)  
[Cerberus](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#cerberus)  
[Certik](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#certik)  
[Chihuahua](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#chihuahua)  
[Comdex](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#comdex)  
[Commercio](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#commercio)  
[Cosmos Hub](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#cosmos-hub)  
[Crescent](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#crescent)  
[Decentr](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#decentr)  
[Desmos](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#desmos)  
[Dig Chain](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#dig-chain)  
[Emoney](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#emoney)  
[Evmos](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#evmos)  
[Fetch Ai](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#fetch-ai)  
[Galaxy](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#galaxy)  
[Gravity Bridge](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#gravity-bridge)  
[Injective](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#injective)  
[Iris](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#iris)  
[Ixo](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#ixo)  
[Juno](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#juno)  
[Kava](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#kava)  
[Ki Chain](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#ki-chain)  
[Konstellation](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#konstellation)  
[Lum](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#lum)  
[Medibloc](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#medibloc)  
[Meme](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#meme)  
[Microtick](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#microtick)  
[Nomic](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#nomic)  
[Omniflix](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#omniflix)  
[Oraichain](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#oraichain)  
[Osmosis](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#osmosis)  
[Persistence](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#persistence)  
[Regen](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#regen)  
[Rizon](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#rizon)  
[Secret](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#secret)  
[Sentinel](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#sentinel)  
[Sifchain](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#sifchain)  
[Sommelier](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#sommelier)  
[Stargaze](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#stargaze)  
[Starname](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#starname)  
[Terra](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#terra)  
[Umee](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#umee)  
[Vidulum](https://github.com/StakeLab-Hub/Ledger_Authz_CLI/blob/main/README.md#vidulum)   

## Supported networks:  

### _Akash_  
----------------
### _Asset Mantle_  
----------------
### _Axelar_  
----------------
### _Band Protocol_  
----------------
### _Bitcanna_  
----------------
### _Bitsong_  
----------------
### _Cerberus_  
----------------
### _Certik_  
```shell
git clone https://github.com/ShentuChain/shentu restake_shentu && cd restake_shentu && make install
```  
You should already have the Cosmos application open, if not, open it! Then run: 
```shell
certik keys add certik --ledger
```  
It will generate your address under the wallet name "certik" to make it easier to remember using the chain name.  
Now we will enable StakeLab to auto-compound:  
```shell
certik tx authz grant certik1mjq48r6435aewerpruwc8up3tz3rzan2t3zqq7 generic --msg-type /cosmos.staking.v1beta1.MsgDelegate --from certik --ledger --chain-id shentu-2.2 --node https://rpc.cosmos.directory:443/shentu --gas auto --gas-prices 0.024999999999999998uctk --gas-adjustment 1.5
```  
If you want to stop the auto-compounding, one command to revoke the access:  
```shell
certik tx authz revoke certik1mjq48r6435aewerpruwc8up3tz3rzan2t3zqq7 /cosmos.staking.v1beta1.MsgDelegate --from certik --ledger --chain-id shentu-2.2 --node https://rpc.cosmos.directory:443/shentu --gas auto --gas-prices 0.024999999999999998uctk --gas-adjustment 1.5
```  
----------------
### _Chihuahua_  
----------------
### _Comdex_  
----------------
### _Commercio_  
----------------
### _Cosmos Hub_  
----------------
### _Crescent_  
----------------
### _Decentr_  
----------------
### _Desmos_  
----------------
### _Dig Chain_  
----------------
### _E_money_  
----------------
### _Evmos_  
----------------
### _Fetch Ai_  
----------------
### _Galaxy_  
----------------
### _Gravity Bridge_  
----------------
### _Injective_  
----------------
### _Iris_  
----------------
### _Ixo_  
----------------
### _Juno_  
----------------
### _Kava_  
----------------
### _Ki Chain_  
----------------
### _Konstellation_  
----------------
### _Lum_  
----------------
### _Medibloc_  
----------------
### _Meme_  
----------------
### _Microtick_  
----------------
### _Nomic_  
----------------
### _Omniflix_  
----------------
### _Oraichain_  
----------------
### _Osmosis_  
----------------
### _Persistence_  
----------------
### _Regen_  
----------------
### _Rizon_  
----------------
### _Secret_  
----------------
### _Sentinel_  
----------------
### _Sifchain_  
----------------
### _Sommelier_  
----------------
### _Stargaze_  
----------------
### _Starname_  
----------------
### _Terra_  
----------------
### _Umee_  
----------------
### _Vidulum_  
----------------
