# Ledger_Authz_CLI
Through this guide you gonna learn how to enable auto compounding with StakeLab using CLI and the Authz module.  
*Note that this is only for users managing their assets with a Ledger device.*  

## Prerequis:  
*  Linux Machine 20.4+  
*  Few packages  
`apt install build-essential git
wget -c https://go.dev/dl/go1.18.3.linux-amd64.tar.gz && rm -rf /usr/local/go && tar -C /usr/local -xzf go1.18.3.linux-amd64.tar.gz`  
`echo 'export GOROOT=/usr/local/go' >> $HOME/.bash_profile
echo 'export GOPATH=$HOME/go' >> $HOME/.bash_profile
echo 'export GO111MODULE=on' >> $HOME/.bash_profile
echo 'export PATH=$PATH:/usr/local/go/bin:$HOME/go/bin' >> $HOME/.bash_profile && . $HOME/.bash_profile`  
*  

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

### _Asset Mantle_  

### _Axelar_  

### _Band Protocol_  

### _Bitcanna_  

### _Bitsong_  

### _Cerberus_  

### _Certik_  
`git clone https://github.com/ShentuChain/shentu restake_shentu && cd restake_shentu && make install`  

### _Chihuahua_  

### _Comdex_  

### _Commercio_  

### _Cosmos Hub_  

### _Crescent_  

### _Decentr_  

### _Desmos_  

### _Dig Chain_  

### _E_money_  

### _Evmos_  

### _Fetch Ai_  

### _Galaxy_  

### _Gravity Bridge_  

### _Injective_  

### _Iris_  

### _Ixo_  

### _Juno_  

### _Kava_  

### _Ki Chain_  

### _Konstellation_  

### _Lum_  

### _Medibloc_  

### _Meme_  

### _Microtick_  

### _Nomic_  

### _Omniflix_  

### _Oraichain_  

### _Osmosis_  

### _Persistence_  

### _Regen_  

### _Rizon_  

### _Secret_  

### _Sentinel_  

### _Sifchain_  

### _Sommelier_  

### _Stargaze_  

### _Starname_  

### _Terra_  

### _Umee_  

### _Vidulum_  
