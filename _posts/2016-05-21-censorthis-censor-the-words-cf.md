---
layout: post
title:  "Jeux vidéo en bibliothèque : Médiathèque de la Marine (Colombes, 92)"
date:   2019-08-03 13:30:54 +0100
categories: [jeux-vidéo, médiathèque]
---

Je vous présente quelques exemples de mise à dispositon de jeux-vidéo en médiathèque. Pour ce premier épisode, il s'agit de ce que j'ai mis en place à la médiathèque de la Marine, de la ville de Colombes (92). C'est une médiathèque de quartier, le budget alloué aux jeux-vidéo est de 300€/an, la médiathèque dispose d'une PS4, une Switch, une petite borne d'arcade (raspberry pi), un pc pour la réalité virtuelle et un parc de 12 EPN (sous linux).

Dans cette médiathèque il n'y a pas de système de prêt de jeu. Uniquement du jeu sur place.

## Consoles

Les consoles sont placées dans un espace vitré fermé appellé la "bulle jeux-vidéo". La bulle est un espace assez petit (<10m²) dans lequel sont branchées une PS4, une Switch et deux téléviseurs. Les consoles sont placées dans des meubles fermés à clé pour ne pas être directement accessibles au public.

Les usagers peuvent se présenter à la banque de prêt seuls ou à deux, on leur remet des manettes en échange de leur carte de bibliothèque pour une session de 45 minutes. Les enfants de moins de 8 ans doivent impérativement être accompagnés par un adulte. A partir de 8 ans la présence d'un adulte est souhaitable, mais pas obligatoire. A partir de 12 ans l'usager peut venir seul.

Tous les titres présents sur la console sont téléchargés en version dématérialisée, il n'est donc pas nécessaire de faire intervenir un bibliothécaire pour changer de jeu, et il n'y a pas besoin d'accèder physiquement à la console.



To manage this, you have been asked to implement a censorship algorithm. You will be given the fan letter `text` and a list of `forbiddenWords`. Your algorithm should replace all occurrences of the forbidden words in the text with sequences of asterisks of the same length.

Be careful to censor only words, no one want to see `"classic"` spelled as `"cl***ic"`.

**Example**

For text = "The cat does not like the fire" and
forbiddenWords = ["cat","fire"], the output should be
`CensorThis(text, forbiddenWords) = "The *** does not like the ****".

* **[input] string text**

Text to censor, composed of mixed case English words separated by a single whitespace character each.

* **[input] array.string forbiddenWords**

The list of words to censor, all in lowercase.

* **[output] string**

The censored text. Its length should be the same as the length of text.

**Solution:**

```python
def CensorThis(text, forbiddenWords):
  return ' '.join([ t.replace(t, "*" * len(t)) if t.lower() in forbiddenWords else t for t in text.split() ])
```

**Test 1**

```
text: "The cat does not like the fire"
forbiddenWords: ["cat", "fire"]
Expected Output: "The *** does not like the ****"
```

**Test 2**

```
text: "The cat does not like the therapy"
forbiddenWords: ["the",  "like"]
Expected Output: "*** cat does not **** *** therapy"
```

**Test 3**

```
text: "Python is the BEST programming language and LOLCODE is the Worst"
forbiddenWords: ["worst", "best"]
Expected Output: "Python is the **** programming language and LOLCODE is the *****"
```

**Test 4**

```
text: "A bald eagle is a worthy adversary"
forbiddenWords: ["bald", "a"]
Expected Output: "* **** eagle is * worthy adversary"
```

**Test 5**

```
text: "The MAGIC words are fiz buzz and plaf"
forbiddenWords: []
Expected Output: "The MAGIC words are fiz buzz and plaf"
```

**Test 6**

```
text: "The MAGIC words are fiz buzz and plaf"
forbiddenWords: ["fluzz", "z", "ping", "narf", "tedd", "troz", "zort"]
Expected Output: "The MAGIC words are fiz buzz and plaf"
```

Thanks to **GOD**.
