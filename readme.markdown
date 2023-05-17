# Orchard Street Wordlists

Fresh wordlists for all your passphrase-creation needs. Use these wordlists to create strong, secure passphrases, either [with dice](https://www.eff.org/dice) or a password manager/generator.

All of the wordlists included in this repository are **uniquely decodable**, meaning words from any one of these lists can be safely combined without word separators. For example: "sharkhealsetupthrustphasespy".

**Note** that I am still removing and replacing a few words here and there, and thus none of these lists should be considered as "finalized" as long as this paragraph is present. Obviously you're free to download a (static) copy, download the latest release, or fork this repository at any time if you require a static, unchanging list.

## Orchard Street Long List

The [Orchard Street Long List](lists/orchard-street-long.txt) is a 17,576-word list. It provides a hefty 14.1 bits of entropy per word, meaning a 7-word passphrase gives almost 99 bits of entropy.

```text
List length               : 17576 words
Mean word length          : 7.98 characters
Length of shortest word   : 3 characters (add)
Length of longest word    : 15 characters (troubleshooting)
Free of prefix words?     : false
Uniquely decodable?       : true
Entropy per word          : 14.101 bits
Efficiency per character  : 1.767 bits
Above brute force line?   : true
Mean edit distance        : 7.914

Word samples
------------
constancy combating sugar invading workable recession
nickname capitals mocking coliseum archipelago evaporation
certainly postures beta exit accuse furious
packaging romances foyer mountain pulls scenery
phase savage vicinity fumes senator engineer
```

## Orchard Street Medium List

The [Orchard Street Medium List](lists/orchard-street-medium.txt) is our version of the classic Diceware list. 7,776 words gives a traditional 12.925 bits of entropy per word, same as [the EFF long word list](https://www.eff.org/deeplinks/2016/07/new-wordlists-random-passphrases). Also available [with corresponding dice roll numbers prepended](lists/orchard-street-medium-dice.txt) (when using dice to create a passphrase, we recommend you follow [EFF's instructions for creating a passphrase](https://www.eff.org/dice)).

```text
List length               : 7776 words
Mean word length          : 7.05 characters
Length of shortest word   : 3 characters (add)
Length of longest word    : 10 characters (worthwhile)
Free of prefix words?     : false
Uniquely decodable?       : true
Entropy per word          : 12.925 bits
Efficiency per character  : 1.832 bits
Above brute force line?   : true
Mean edit distance        : 6.954

Word samples
------------
sees talking exclusion inequality granite prefer
faction surgery toll accepts songs unfamiliar
manifest rulers devils governors flight brutal
prosecutor lemon reluctant targets penguin brethren
wade chassis stuck coated sharing imagery
```

## Orchard Street Short Lists

[Orchard Street Alpha](lists/orchard-street-alpha.txt) and [Orchard Street QWERTY](lists/orchard-street-qwerty.txt) lists both have 1,296 words and are optimized for inputting resulting passphrases into devices like smart TVs. Each word gives a passphrase an additional 10.34 bits of entropy.

The difference between these two lists are which **keyboard layout** they are optimized for. Use the Alpha list if your device's keyboard is laid out alphabetically; use the QWERTY list if it is closer to [the QWERTY layout](https://en.wikipedia.org/wiki/QWERTY).

For more information, see [this GitHub repo](https://github.com/sts10/remote-words) and/or [this blog post](https://sts10.github.io/2022/10/24/a-good-netflix-password.html).

## FAQ

Check [our FAQ](faq.markdown) for answers to frequently asked questions.

## Word sources and licensing

The words contained in these word lists are taken from two sources: [Google Books Ngram data](https://storage.googleapis.com/books/ngrams/books/datasetsv3.html) (2012 data) and Wikipedia, via [a Wikipedia word frequency project](https://github.com/IlyaSemenov/wikipedia-word-frequency/), taken on April 13, 2023.

This project has no association with either Google, Wikipedia, or the creators of the Wikipedia frequency project cited above. Neither Google, nor Wikipedia, nor the creators of the Wikipedia word frequency project cited above endorses this project.

At that time that words were pulled from Wikipedia, [Wikipedia text was (and still is, as of this writing) licensed as Creative Commons Attribution-ShareAlike 3.0 Unported License ("CC BY-SA")](https://foundation.wikimedia.org/wiki/Policy:Terms_of_Use#7._Licensing_of_Content), and thus I am using that license for this project. (Note that technically this data is from dumps.wikimedia.org, which is [also licensed the same way](https://dumps.wikimedia.org/legal.html).)

<!-- ### Licensing -->
<a rel="license" href="http://creativecommons.org/licenses/by-sa/3.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/3.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/3.0/">Creative Commons Attribution-ShareAlike 3.0 Unported License</a>.
