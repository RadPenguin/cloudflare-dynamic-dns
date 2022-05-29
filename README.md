# CloudFlare Dynamic DNS

A simple BASH script that updates a single CloudFlare DNS record.

## First Run

1. Run `update.sh` once to generate the `.env` file.
2. Edit the `.env`, and fill in the settings as instructed.
3. Run `update.sh` again to update the CloudFlare DNS record.

## Options

* `export CF_ENV_FILE=/path/to/.env` - Set this environment variable to change the path to the `.env` file.
* `update.sh --force` - Force an update of the DNS record, regardless of whether your public IP address has changed.