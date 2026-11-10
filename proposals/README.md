# Deontic completion proposal

[2026-11-08-deontic-completion.ttl](2026-11-08-deontic-completion.ttl) renders
proposal `deontic-completion-2026-11-08` from the Agents' Lawful Good gap registry,
including its approved 2026-11-10 restructuring. It proposes 19 new Canon classes,
14 added parents for existing classes, and translations for the existing Condition
class. It uses the Canon's base namespace and only local names supplied by the
proposal YAML.

## Why these additions

Agents' Lawful Good resolves conflicts between norms from international,
religious, national, state, local, private, and personal authorities. That requires
a full set of deontic positions and rules for relating them. FOLIO already models
obligation, prohibition, permission, right, authority, waiver, exception,
compliance, and violation. The proposal fills gaps around conditions, Hohfeldian
immunity, recommendation and discouragement, justification versus excuse,
normative consequences, priority rules, and strong versus weak permission.
The Canon already has Condition but lacks Waiver and Dispensation, canon law's
own mechanism for relaxing a law in a particular case.

The revised structure groups concepts under Deontic Modality, Normative Position,
Norm Defeater, and Normative Outcome. Canons of Construction sits under the
Canon's Normative Concepts, with Norm Priority and the three lex rules below it.
Justification and Excuse also sit under Litigation Defenses, linking the existing
defense classes to the new concepts.

## Maintainer workflow and FOLIO alignment

These are proposal files only; `sources/` and all ontology exports are untouched.
WebProtégé remains the source of truth. Maintainers apply accepted classes,
added parents, and translations in WebProtégé; the next ontology export closes
the loop by bringing those accepted changes into this repository.

The same local names go to FOLIO in a parallel PR. FOLIO already has Waiver,
while Condition is new there and Dispensation is Canon-only. FOLIO places Canons
of Construction under Objectives; the Canon uses Normative Concepts instead.
All new classes carry the ten FOLIO-language translations, plus the Latin and
Italian translations supplied by the YAML. Canon examples precede general
examples, and `rdfs:seeAlso` references are included only when present in the
current Canon export.

## New classes

IRIs below use the `@base` declared in the Turtle file.

| Class                  | IRI                         | Parent(s)                                                                                      |
| ---------------------- | --------------------------- | ---------------------------------------------------------------------------------------------- |
| Deontic Modality       | `<R2PCCd0Cf7TiP6IxGyrz7Ta>` | Deontic Specification (`<RClhbl4E1TJp9LygIXewIhn>`)                                            |
| Recommendation         | `<RjMjN3NkaSRnPZw8vlwlcY>`  | Deontic Modality (`<R2PCCd0Cf7TiP6IxGyrz7Ta>`)                                                 |
| Discouragement         | `<R29CRZT3JnJ8AmB5EFfSTp5>` | Deontic Modality (`<R2PCCd0Cf7TiP6IxGyrz7Ta>`)                                                 |
| Normative Position     | `<R2TPb1dgPO42w8tLZkDdqCP>` | Deontic Specification (`<RClhbl4E1TJp9LygIXewIhn>`)                                            |
| Normative Immunity     | `<R1Xlw46piQQyK0QeaoR8pI3>` | Normative Position (`<R2TPb1dgPO42w8tLZkDdqCP>`)                                               |
| Norm Defeater          | `<R3p22AB0XXbb1kWWNeQWRDD>` | Deontic Specification (`<RClhbl4E1TJp9LygIXewIhn>`)                                            |
| Justification          | `<R1zBn1lrGhO9ZNTlHKf0gB>`  | Norm Defeater (`<R3p22AB0XXbb1kWWNeQWRDD>`); Litigation Defenses (`<R7vJPxcT40MjEfNZkBK1tKH>`) |
| Excuse                 | `<R2Cfmjnr5HGhJlZCMmlCyw0>` | Norm Defeater (`<R3p22AB0XXbb1kWWNeQWRDD>`); Litigation Defenses (`<R7vJPxcT40MjEfNZkBK1tKH>`) |
| Normative Outcome      | `<R3oECS9Y8el0TByDj3bapCz>` | Deontic Specification (`<RClhbl4E1TJp9LygIXewIhn>`)                                            |
| Normative Consequence  | `<R3eE7scihp6mUkGxxTTmI6l>` | Normative Outcome (`<R3oECS9Y8el0TByDj3bapCz>`)                                                |
| Strong Permission      | `<R30DEF9ukwQ52s1M0TM3rrK>` | Permission (`<RCurUksxnjgPwYWpCSq0xPI>`)                                                       |
| Weak Permission        | `<R19dUa6OpptxedDqxi9cMOC>` | Permission (`<RCurUksxnjgPwYWpCSq0xPI>`)                                                       |
| Canons of Construction | `<RbR0g0g0FweCujfDBLnpLi>`  | Normative Concepts (e.g., Ethics, Morals, Laws) (`<RDQC6BrYjcS3V0gZcYzqc8O>`)                  |
| Norm Priority          | `<R1VeCUx7ApksL6aQiE1BjFN>` | Canons of Construction (`<RbR0g0g0FweCujfDBLnpLi>`)                                            |
| Lex Superior           | `<R1mB8KZFWjVdadUCG6mTXeX>` | Norm Priority (`<R1VeCUx7ApksL6aQiE1BjFN>`)                                                    |
| Lex Specialis          | `<R3OGtuu1PDM3jR07sv9xc0N>` | Norm Priority (`<R1VeCUx7ApksL6aQiE1BjFN>`)                                                    |
| Lex Posterior          | `<R2J1C02SzYxcRUGuN0V8gJ5>` | Norm Priority (`<R1VeCUx7ApksL6aQiE1BjFN>`)                                                    |
| Waiver                 | `<R9CBXdybYDztLBRNDNJl0W>`  | Norm Defeater (`<R3p22AB0XXbb1kWWNeQWRDD>`)                                                    |
| Dispensation           | `<R2mVIpzkOdrbXKdRD71wKYs>` | Exception (`<RCdJXw1Ml7DIBqmouWarZm2>`)                                                        |

## Added parents for existing classes

Each row adds one `rdfs:subClassOf` triple. All existing parents are retained;
none is removed. Retiring an old direct parent would require a later,
separately reviewed change. The informational Authority label divergence in the
YAML requires no label change.

| Existing class           | IRI                         | Added parent                                     |
| ------------------------ | --------------------------- | ------------------------------------------------ |
| Obligation               | `<RDtFkLR3v97fran5zQ3ugao>` | Deontic Modality (`<R2PCCd0Cf7TiP6IxGyrz7Ta>`)   |
| Prohibition              | `<RCqqI0SLTxsE8Z2rCu7KOXm>` | Deontic Modality (`<R2PCCd0Cf7TiP6IxGyrz7Ta>`)   |
| Permission               | `<RCurUksxnjgPwYWpCSq0xPI>` | Deontic Modality (`<R2PCCd0Cf7TiP6IxGyrz7Ta>`)   |
| Right                    | `<RmCCZU8GS7O8920pkDipw7>`  | Normative Position (`<R2TPb1dgPO42w8tLZkDdqCP>`) |
| Authority                | `<R9ikrznaQwm4RUsMzP9KXFR>` | Normative Position (`<R2TPb1dgPO42w8tLZkDdqCP>`) |
| Exception                | `<RCdJXw1Ml7DIBqmouWarZm2>` | Norm Defeater (`<R3p22AB0XXbb1kWWNeQWRDD>`)      |
| Compliance               | `<RCZwssbqfmu0Lds0LPDV34F>` | Normative Outcome (`<R3oECS9Y8el0TByDj3bapCz>`)  |
| Violation                | `<RDsDXHKUsZoJfz87jnz7zjj>` | Normative Outcome (`<R3oECS9Y8el0TByDj3bapCz>`)  |
| Self-Defense             | `<RDLANHrFj8nfaiNIalX9Ndx>` | Justification (`<R1zBn1lrGhO9ZNTlHKf0gB>`)       |
| Necessity of Trespass    | `<RbmgMZH2v4CykER8m2CutA>`  | Justification (`<R1zBn1lrGhO9ZNTlHKf0gB>`)       |
| Duress                   | `<RDDmzFedWDpLN1Xtuy3FiLh>` | Excuse (`<R2Cfmjnr5HGhJlZCMmlCyw0>`)             |
| Insanity Defense         | `<Rss8FJTgnn6V9FuSLxl90u>`  | Excuse (`<R2Cfmjnr5HGhJlZCMmlCyw0>`)             |
| Involuntary Intoxication | `<R84WSMY4efMvESQh729h2Kp>` | Excuse (`<R2Cfmjnr5HGhJlZCMmlCyw0>`)             |
| Lack of Capacity         | `<R9kRdeC3m6NEz0zOxotAueb>` | Excuse (`<R2Cfmjnr5HGhJlZCMmlCyw0>`)             |

## Translation additions to Condition

| Existing class | IRI                         | Existing parents (retained)        |
| -------------- | --------------------------- | ---------------------------------- |
| Condition      | `<R8nMXQ6k46QexNTIdUvvr4k>` | Proposition; Deontic Specification |

Only `skos:altLabel` triples are proposed for Condition: the ten FOLIO languages
(`en-gb`, `es-es`, `es-mx`, `fr-fr`, `de-de`, `pt-br`, `he-il`, `hi-in`, `ja-jp`,
`zh-cn`), plus Latin (`la`) and Italian (`it`). Any language already present in
the Canon is skipped; the current export has none of these tagged altLabels.
Condition's existing labels, definition, examples, and parents remain intact.
The YAML's other translation backfills and corrections are outside this Canon
proposal's three sections.
