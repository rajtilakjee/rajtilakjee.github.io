# Searchcraft: Because `Ctrl + F` Doesn't Scale

Every developer reaches a point where they think:

> "How hard can a search engine be?"

History has repeatedly answered that question with billion-dollar companies and decades of research.

Naturally, I ignored history.

So **Searchcraft** was born.

Not because I wanted to compete with Google (I enjoy sleeping at night). Not because Elasticsearch offended me personally. But because I realized I'd used search engines every single day without ever understanding what happened after I pressed **Enter**.

That felt... wrong.

So I decided to build one.

From scratch.

## The Rules

There were only a few rules.

* No AI magic.
* No existing search libraries.
* Build every piece myself.
* Understand every line before writing the next one.

The goal isn't to build the fastest search engine.

It's to build one where I can explain every component without waving my hands and saying "the framework handles that."

## Version 0.1.0

The first version is wonderfully underwhelming. It reads documents. It indexes them. It lets me search words. That's it.

No ranking.
No fuzzy matching.
No spell correction.
No machine learning.

Just honest software doing exactly what it's told.

## Feeding the Beast

The search engine begins by loading documents.

```python
def load_documents(folder: Path):
    for path in folder.glob("*.txt"):
        yield Document(
            id=path.stem,
            text=path.read_text(encoding="utf-8")
        )
```

Nothing fancy. Every `.txt` file becomes a document object. At this point Searchcraft knows absolutely nothing about words. It's just carrying around giant blobs of text like an exhausted librarian.

## Teaching It to Read

Raw text isn't very useful. Computers don't think in sentences. They think in tokens. So the tokenizer breaks text apart.

```python
TOKEN_PATTERN = re.compile(r"\b\w+\b")

def tokenize(text: str):
    return [
        token.lower()
        for token in TOKEN_PATTERN.findall(text)
    ]
```

This tiny function is surprisingly important.

It turns:

```
Hello, World!
```

into

```
["hello", "world"]
```

Suddenly punctuation stops getting in the way. Uppercase and lowercase become friends. Life becomes slightly less chaotic.

## The Magical Data Structure

Here's the part that made me smile. Instead of storing every document and searching through all of them every single time... we flip the relationship.

Instead of:

```
Document
 ├── words
```

we build

```
Word
 ├── documents
```

This is called an **inverted index**. Which sounds like something your chiropractor warns you about.

The code is beautifully simple.

```python
index[token].add(document.id)
```

That's it. Every word becomes a key. Every key stores the documents that contain it. So after indexing three books we might have something like:

```
dragon
 ├── dracula
 └── fantasy_notes

castle
 ├── dracula

elizabeth
 ├── pride_and_prejudice
```

Searching suddenly becomes incredibly cheap. Instead of reading every document...

...we simply ask the dictionary.

```python
results = index.get(query.lower(), set())
```

Python dictionaries are absurdly fast.

## The Command Line

I wanted Searchcraft to feel like a real tool from day one. That's why I built it as a CLI using **Typer**.

```
searchcraft index
```

Build the index.

```
searchcraft search-docs vampire
```

Search for a word.

```
Found in:

- Dracula
```

Tiny?
Absolutely.

Satisfying?
More than it has any right to be.

## Why Not Just Use Elasticsearch?

Because that's like learning how engines work by buying a Ferrari.

Useful?
Definitely.

Educational?
Not particularly.

Searchcraft exists because I wanted to understand the fundamentals first. Once you know how an inverted index works, suddenly all those enterprise search tools stop feeling like black boxes. They're just solving much harder problems.

## What's Next?

Version 0.1.0 proves one thing:

The basic engine works.

Now the interesting problems begin. The roadmap currently looks something like this:

* Store where every word appears inside a document.
* Support multi-word queries.
* Rank results instead of returning everything equally.
* Highlight matching words.
* Add phrase searching.
* Ignore common words like *the*, *and*, and *is*.
* Handle plurals and different word forms.
* Build a small web interface.
* Eventually crawl web pages instead of just local files.

Each feature sounds tiny. Each feature is almost certainly hiding three weeks of unexpected complexity. Software has a wonderful habit of doing that.

## Why I'm Writing This Series

There are countless tutorials that teach you **how** to use search engines. Far fewer explain **how search engines actually work**. Searchcraft is my excuse to learn those ideas properly. If, along the way, someone else learns why an inverted index is one of the coolest data structures ever invented that's a pretty good bonus.

Until the next post.

Hopefully I'll have taught my search engine enough new tricks that it stops behaving like a very enthusiastic dictionary.
