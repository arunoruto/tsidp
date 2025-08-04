# tsidp

> [!WARNING]  
> Tailscale provides an official tsidp image now: https://hub.docker.com/r/tailscale/tsidp

> [!NOTE]  
> This repository is automated! Please look at the package versions
> [here](https://github.com/arunoruto/tsidp/pkgs/container/tsidp).
> If the code hasn't been touched for a long time, don't worry;
> containers are built against the newest release of Tailscale.

I saw the [video about tsidp](https://www.youtube.com/watch?v=BdQ-Gz6bs3g),
I found it a bit sad that there was no docker container to try it out.
So I sat down to make one myself: compile it, package it, publish it.
The image is available at `ghcr.io/arunoruto/tsidp`.
You can either use `latest` for the newest version
or pin it to a specific release of Tailscale from their [repo](https://github.com/tailscale/tailscale).

## Config

|          env           | required |                                      description                                       | default value |
| :--------------------: | :------: | :------------------------------------------------------------------------------------: | :-----------: |
|       TS_AUTHKEY       |   true   | Tailscale authkey. You can get it from https://login.tailscale.com/admin/settings/keys |    <empty>    |
|      TS_USERSPACE      |  false   |                               Use userspace networking.                                |     false     |
|        VERBOSE         |  false   |                                Get verbose log output.                                 |     false     |
| TAILSCALE_USE_WIP_CODE |  false   |                Code is work in progress. Is needed for `tsidp` to work!                |       1       |

## Compose

There is a `compose.yml` which can be used to incorporate it in your Tailscale compose setup.
Either replace `${TS_AUTHKEY}` under environment with your key,
or create a `.env` file with `TS_AUTHKEY=paste-your-key-here`.

## Contribute

Feel free to open an issue if you have any questions or problems,
or even better, fork the repo and open a PR with a fix ;)

## TODO

- [x]] Save the current newest version in cache. If there wasn't a new release, don't rebuild.
  -> If this is implemented, daily checks could be implemented!
