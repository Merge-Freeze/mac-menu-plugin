# Merge Freeze Mac menu plugin

![merge-freeze-mac-menu-app-example](https://user-images.githubusercontent.com/3083888/188286665-131e3cb8-9b1d-45e2-af4a-2852201c334e.png)

Manage projects without logging into Merge Freeze or visiting a GitHub PR. Powered by [Xbar](https://xbarapp.com/).

### Installation

1. [install Xbar](https://xbarapp.com/dl)
2. open Xbar app > click xbar mac menu icon > click "open plugin folder"
3. `cd ~/Library/Application\ Support/xbar/plugins/ && touch merge-freeze.5m.rb` > paste raw contents of [merge-freeze.5m.rb](https://github.com/Merge-Freeze/mac-menu-plugin/blob/master/merge-freeze.5m.rb) into file
4. while still in `xbar/plugins` directory, `chmod +x merge-freeze.5m.rb` (file must be executable)
5. click xbar mac menu icon > click "Refresh all" to activate Merge Freeze plugin
6. click the Merge Freeze menu icon > press "CMD+E" to open plugin interface
7. add your organization's GitHub slug and a Merge Freeze [organization-level API token](https://docs.mergefreeze.com/web-api#organization-access-tokens-organizations-only) in the labeled fields, then click the "refresh" button

### Features

* the Merge Freeze icon in your menu bar will toggle a red/white fill when 1+ repos are frozen
* click the icon to view frozen/unfrozen repositories, sorted alphabetically
* view upcoming Scheduler freeze/unfreeze events, in multiple date formats
* select any frozen repository to view its blocked pull requests on GitHub
* select any unfrozen repository to view it in your Merge Freeze dashboard

### Customizing

below are tweaks you can add to your own build, or as a PR:

* ability to freeze/unfreeze directly from the menu dropdown (`href=` [parameter](https://github.com/matryer/xbar-plugins/blob/main/CONTRIBUTING.md#parameters))
* custom icons (we offer native support for 2, frozen/unfrozen state)
* increase or decrease the fetch frequency by changing `5m` in filename (eg `10s` = 10 seconds, `3h` = 3 hours `1d` = 1 day, etc)

**icon preparation**
save 22px image w/ padding to PNG, then [convert](https://www.base64-image.de/) to Base64 and update `Icons` module definitions.

### Contributing

the MVP requires Ruby to be installed on your system, but it would be easy to convert this script to bash. PRs in all [supported languages](https://github.com/matryer/xbar-plugins/blob/main/CONTRIBUTING.md#supported-languages) welcome (naming: `merge-freeze.{refresh-rate}.{file-ext}`).
