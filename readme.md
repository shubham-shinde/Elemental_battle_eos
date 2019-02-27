# Elemental Battle Card Game

**This is a Card Game build on EOS Blockchain. It uses React-Redux for its frondend application.**

## Installing Process

Before running this application make sure that node, npm and nodeos is intalled on your device.

Clone this repo and open contracts folder in terminal.

Run command

> eosio-cpp -o cardgame.wasm cardgame.cpp -abigen

This command will generate .wasm and .abi file which we will deploy on eosio blockchain.

start **keosd** with following command :

> keosd &

keosd securely stores and manages keys

start **nodeos** with following command

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

open http://localhost:8888/v1/chain/get_info in any browser to check nodeos

## Create Accounts and Wallets

creat eosio default wallet

> cleos wallet create -n default --to-console

save the private key printed on console

Import a private key to this wallet using command.

> cleos wallet import -n default --private-key PW5JxAwWYRxFbiiTXiwoXRugdywTVo8FkZHnQk84L2wBFYG49798q

Now, Creat a wallet named cardgamewal using command:

> cleos wallet creat -n cardgamewal --to-console

Save the password printed on console

Import owner key and active key to cardgamewal using command:

> cleos wallet import -n cardgamewal --private-key 5JpWT4ehouB2FF9aCfdfnZ5AwbQbTtHBAwebRXt94FmjyhXwL4K
> cleos wallet import -n cardgamewal --private-key 5JD9AGTuTeD5BXZwGQ5AtwBqHK21aHmYnTetHgk1B3pjj7krT8N

We want public keys associated with these private keys. 

> cleos wallet private-keys -n cardgamewal

and past the password on cardgamewal which we saved when we create the cardgamewal.
You will get public keys with private keys

Now create an account to deploy our contract on blockchain

> cleos create account eosio cardgameacc EOS6PUh9rs7eddJNzqgqDx1QrspSHLRxLMcRdwHZZRL4tpbtvia5B EOS8BCgapgYA2L4LJfCzekzeSr3rzgSTUXRXwNi8bNRoz31D14en9

Note : These two keys are the public keys of active and owner key







