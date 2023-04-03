# Orchard Street Wordlists

Fresh wordlists for all your passphrase-creation needs! Use these wordlists to create strong, secure passphrases, either [with dice](https://www.eff.org/dice), or a password manager/generator.

All of the wordlists included in this repository are uniquely decodable, meaning words from any one of these lists can be safely combined without word separators. For example: "sharkhealsetupthrustphasespy".

## Orchard Street Long List

The [Orchard Street Long List](lists/orchard-street-long.txt) is a 17,576-word list. It provides a robust 14.1 bits of entropy per word, meaning a 7-word passphrase gives almost 99 bits of entropy.

```text
List length               : 17576 words
Mean word length          : 7.98 characters
Length of shortest word   : 3 characters (add)
Length of longest word    : 15 characters (troubleshooting)
Uniquely decodable?       : true
Entropy per word          : 14.101 bits
Efficiency per character  : 1.767 bits
Assumed entropy per char  : 4.700 bits
Mean edit distance        : 7.913

Pseudorandomly generated sample passphrases
-------------------------------------------
selectors lifelong ascended commerce reactors sobbing 
exempt acknowledgment worthless esteem compliments hepatitis 
fortress infertility quota attends correlation rainforest 
precipitation assemblages butcher nobles backed unexpected 
canoeing clandestine guarding chewed calculus cosmological 
```

## Orchard Street Medium List

The [Orchard Street Medium List](lists/orchard-street-medium.txt) is our version of the classic Diceware list. 7,776 words gives a traditional 12.925 bits of entropy per word, same as the EFF long list. Also available in [a Diceware version](lists/orchard-street-medium-dice.txt) (when using dice to create a passphrase, we recommend you follow [EFF's instructions for creating a passphrase](https://www.eff.org/dice)).

```text
List length               : 7776 words
Mean word length          : 7.06 characters
Length of shortest word   : 3 characters (add)
Length of longest word    : 10 characters (worthwhile)
Uniquely decodable?       : true
Entropy per word          : 12.925 bits
Efficiency per character  : 1.832 bits
Assumed entropy per char  : 4.308 bits
Mean edit distance        : 6.955

Pseudorandomly generated sample passphrases
-------------------------------------------
pig broke realized kicked fighter experiment 
episcopal walking gives threaten dividend reserves 
residual paramount networking indicating curve activities 
afghan commenting nucleus regulate hurricane intimate 
surgery tributary entering industry sufficient contents 
```

## Orchard Street Short Lists

[Orchard Street Alpha](lists/orchard-street-alpha.txt) and [Orchard Street QWERTY](lists/orchard-street-qwerty.txt) lists both have 1,296 words and are optimized for inputting resulting passphrases into devices like smart TVs. Each word gives a passphrase an additional 10.34 bits of entropy. 

Use the Alpha list if your devices keyboard is laid out alphabetically; use the QWERTY list if it is in the QWERTY layout.

## Using these word lists with KeePassXC 

Some password managers allow users to use any given wordlist file to generate passphrases. [KeePassXC](https://keepassxc.org) is one of these password managers.

To have KeePassXC use one of these wordlists, click on KeePassXC's dice icon to open the password generator, then click over to the "Passphrase" tab, then click to + button to choose a word list file. 

![Screenshot showing how to change the word list that KeePassXC uses](img/keepassxc-use.png)

## How we created these wordlists

The words contained in these word lists are taken from two sources: [Google Books Ngram data](https://storage.googleapis.com/books/ngrams/books/datasetsv3.html) and [a Wikipedia word frequency project](https://github.com/IlyaSemenov/wikipedia-word-frequency/).

The lists are made uniquely decodable using a process based on [the Sardinas–Patterson algorithm](https://en.wikipedia.org/wiki/Sardinas%E2%80%93Patterson_algorithm) that I'm calling [Schlinkert pruning](https://sts10.github.io/2022/08/12/efficiently-pruning-until-uniquely-decodable.html). 

## Tools I used to generate these word lists

- [Tidy](https://github.com/sts10/tidy): A command-line utility for editing word lists. Can also print notable attributes of word lists, such as those printed above.
- [Common Word List Maker](https://github.com/sts10/common_word_list_maker): Scrapes Google Books Ngram data to create a long word list of commonly used words

## Word sources and licensing

The words contained in these word lists are taken from two sources: [Google Books Ngram data](https://storage.googleapis.com/books/ngrams/books/datasetsv3.html) and [a Wikipedia word frequency project](https://github.com/IlyaSemenov/wikipedia-word-frequency/).

### Licensing

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.

This project has no association with either Google, Wikipedia, or the creators of the Wikipedia frequency project cited above. Neither Google, Wikipedia, nor the creators of the Wikipedia word frequency project cited above endorses this project.
