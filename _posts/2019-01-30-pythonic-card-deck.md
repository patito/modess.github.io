---
layout: post
title: A Pythonic Card Deck (Fluent Python)
---

This code example is from `Fluent Python` book. I'm just reading the whole book and sharing here the code.

<!-- more -->

```python
import collections

Card = collections.namedtuple('Card', ['rank', 'suit'])

class FrenchDeck:
    ranks = [str(n) for n in range(2, 11)] + list('JQKA')
    suits = 'spades diamonds clubs hearts'.split()

    def __init__(self):
        self._cards = [print(rank, suit) for suit in self.suits
                                         for rank in self.ranks]

    def __len__(self):
        return len(self._cards)

    def __getitem__(self, position):
        return self._cards[position]
```
