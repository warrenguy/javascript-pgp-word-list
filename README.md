# pgp-word-list.js

Convert hex strings to PGP word lists and vice-versa.

See [PGP word list on WikiPedia](http://en.wikipedia.org/wiki/PGP_word_list]) for more information.

I've also written a Ruby version: [ruby-pgp-word-list](https://github.com/warrenguy/ruby-pgp-word-list).

## Usage

Include pgp-word-list.js, which provides following functions:

````
> pgp_words_to_hex(["stairway", "souvenir", "flytrap", "recipe"])
=> ["D1", "D4", "64", "C0"]

> pgp_hex_to_words(["D1", "D4", "64", "C0"])
=> ["stairway", "souvenir", "flytrap", "recipe"]
````

also singular `pgp_word_to_hex(word)` and `pgp_hex_to_word(hex, position)`.

### More examples

````
> var hexstring = 'd1d4 64c0';
> pgp_hex_to_words(hexstring.toUpperCase().replace(/[^0-9A-F]/g,'').match(/.{1,2}/g))
=> ["stairway", "souvenir", "flytrap", "recipe"]

> var wordstring = 'stairway souvenir flytrap recipe';
> pgp_words_to_hex(wordstring.split(' '))
=> ["D1", "D4", "64", "C0"]

> pgp_words_to_hex(wordstring.split(' ')).join(' ')
=> "D1 D4 64 C0"
````

etc...

## Author

Warren Guy <warren@guy.net.au>

https://warrenguy.me

The word list itself belongs to PGP Corporation.

## License

MIT license. See [LICENSE](https://github.com/warrenguy/ruby-pgp-word-list/blob/master/LICENSE)
