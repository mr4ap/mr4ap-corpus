# Meaning Representation for Application Purposes (MR4AP) corpus (v0.1)

## Disclaimer

This corpus is supposed to grow in size.

## Repository contents

This repository hosts the __MR4AP__ corpus v0.1. The `files` folder contains all
the currently available JSON files. Those files present three main fields:
* `id`: the text id,
* `text`: the plain text that is annotated,
* `owl`: the corresponding OWL containing the annotations.

Here is an example for the following sentence: `Luc a mangé une pomme`.

```json
{
    "id": "00000",
    "text": "Luc a mangé une pomme",
    "owl": ":mr4ap/kb/100000004 a owl:NamedIndividual;\n  rdfs:label \"2023-03-23T09:45:11.648919675\" .\n\n:mr4ap/kb/1718136849 a owl:NamedIndividual, :mr4ap/ontology/100000001,\n    :mr4ap/ontology/Human, :Httpwwww3org200207owlNamedIndividual;\n  rdfs:label \"Luc\" .\n\n:mr4ap/ontology/100000001 a owl:NamedIndividual;\n  rdfs:label \"Masculine\" .\n\n:mr4ap/ontology/Human a owl:NamedIndividual .\n\n:Httpwwww3org200207owlNamedIndividual a owl:NamedIndividual .\n\n:mr4ap/kb/446309268 a owl:NamedIndividual, :mr4ap/ontology/Concrete,\n    :Httpwwww3org200207owlNamedIndividual;\n  :has_measureexact \"1\";\n  rdfs:label \"Pomme\", \"pomme\" .\n\n:mr4ap/ontology/Concrete a owl:NamedIndividual .\n\n:mr4ap/kb/50486795 a owl:NamedIndividual, :mr4ap/ontology/Eat,\n    :mr4ap/ontology/Event;\n  :has_agent :mr4ap/kb/1718136849;\n  :has_patient :mr4ap/kb/446309268;\n  :has_timemax :mr4ap/kb/100000004;\n  :has_aspect \"performance\";\n  :has_polarity \"Pos\";\n  rdfs:label \"mangé\" .\n\n:mr4ap/ontology/Eat a owl:NamedIndividual .\n\n:mr4ap/ontology/Event a owl:NamedIndividual ."
}
```

Each filename follows the following syntax `sentence_00000.json`.

## Corpus statistics

In this very first version, 100 short French sentences from the TaPaCo corpus 
[(Scherrer, 2020)](https://helda.helsinki.fi/bitstream/handle/10138/327739/multitatoeba_lrec2020.pdf?sequence=1)) 
are included. Below are some additional insights.

| Item   | Number |
|--------|--------|
| Sentences | 100 |
| Tokens | 534    |
| Min length | 3 |
| Max length | 12 |
| Avg length | 5.34 |

__MR4AP__'s graphs are directed graphs and are composed of nodes and relations. Each node can either be:
* an event (e.g. `eat` in _John ate an apple_),
* a state (e.g. `state` in _John is tired_),
* or a feature (e.g. `aspect`, `modality`, etc.)

Nodes can represent (named) entities. Those entities are semantically typed.

Relations link nodes to other nodes. These relations can either be:
* a thematic role (subset of VerbNet's thematic roles 
[(Schuler, 2005)](https://www.proquest.com/openview/7ca4b1b9093522a7d8089ff2e987e74e/1?pq-origsite=gscholar&cbl=18750&diss=y),
* a discursive, temporal, spatial relation tag (e.g. `Condition`, `TimeMax`, `Location`),
* or a coreference relation (`SameAs`).

Below are some additional insights.

![Roles in corpus](img/roles.jpg "Roles in corpus")

![Semantic types in corpus](img/types.jpg "Semantic types in corpus")


