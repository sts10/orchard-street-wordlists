# FAQ 

## Can I have my password manager use an Orchard Street Wordlist?

Some password managers allow users to use any given wordlist file to generate passphrases. [KeePassXC](https://keepassxc.org) is one such password manager.

To have KeePassXC use one of these wordlists, click on KeePassXC's dice icon to open the password generator, then click over to the "Passphrase" tab, then click to + button to choose a word list file. 

![Screenshot showing how to change the word list that KeePassXC uses](img/keepassxc-use.png)

## How can I use dice to create a passphrase?

I'd point you to [the EFF's guide on how to do this](https://www.eff.org/dice) and [this article by Micah Lee](https://theintercept.com/2015/03/26/passphrases-can-memorize-attackers-cant-guess/). Note that you will have to use either the Orchard Street Medium List or one of the Short Lists.

## Do you recommend a CLI tool for generating passphrases?

You could probably do worse than [Micah Lee's passphraseme tool](https://github.com/micahflee/passphraseme). Use the `-d` / `--dictionary` option to use an Orchard Street Wordlist file.

## How _many_ words should I use in a passphrase?

That depends on your threat model, so I can't give a general answer. But if I were forced to give a general rule of thumb, I'd say using 6 words from the long or medium lists (e.g. "fig phases telephone cowboys warning lit") and 7 words from a short list (e.g. "robe towed wooded cue hasty cups each") is a safe bet.

## What's the difference between your Medium list and the EFF "long list"?

They're pretty similar! Both the [EFF's long list](https://www.eff.org/deeplinks/2016/07/new-wordlists-random-passphrases) and the Orchard Street Medium List contain exactly 7,776 words. This is so that each word can correspond to the roll of 5 6-sided dice. Both lists are also _uniquely decodable_, which is good for use with passphrase generators. One difference is that the EFF list is uniquely decodable because it has no "prefix words". The Orchard Street Medium List was made uniquely decodable through [a novel process we invented called Schlinkert pruning](https://sts10.github.io/2022/08/12/efficiently-pruning-until-uniquely-decodable.html). I'll also note that EFF list's mean word length is every so slightly shorter (by 0.07 characters).

The EFF list is definitely more well-known and more widely used choice, so it's 100% the less risky choice. But if you're here reading this FAQ, maybe you want to be on the cutting edge...

## I'm creating a passphrase I know I'll frequently be entering into a smart TV or video game console. Which list should I use?

Entering secure passwords on a smart TV remote or video game controller is a pain. To make this easier, the Orchard Street Short Lists are optimized to minimize the number of "clicks" you must execute to enter a passphrase. 

This number of clicks depends on the keyboard layout. If the service's password keyboard looks like a traditional QWERTY layout:

```txt
qwertyuiop
asdfghjkl
zxcvbnm
```

use the [Orchard Street Qwerty list](lists/orchard-street-qwerty.txt). 

If it's in alphabetical order:

```txt
abcdef
ghijkl
mnopqr
stuvwx
yz
```

use [Orchard Street Alpha](lists/orchard-street-alpha.txt).

You can read [this blog post for more information](https://sts10.github.io/2022/10/24/a-good-netflix-password.html).

## I'm creating passphrase-generation software. Can I use one or more of the Orchard Street Wordlists in my code?

Sure! Just be sure to follow the licensing (see Readme).

## Do I need to use separating punctuation between words in passphrases from Orchard Street Wordlists?

No. All Orchard Street Wordlists are uniquely decodable, which means words from any one of them can be safely combined in a passphrase _without_ punctuation between the words, e.g. "thrillerconcernclearedevidencestretchapple". Though there's nothing wrong with putting a space, hyphen, underscore, etc. between the words if you prefer.

## How were the Orchard Street Wordlists created?

The words that make up these word lists are taken from two sources: [Google Books Ngram data](https://storage.googleapis.com/books/ngrams/books/datasetsv3.html) and [a Wikipedia word frequency project](https://github.com/IlyaSemenov/wikipedia-word-frequency/).

The lists were made uniquely decodable using a process based on [the Sardinas–Patterson algorithm](https://en.wikipedia.org/wiki/Sardinas%E2%80%93Patterson_algorithm) that I call [Schlinkert pruning](https://sts10.github.io/2022/08/12/efficiently-pruning-until-uniquely-decodable.html). 

### What tools were used to create the Orchard Street Wordlists?

- [Tidy](https://github.com/sts10/tidy): A command-line utility for editing word lists. 
- [Common Word List Maker](https://github.com/sts10/common_word_list_maker): Scrapes Google Books Ngram data to create a long word list of commonly used words
