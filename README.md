# DApp Store TipBot

# Usage:

## Test network

1. Setup TipBot accounts:

```
$ gem install mobius-client
$ mobius-cli create dapp_account

Calling Mobius FriendBot...
 * Public Key: GDF2AY44IYXRLNOZ2BPGM6YWMOFTIJ3M7Y2BD6YGLTY2UWXK3JNTG6F2
 * Private Key: SBWODOL62Y3ALAXJJHA2EEK4GYFYXDLX23AIFJXMQY4V3PTJXEIT47YK
 * MOBI balance: 1000.0
Done!

$ mobius-cli create dapp_account -a GDF2AY44IYXRLNOZ2BPGM6YWMOFTIJ3M7Y2BD6YGLTY2UWXK3JNTG6F2

Calling Mobius FriendBot...
 * Public Key: GC5Z2TW36D5R5HTV57K66P6KNQG4CMCRXPWSLU2EPR5MUNNHQJUYZTPU
 * Private Key: SBTDFELTI4IK22U7XOPVSD7A3BAZI2U3MD2CROSZW4DMML6WVH5OUOYS
 * MOBI balance: 1000.0
Adding cosigner...
Done!
```

First account contains tips (in MOBI by default). Second account is used to accumulate tips which are not yet withdrawn to users.

2. Setup Redis.
3. Obtain bot token in Slack (https://my.slack.com/services/new/bot)

## Run

```
MOBIUS_TIPBOT_REDIS_URL="redis://localhost:6379/8" \
MOBIUS_TIPBOT_SLACK_API_TOKEN="xoxb-340071536035-YnD3U819uiROw1vtdrg3LjQg" \
MOBIUS_TIPBOT_APP_PRIVATE_KEY="SBTDFELTI4IK22U7XOPVSD7A3BAZI2U3MD2CROSZW4DMML6WVH5OUOYS" \
MOBIUS_TIPBOT_CREDIT_ADDRESS="GDF2AY44IYXRLNOZ2BPGM6YWMOFTIJ3M7Y2BD6YGLTY2UWXK3JNTG6F2" \
MOBIUS_TIPBOT_RATE="0.5" \
bundle exec ruby slack.rb
```

`MOBIUS_TIPBOT_RATE` is represents a price of the tip.
