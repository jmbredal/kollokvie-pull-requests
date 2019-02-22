# Pull requests i Hemit Systemutvikling

- John-Magne Bredal

## Introduksjon

[What's Pull Request Flow All About?]

Hva er en pull request:

- er en måte å si fra om at en feature er ferdig
- gjør det mulig å la andre se over det som er gjort før det, typisk, kommer inn i master
- består av en eller flere commits

For å bruke pull requests trenger man et verktøy som legger til rette for å diskutere og kommentere, få meldinger om oppdateringer og akseptere og merge inn endringer.

- GitHub
- [Azure DevOps](https://hemit.visualstudio.com/MRS4/)

_Mål_: bedre kodekvalitet, forhindre feil

## 1. Lag en pull request

[Review code with pull requests]

### Først - lag en feature branch

- `Branches` -> `New branch` -> `user\<user>\<branch>`
- Lag feature på vanlig måte
- Husk - man kan jobbe på flere features samtidig ved å bytte mellom grener

### Push endringene og lag pull request

- Høyreklikk -> `Push branch`
- Lag pull request ved å trykke på lenken
  - evt. høyreklikk og `Lag pull request`
  - evt. gå inn i Azure DevOps og lag derfra
- fyll inn relevant info
- assign reviewers (en eller flere)
- nå er din jobb i beste fall ferdig

## 2. Review pull request

Gjøres av andre enn de som har laget pull requesten. Alle som er satt som "Reviewer" kan gjøre dette.

- Les beskrivelse for å se hva pull requesten er om
- sjekk ut koden lokalt for å se hvordan den oppfører seg
  - høyreklikk pull request -> `Checkout source branch`
- se på diff for å se kodeendringer - gjøres i fanen `Files`
- man kommenterer ved å klikke ved siden av linjenummeret
  - `@username`, `#workItemID`, `!pullRequestId`
- kommentarer må/kan/skal (basert på policies) markeres som gått gjennom
- man velger aksept i "Approve"-dropdownen

Her kan det bli flere iterasjoner.

## 2.1 Oppdater pull request

Dersom det trengs endringer i pull requesten:

- For å oppdatere pull requesten oppdaterer man koden lokalt og pusher.
- Det er også mulig å gjøre små endringer via web-grensesnittet: `View in file explorer` -> `Edit`

## 3. Complete pull request

Når man er klar til å merge med master:

- Velg `Complete`
  - Man må bestemme seg hvem som skal gjøre dette (alle, de som reviewer)
- Slett branch
- Evt. squash (slå sammen) commits

## Branch policies

- Regler for hva utviklere kan gjøre med en gren
- F.eks. kreve pull requests, minimum reviewers, linking til work items

## Problemer med pull requests

- ~~Vanskelig~~
- ~~for mange steg~~
- Feature-branches som lever for lenge
- mye jobb for de som skal reviewe
- reviews blir ikke gjort
- premature optimization

## Feature-branch (pull request) vs trunk-based (master) workflow

[Trunk-based Development vs. Git Flow]

Et par ting som sies om måtene å arbeide på:

Feature-branch pro:

- open source (trenger kontroll meed hva som pushes)
- mange nye som skal jobbe med et system
- etablert system med etablerte rutiner

Feature-branch con:

- når man starter med et system
- når man trenger raske iterasjoner
- når det kun vil være overhead med feature-branches

Trunk based er mer eller mindre motsatt.

## Andre ting

Et par andre ting angående pull requests:

- draft pull requests - work in progress
- link work items - dersom man legger issues i Azure DevOps

## Lenker

- [Trunk-based Development vs. Git Flow]
- [Review code with pull requests]
- [What's Pull Request Flow All About?]

[Trunk-based Development vs. Git Flow]: https://codeburst.io/trunk-based-development-vs-git-flow-a0212a6cae64
[Review code with pull requests]: https://docs.microsoft.com/en-us/azure/devops/repos/git/pull-requests?view=azure-devops&tabs=new-nav
[What's Pull Request Flow All About?]: https://www.netguru.com/blog/pull-request-flow-pm-perspective#