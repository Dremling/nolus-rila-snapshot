### Nolus Snapshot Setup
We take node snapshot every night at 12:00 UTC+3

You can browse the logs for current snapshot date, block height, and file size information.


##### Stop your node
`sudo systemctl stop nolusd`
##### Reset your node
This will erase your node database. If you are already running validator, be sure you backed up your priv_validator_key.json prior to running the the command.

`nolusd tendermint unsafe-reset-all --home $HOME/.nolus --keep-addr-book`

##### Download & Install the snapshot
`curl -L http://23.88.74.54/nolus/nolus-rila_latest.tar | tar -xf - -C $HOME/.nolus `
##### Restart Service & Check Log:
`sudo systemctl start nolusd && journalctl -u nolusd -f --no-hostname -o cat`
