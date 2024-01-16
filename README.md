# luamin, a Lua minifier written in JavaScript

[![Build status](https://travis-ci.org/mathiasbynens/luamin.svg?branch=master)](https://travis-ci.org/mathiasbynens/luamin)

luamin uses the excellent [gluaparse](https://github.com/everyday-as/glua.js) library to parse Lua code into an Abstract Syntax Tree. Based on that AST, luamin then generates a (hopefully) more compact yet semantically equivalent Lua program. [Here’s an online demo.](https://mothereff.in/lua-minifier)

luamin was inspired by the [LuaMinify](https://github.com/stravant/LuaMinify) and [Esmangle](https://github.com/Constellation/esmangle) projects.

Feel free to fork if you see possible improvements!

## Usage

```js
var luaCode = 'a = ((1 + 2) - 3) * (4 / (5 ^ 6)) -- foo';
luamin.minify(luaCode); // 'a=(1+2-3)*4/5^6'

// `minify` also accepts luaparse-compatible ASTs as its argument:
var ast = luaparse.parse(luaCode, { 'scope': true });
luamin.minify(ast); // 'a=(1+2-3)*4/5^6'
```

## Author

| [![twitter/mathias](https://gravatar.com/avatar/24e08a9ea84deb17ae121074d0f17125?s=70)](https://twitter.com/mathias "Follow @mathias on Twitter") |
|---|
| [Mathias Bynens](https://mathiasbynens.be/) |

## License

luamin is available under the [MIT](https://mths.be/mit) license.
