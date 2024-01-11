## Shopware6 Plugins

### Table of contents
 - [Foreword](#Foreword)
 - [Software requirements](#Softwarerequirements)
 - [Handle custom and third party plugins with composer](#Handlecustomandthirdpartypluginswithcomposer)
 - [Create custom plugins](#Createcustomplugins)
 - [Create and install custom theme](#Createandinstallcustomtheme)

#### Foreword
 This instrcution does not explain how to work with your IDE, WSL2 System or in Linux in general.
Detailed knowledge about the tools and systems are essential!

#### Software requirement
You need some software to create shopware6 custom plugins...
 - [PHPStorm](https://www.jetbrains.com/de-de/phpstorm/) + [Shopware6Toolbox Plugin](https://plugins.jetbrains.com/plugin/17632-shopware-6-toolbox)
 - VCS (Version Control System) like [git](https://git-scm.com/)
 - [WSL2](https://learn.microsoft.com/de-de/windows/wsl/install) System
 - [Docker](https://www.docker.com/) for Windows or in your WSL System

#### Handle custom and third party plugins with composer
shopware6 directory for third party plugins:

```<project>/src/vendor/manufacturer/PluginName```

Adding, removing or updating plugins

```composer require <pluginprefix/plugin-name>```

```composer remove <pluginprefix/plugin-name>```

```composer update <pluginprefix/plugin-name>```

```composer install```

***Don't forget to stay synchronized with composer.json and composer.lock from your VCS and add changes if you add or remove modules!!!***

#### Create custom plugins
A shopware6 plugin needs a plugin base class and a composer.json to work properly. You can find templates for those files in the [repository](https://github.com/keanuklennerdev/sw6plugins/tree/main/ConnePluginName).

To make the plugin work in the shop use these [shopware console commands](https://docs.shopware.com/en/shopware-6-en/tutorials-and-faq/shopware-cli):

```bin/console plugin:refresh```

```bin/console plugin:install PluginName (--activate, --clearCache)```

```bin/console plugin:activate PluginName ```

```bin/console plugin:deactivate PluginName ```

#### Create and install custom theme
A shopware6 theme plugin needs a plugin base class, composer.json and theme.json file to work properly. You can find templates for those files in the [repository](https://github.com/keanuklennerdev/sw6plugins/tree/main/ConneThemeName).

To install the theme for the shop use these [shopware console commands](https://docs.shopware.com/en/shopware-6-en/tutorials-and-faq/shopware-cli):

```bin/console plugin:refresh```

```bin/console plugin:install PluginName (--activate, --clearCache)```

```bin/console plugin:activate PluginName ```

```bin/console plugin:deactivate PluginName ```

To change the saleschannel theme to yours use these [shopware console commands](https://docs.shopware.com/en/shopware-6-en/tutorials-and-faq/shopware-cli):

```bin/console theme:change --no-compile```

```bin/console theme:compile```

