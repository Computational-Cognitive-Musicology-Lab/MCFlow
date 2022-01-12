# CoCoPops/MCFlow/Humdrum

This folder contains the MCFlow data itself, in 124 separate [humdrum-syntax](https://www.humdrum.org/guide/ch05/) files with a `.rap` extension.
This files use a unique combination of local interpretations to represent rap flow.


## Humdrum spines


The most detailed account of the MCFlow data representation can be found in [Nat's disseration](https://etd.ohiolink.edu/apexprod/rws_etd/send_file/send?accession=osu1461250949&disposition=inline).
In general, each data record in each `.rap` transcription represents one syllable from a rapped verse (no choruses or other sections) of a commercial hip-hop song.

However a brief description is presented here:

Each `.rap` file contains eight data spines: `**recip`, `**stress`, `**tone`, `**break`, `**rhyme`, `**ipa`, `**lyrics`, and `**hype`.

### recip

`**recip` is the standard "reciprocal" approach to indicating rhythmic durations in humdrum (including `**kern`). However, rather than using ties, we use Crag Sapps `n%d` notation to represent duration values that can't be represented by a single token in traditional notation/`**recip`.
For example, the token `8%5` indicates the reciprocal of $\frac{8}{5}$, e.g., $\frac{1}{\frac{8}{5}} = \frac{5}{8}$---five eighth notes!
In general, MCFlow `.rap` transcriptions *never* use "tied" notes---even in cases where rhythmic values cross barlines.
This assures that each row always corresponds to one syllable.


### stress

Syllable stress is indicated here, as either `0` (unstressed) or `1`.
This spine attempts to capture (very roughly) both lexical and prosodic stress.

---

A few transcriptions may currently include a few (experimental) stress transcriptions, which differentiate three-levels (`0`, `1`, `2`) of stress.

### tone

This spine is, unfortunately, empty in nearly all files.
This is an experiment (still under development) in representing important pitch contours in the delivery.
The most complete example, so far, is `NotoriousBIG_BigPoppa.rap`.

### break

The `**break` indicates prosodic breaks in the flow in five levels.
This representation is inspired by the [ToBI](https://www.ling.ohio-state.edu/research/phonetics/E_ToBI/) "break" tier.

A number from `1` to `5` marks the beginning of a prosodic phrase.
Level `3` is (generally) used to indicate the most obvious, "main" phrases in the flow, with level `2` used in indicate "sub-phrases."
Level `1` (used sparingly) indicates even weaker prosodic boundaries.
Finally, levels `4` and `5` are used to indicate really strong "breaks" in the prosody: e.g., the beginning of a verse or a place where the emcee dramatically changes their pitch register or timbre.

### rhyme

### ipa

An [IPA](https://en.wikipedia.org/wiki/International_Phonetic_Alphabet) representation of each syllables' pronunciation.
This IPA was originally generated automatically using pronunciation dictionaries, but has been manually corrected to represent the emcee's actual delivery.

However, WARNING: the level of detail in the `**ipa` spine is definitely not consistent in all files.


### lyrics

The lyrics in standard English orthography.
Since the `**ipa` captures pronunciation, note that words are spelled "correctly" regardless of pronunciation.
Punctuation is used to indicate syntactic boundaries, however the full system of syntactic annotation defined in my dissertation was never fully implemented, unfortunately.


### hype

This spine is used (in some tracks) to indicate notable "hype"---secondary vocal parts that exchange or reinforce the main vocal.

