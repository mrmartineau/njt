<h1 align="center"> 🐸 njt 🐸</h1>

<p align="center">
<b>🐸 npm jump to 🐸</b><br/>
<a href="https://njt.now.sh/">njt.now.sh</a>
</p>

<p align="center">
🛠🛠🛠🛠🛠🛠🛠🛠🛠🛠<br/>
⚠️⚠️ <b>work in progress</b> ⚠️⚠️<br/>
🛠🛠🛠🛠🛠🛠🛠🛠🛠🛠
</p>

Are you often typing npm package names in your search engine to then manually navigate to an npm page, repository, homepage, changelog, versions and so on? 🕐🕑🕒🕓🕔

[Save five seconds thousands of times](https://xkcd.com/1205/) by quickly jumping to the right URL in one go!
Here is a magic spell to remember:

```
🐸✨🐸✨🐸
njt <package name> [destination]
🐸✨🐸✨🐸
```

Examples:

`njt prettier` (no specified destination)  
🐸→ https://www.npmjs.com/package/prettier

`njt prettier h` (homepage)  
🐸→ https://prettier.io

`njt prettier r` (repository)  
🐸→ https://github.com/prettier/prettier

`njt prettier c` (changelog)  
🐸→ https://github.com/prettier/prettier/blob/master/CHANGELOG.md

`njt prettier y` (yarn)  
🐸→ https://yarn.pm/prettier

_There’s more, see below!_

## Getting `njt`

There are several entry points into `njt`.
Pick your favourite or use ’em all!

### 🟢 Command-line tool

Install `njt` globally [from npm](https://www.npmjs.com/package/njt) by running this command in your terminal:

```bash
npm install --global njt
```

You are all set.
Try typing `njt <package> [destination]` in your terminal.
For example, these two commands will take you to Lodash **r**epository and **h**omepage, respectively:

```bash
njt lodash r
njt lodash h
```

A list of supported destinations will be shown if you launch `njt` without arguments.

To uninstall, run `npm remove --global njt`.
To upgrade, run `npm install --global njt` again.

**Pro tip 💡** To customise which browser you want to open, globally set an environment variable called `NJT_BROWSER` (or just `BROWSER`) with the app name of your choice.
The value [may vary](https://www.npmjs.com/package/open#app) based on your OS.
Note that setting `BROWSER` insted of `NJT_BROWSER` may affect other tools, which may or may not be desired.

### 🟢 Search bookmark in Firefox

You can use `njt` right from the address bar in Firefox.

1.  Open [njt.now.sh](https://njt.now.sh)
1.  Right-click on the search input field
1.  In the context menu, select _Add Keyword for this Search..._
1.  You’ll see a small form; type `njt` into the _Keyword_ field
1.  Hit _Save_

From now on, typing `njt <package> [destination]` in the address bar will take you directly to a page you want (for example, `njt react h` will take you to the [React.js homepage](https://reactjs.org/)).

To uninstall, open Firefox bookmarks from the main menu, search for `njt` and remove the bookmark.

**Pro tip 💡** You can use `n` instead of `njt` as a _search keyword_ to save two extra characters each time.
The command to type in Firefox will be `n <package> [destination]` 🚀

### 🟢 DuckDuckGo bang

> I'll submit the bang to DuckDuckGo as soon as the MVP is ready

<s>If you use [duckduckgo.com](https://duckduckgo.com/) as your primary search engine, type `!njt <package> [destination]` in its search field (note the leading exclamation mark).
This trick is possible thanks to DuckDuckGo’s awesome [bang feature](https://duckduckgo.com/bang).</s>

### 🟢 Online search field at the `njt`’s mini-webiste

Open [njt.now.sh](https://njt.now.sh), type your query, press enter.
This method is a bit slower than the other ones because you have to open the landing page first, however, it works everywhere and does not require setup.

Thanks to [now.sh](https://now.sh) for hosting [njt.now.sh](https://njt.now.sh) 💚

### 🟢 More ways?

Are you a shortcut guru?
Feel free [to suggest](https://github.com/kachkaev/njt/issues/new) another entry point into `njt` to save more of the people’s time!

## Available destinations

- `c` → changelog
- `h` → homepage (aliased as `w` for website or `d` for docs)
- `i` → repository issues (aliased as `b` for bugs)
- `n` → package page on [npmjs.com](https://www.npmjs.com/)
- `p` → repository pull requests
- `r` → repository root
- `t` → repository tags (also called releases)
- `v` → list of all packages versions with their publish dates on [npmjs.com](https://www.npmjs.com/)
- `y` → package page on [yarnpkg.com](https://yarnpkg.com/) (mirror registry for [npmjs.com](https://www.npmjs.com/))

Omitting the destination takes you to the package page on [npmjs.com](https://www.npmjs.com/) as if you used `n`.

## How does `njt` work?

For requests like `njt [package]`, `njt [package] n` or `njt [package] y`, the tool just navigates you to URLs like `https://www.npmjs.com/package/[package]` or `https://yarn.pm/[package]`.

Other cases require looking into `package.json` of the latest published version.
This file contains links to the repository, the homepage and other fields, which `njt` uses to construct the destination URL.

The command line version of the tool takes you to `https://njt.now.sh/jump?q=YOUR_QUERY`, from which you are redirected to the destination.

## Prior art

Shortcuts to some destination are built into `npm`:

📦 [`npm docs <package>` or `npm home <package>`](https://docs.npmjs.com/cli/docs)  
⭥  
🐸 `njt <package> h`

---

📦 [`npm repo <package>`](https://docs.npmjs.com/cli/repo)  
⭥  
🐸 `njt <package> r`

---

📦 [`npm bugs <package>` or `npm issues <package>`](https://docs.npmjs.com/cli/bugs)  
⭥  
🐸 `njt <package> i`

With `njt`, you have access to more shortcuts in a variety of environments, not limited to the command line.