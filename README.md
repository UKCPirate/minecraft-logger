<!-- INTRO -->
<br />
<div align="center">
  <a href="/">
    <img src="https://cdn-icons-png.flaticon.com/512/462/462642.png" alt="Logo" width="100" height="100">
  </a>

  <h3 align="center">Minecraft Logger</h3>

  <p align="center">
    A Minecraft Server Plugin that logs events to a database :video_game:
    <br />
    <a href="https://github.com/edenia/minecraft-logger">Explore the docs</a>
    /
    <a href="https://github.com/edenia/minecraft-logger/issues/new?template=bug_report.md">Report Bug</a>
    /
    <a href="https://github.com/edenia/minecraft-logger/issues/new?template=feature_request.md">Request Feature</a>
  </p>
</div>


<!-- ABOUT THE PROJECT -->
## About The Project

...



<!-- GETTING STARTED -->
## Getting Started


### Prerequisites

You will need a [PaperMC](https://papermc.io/) server up and runing

### Installation

The steps to install this server are [same](https://docs.papermc.io/paper/adding-plugins) to install anyone, the only difference it's at the config file, so let's start

1. <a href="#contact">Contact us</a> to get your API KEY
2. Download the [SuperLog.jar](SuperLog.jar) file
3. Once you have the plugin downloaded locally, locate the `plugins` folder from the root directory of your Paper server.
4. Drag and drop the plugin file `SuperLog.jar` into the plugins folder.
5. Restart your server. The plugin should load.
6. Replace the content of `plugins/SuperLog/config.yml` with this
```yml
# +————————————————————————————————————————————————————+ #
# |——————————     SUPERLOG CONFIGURATION     ——————————| #
# |——————————————————      v1.2      ——————————————————| #
# +————————————————————————————————————————————————————+ #
# |                   Documentation:                   | #
# |            http://superlog.andross.fr/             | #
# +————————————————————————————————————————————————————+ #

## Time between saving logs (async)
## 0 will save logs instantly (use more resource)
## If you have many players, you should save the cache a bit more often, so you'll need a smaller save-delay.
## If you don't have many players, you can save logs less often, so you can use a greater save-delay.
save-delay: 5

## This is how the date will be displayed into logs file
date-format: 'HH:mm:ss'

# ## This where the logs will be saved
logs-path: '/data'

## This is how the log file will be named
logs-format: '{DAY}-{MONTH}-{YEAR}_{TYPE}.log'

## This is how the log live will be received ingame
logs-live-format: '&7&o[{TIME}][{EVENT}] {LOG}'

## If the plugin should displays in console when logs are saved
logs-in-console: true

## If the plugin should displays in game when logs are saved
logs-in-game: false

## Utilities
## GZip old logs after X days
gzip-logs-after: 2

## Delete old logs after X days
delete-logs:
  after: 7
  even-gzipped: true

## Check for update (async)
check-update: true

## Alert in game when a command is used
commands-alert:
  list:
    - '/gamemode'
    - '/god'
  message: '&7&l{PLAYER}&7 used: &e{COMMAND}'

## Configurable messages
messages:
  prefix: '&3&l[&e&lLOG&3&l] '
  noperm: '&cYou do not have permission.'
  logs-saved: '&7Saved {LOGS} files.'

## Integration with External API
api:
  endpoint: https://example.com/v1/graphql
  token: 'REPLACE_WITH_YOUR_API_KEY'

## List of events to log
## The event names ARE case sensitive
## Full list of events https://superlog.andross.fr/#doc
events:
  EntityDeathEvent:
    enabled: true
    message: '-(\"world\": \"{LOCWORLD}\", \"event\": \"ENTITY_DEATH_EVENT\", \"target\": \"{TYPE}\", \"username\": \"{LASTDEATHBY}\", \"payload\": (\"location\": \"{LOCX};{LOCY};{LOCZ}\"))-'
  BlockPlaceEvent:
    enabled: true
    message: '-(\"world\": \"{LOCWORLD}\", \"event\": \"BLOCK_PLACE_EVENT\", \"target\": \"{ITEMINHAND.NAME}\", \"username\": \"{PLAYER}\", \"payload\": (\"location\": \"{LOCX};{LOCY};{LOCZ}\"))-'

 ```
 7. Remember replace only the text `REPLACE_WITH_YOUR_API_KEY` with your actual API KEY


<!-- LICENSE -->
## License

Distributed under the MIT License. See [LICENSE](LICENSE) for more information.


<!-- CONTACT -->
## Contact

Eric - [@ericattreis](https://github.com/ericattreis)

Project Link: [minecraft.eosusa.io](https://minecraft.eosusa.io/)


<!-- ACKNOWLEDGMENTS -->
## Acknowledgments

This plugin it's a fork from [Logger](https://github.com/ExceptedPrism3/Logger) for more iformation about it take a look to

* [spigotmc.org](https://www.spigotmc.org/resources/logger-1-7-1-19.94236/)
* [ExceptedPrism3](https://github.com/ExceptedPrism3/Logger)


