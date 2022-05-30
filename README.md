# CloudFlare Dynamic DNS

A simple BASH script that updates a single CloudFlare DNS record.

## Setup

1. Run `update.sh` once to generate the `.env` file.
2. Edit your `.env` file, and fill in the required information:
    1. `CF_RECORD` - The fully qualified domain name of the record you want to update. Default: `test.example.com`
    2. `CF_RECORD_PROXIED` - Allow CloudFlare to hide the original IP. Must be one of: `true`, `false`. Default: `false`
    3. `CF_RECORD_TTL` - The record TTL, in seconds. Default: `60`
    4. `CF_RECORD_TYPE` - The record type. Must be one of: `A, AAAA`. Default: `A`
    5. `CF_TOKEN` - Your [CloudFlare API token](https://dash.cloudflare.com/profile/api-tokens). It should have Zone
       Edit permissions.
    6. `CF_ZONE` - The domain name you want to update. Default: `example.com`.
3. All other values in `.env` can be ignored, as they'll be populated when the script is run.

## Usage

* `update.sh` - Update the DNS record, but only if your public IP address has changed since last run.
* `update.sh --force` - Force an update of the DNS record, regardless of whether your public IP address has changed.

## Configuration

* `export CF_ENV_FILE=/your/path/to/.env` - Change where the `.env` file is stored (add this to your `~/.bashrc` file).
