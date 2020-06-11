# ISO 639 Databases

This repository is borne out of a need for a singular database of languages mapped to their ISO 639-1 and ISO 639-3 codes with their native name ("autonym") listed against their tags.

This database has been extended to include tables for resolving default ISO 15924 scripts for a given ISO 639 tag, and a table for resolving locales to LCIDs for Microsoft Windows and Microsoft Office-related localisation efforts.

## ISO 639 Autonyms - iso639-autonyms.tsv

While the data has initially been generated from standard sources, contributions are welcomed for any overly-anglicised names (those not using the native character set of the language) or those languages with name variants that have not been included.

### Interpretation

`tag3` and `tag1` columns represent the ISO 639-3 and -1 tags respectively. The `name` field is the "most recognisable" form of the language name, typically in English, to be used as a fallback where an autonym is not available.

The `autonym` field is the name of the language *in* that language. If this field is blank, it means that there is no confirmed autonym for this language in this database and you may use the `name` field as a fallback.

An `autonym` being blank does not necessarily indicate that the `name` field represents the autonym. In the case where they are the same, they should be listed in both columns.

### Sources

Here are the currently utilised sources by this table:

- `cldr` - [Unicode Common Locale Data Repository](http://cldr.unicode.org/)
- `ethnologue` - [Ethnologue](https://www.ethnologue.com/), only autonyms where specified.
- `iso639-3` - [ISO 639-3](http://www.sil.org/iso639-3/), reference language names only.
- `github` - [This repository](https://github.com/bbqsrc/iso639-databases)

## ISO 639 Default Script (ISO 15924) - iso639-default-script.tsv

### Interpretation

`tag3` and `tag1` columns represent the ISO 639-3 and -1 tags respectively.

The `script` field is the most likely valid ISO 15924 script given no more context than just simply the ISO 639 tag. An example case is `crk`, which nominally exists in both `Latn` and `Cans` forms, where software should reasonable expect that `crk` with no other context to be considered to be `Latn` by default.

### Sources

Here are the currently utilised sources by this table:

- `cldr` - [Unicode Common Locale Data Repository](http://cldr.unicode.org/)
- `giellatekno` - [Giellatekno](https://github.com/giellalt)
- `github` - [This repository](https://github.com/bbqsrc/iso639-databases)

## ISO 639 Microsoft Office LCIDs - iso639-default-script.tsv

The LCIDs used in this table are defined by [MS-OE376: 2.1.1906 Part 4 Section 7.6.2.39, LCID (Locale ID)](https://docs.microsoft.com/en-us/openspecs/office_standards/ms-oe376/6c085406-a698-4e12-9d4d-c3b0ee3dbc4a).

### Interpretation

`tag3` and `tag1` columns represent the ISO 639-3 and -1 tags respectively.

In effect, if a field is blank, it indicates that in BCP47 form, that segment should not be included to be equal to the given LCID. For example, `ar` is `1025`, while `ar-AE` is 14337.

# License

Databases in many countries do not attract intellectual property rights, and where they do it, they very rarely attract copyright due to the raw and inexpressive nature of the data. However, to alleviate doubt, this data is being published by a resident of Sweden where sui generis database rights do not apply to non-EU datasets. CLDR and Ethnologue are both datasets published in the US, where database rights also do not apply.

However, for those who have annoying and immovable legal teams and want to use this in a product, the dataset is licensed under the Creative Commons Zero 1.0 license.

# Contributing

Any contributions to this repository are on the condition that the contributor relinquishes all database rights, copyrights and all other intellectual property rights or claims to the contribution.

Mark the source as `github` in the data.