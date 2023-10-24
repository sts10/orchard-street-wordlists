# FAQ 

## How can I use dice to create a passphrase?

I'd point you to [the EFF's guide on how to do this](https://www.eff.org/dice) and [this article by Micah Lee](https://theintercept.com/2015/03/26/passphrases-can-memorize-attackers-cant-guess/). Note that you will have to use either the Orchard Street Diceware List or one of the Short Lists.

## Can I have my password manager use an Orchard Street Wordlist?

Some password managers allow users to use any given wordlist file to generate passphrases. [KeePassXC](https://keepassxc.org) (v 2.7+) is one such password manager.

To have KeePassXC use one of these wordlists, click on KeePassXC's dice icon to open the password generator, then click over to the "Passphrase" tab, then click to + button to choose a word list file. 

![Screenshot showing how to change the word list that KeePassXC uses](img/keepassxc-use.png)

## How _many_ words should I use in a passphrase?

That depends on your threat model, so I can't give a general answer. But if I were forced to give a general rule of thumb, I'd say using 6 words from the long or medium lists (e.g. "fig phases telephone cowboys warning lit") and 7 words from a short list (e.g. "robe towed wooded cue hasty cups each") is a safe bet.

## Are any password managers currently using any Orchard Street Wordlists?

* The [Buttercup password manager](https://buttercup.pw/) [now uses](https://github.com/buttercup/buttercup-generator/pull/18) the Orchard Street Medium list as its passphrase word list. 
* [Strongbox](https://strongboxsafe.com/) [offers](https://github.com/strongbox-password-safe/Strongbox/blob/master/resources/wordlists/orchard-street-diceware.txt) the Orchard Street Diceware list to users looking to generate passphrases. 

If you find other examples, feel free to create an Issue or PR!

## Do you recommend a CLI tool for generating passphrases?

I created [a passphrase generator that uses the Orchard Street Wordlists that I call Phraze](https://github.com/sts10/phraze).

If you don't trust me or like Rust, there's also [Micah Lee's passphraseme tool](https://github.com/micahflee/passphraseme). Use the `-d` / `--dictionary` option to use an Orchard Street Wordlist file.

## Do I need to use separating punctuation between words in passphrases from Orchard Street Wordlists?

No. All Orchard Street Wordlists are **uniquely decodable**, which means words from any one of them can be safely combined in a passphrase _without_ punctuation between the words, e.g. "thrillerconcernclearedevidencestretchapple". Though there's nothing wrong with putting a space, hyphen, underscore, etc. between the words if you prefer.

## What's the difference between the Orchard Street Diceware List and the EFF "long list"? They both have 7,776 words...

They're pretty similar! Both the [EFF's long list](https://www.eff.org/deeplinks/2016/07/new-wordlists-random-passphrases) and the Orchard Street Diceware List contain exactly 7,776 words. This is so that each word can correspond to the roll of 5 6-sided dice. Both lists are also _uniquely decodable_, which is good for use with passphrase generators. One difference is that the EFF list is uniquely decodable because it has no "prefix words". The Orchard Street Diceware List was made uniquely decodable through [a novel process I invented called Schlinkert pruning](https://sts10.github.io/2022/08/12/efficiently-pruning-until-uniquely-decodable.html). I'll also note that EFF list's mean word length is ever so slightly shorter (by 0.07 characters).

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

## I'm creating passphrase-generation software. Can I use one or more of the Orchard Street Wordlists in my project?

Sure! Just be sure to follow the licensing (see readme file).

## If I want a really long list, can I combine all of the Orchard Street Wordlists into one super long list?

I would NOT recommend doing this. The reason is that, even if you removed duplicate words, the resulting list would **almost certainly not be uniquely decodable**, an important quality.

Though if you do feel the need to edit an existing list or make you're own word list, you're welcome to use a tool I wrote called [Tidy](https://github.com/sts10/tidy), which can make lists uniquely decodable using a variety of methods, including Schlinkert pruning. 

Lastly, if you want a very long uniquely decodable list, you can try [this 40,000-word list I created](https://github.com/sts10/generated-wordlists/blob/main/lists/experimental/ud2.txt) as part of another project.

## How were the Orchard Street Wordlists created?

The words that make up these word lists are taken from two sources: [Google Books Ngram data](https://storage.googleapis.com/books/ngrams/books/datasetsv3.html) and [a Wikipedia word frequency project](https://github.com/IlyaSemenov/wikipedia-word-frequency/).

The lists were made uniquely decodable using a process based on [the Sardinas–Patterson algorithm](https://en.wikipedia.org/wiki/Sardinas%E2%80%93Patterson_algorithm) that I call [Schlinkert pruning](https://sts10.github.io/2022/08/12/efficiently-pruning-until-uniquely-decodable.html). 

### What tools were used to create the Orchard Street Wordlists?

- [Tidy](https://github.com/sts10/tidy): A command-line utility for editing word lists that I wrote.
- [Common Word List Maker](https://github.com/sts10/common_word_list_maker): Scrapes Google Books Ngram data to create a long word list of commonly used words
- [Wikipedia word frequency generator](https://github.com/IlyaSemenov/wikipedia-word-frequency): Gather word frequencies from Wikipedia articles.
