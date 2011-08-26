---
title: Searching for modules with npm
author: George Ornbo
layout: post
excerpt: How to find node.js modules using the command line or the web
tags:
- npm
---

The node.js community has many modules that you can use in your projects. But how do you find them?

### Finding modules with npm

You can use the npm command line tool to search the registry using the command `npm search`.

    npm search irc
    NAME                DESCRIPTION                                                   AUTHOR          KEYWORDS
    ann                 IRC bot made to announce and for convenience.                 =neat           irc bot
    app                 mirco web app framework                                       =rolandpoulter  micro web app

If you want more information on a module you can use `npm info`. This returns information from the package.json file provided by the author

    npm info ann
    { name: 'ann',
      description: 'IRC bot made to announce and for convenience.',
      'dist-tags': { latest: '0.1.3' },
      versions: 
       [ '0.1.0',
         '0.1.1',
         '0.1.2',
         '0.1.3' ],
      maintainers: 'neat <wrapper476@gmail.com>',
      time: 
       { '0.1.0': '2011-07-28T11:39:26.322Z',
         '0.1.1': '2011-07-28T11:49:34.406Z',
         '0.1.2': '2011-07-28T13:24:52.076Z',
         '0.1.3': '2011-07-28T13:37:27.122Z' },
      author: 'Roly Fentanes (https://github.com/fent)',
      repository: 
       { type: 'git',
         url: 'git://github.com/fent/Ann.git' },
      keywords: [ 'irc', 'bot' ],
      version: '0.1.3',
      homepage: 'https://github.com/fent/Ann',
      main: './lib/Ann.js',
      directories: { lib: './lib' },
      engines: { node: '*' },
      dependencies: 
       { irc: '>=0.2.0',
         async: '>=0.1.9',
         'cli-color': '>=0.1.1',
         sprintf: '>=0.1.0' },
      licenses: 
       { type: 'MIT',
         url: 'http://github.com/fent/ann/raw/master/LICENSE' },
      devDependencies: {},
      dist: 
       { shasum: 'bb0db0ac007362f7fa5605aea2d57a059a084a6c',
         tarball: 'http://registry.npmjs.org/ann/-/ann-0.1.3.tgz' },
      scripts: {} }


### Finding modules via the web 

There is also a [web based search tool][1] that lists some further information like the latest updates and the most depended on modules. This can be helpful for finding new modules and modules that are considered stable.

[![npm web registry][4]][1]


[Blagovest Dachev][2] created [a site][3] that pulls in additional information from the Github repository for projects and gives you information on the number of watchers, forks and issues a project has. This is extremely useful for seeing how active a project is and when it was last updated. 

[![npm with added github zing][5]][3]

[1]: http://search.npmjs.org/
[2]: https://github.com/dachev
[3]: http://blago.dachev.com/modules
[4]: http://cdn.nodejsbook.io/images/articles/npm_websearch.png
[5]: http://cdn.nodejsbook.io/images/articles/npm_github_web.png
