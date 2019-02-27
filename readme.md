# Elemental Battle Card Game

**This is a Card Game build on EOS Blockchain. It uses React-Redux for its frondend application.**

## Installing Process

Before running this application make sure that node, npm and nodeos is intalled on your device.

Clone this repo and open contracts folder in terminal.

Run command

eosio-cpp -o cardgame.wasm cardgame.cpp -abigen

This command will generate .wasm and .abi file which we will deploy on eosio blockchain.

start keosd with following command :

> keosd &

keosd securely stores and manages keys

start nodeos with following command

>nodeos -e -p eosio \
>  --plugin eosio::producer_plugin \
>  --plugin eosio::chain_api_plugin \
>  --plugin eosio::http_plugin \
>  --plugin eosio::history_plugin \
>  --plugin eosio::history_api_plugin \
>  --access-control-allow-origin='*' \
>  --contracts-console \
>  --http-validate-host=false \
>  --verbose-http-errors \
>  --filter-on='*' >> nodeos.log 2>&1 &
