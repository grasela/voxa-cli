## Spreadsheet interaction model structure
You can take a look at `example-interaction-model.xlsx` in the root of the repository
* Spreadsheet must contain a valid local on it's name eg. `MySkill - Intents & Utterances-en-US`. Valid Locales are (['en-US','en-GB', 'de-DE'])
* Tab for intent must be named `INTENT`
* Tab for utterances must be named `UTTERANCES` eg. `UTTERANCES_MAIN`, `UTTERANCES_HELP`
* Tab for slots must contain `LIST_OF_` eg. `LIST_OF_TERMS`.
* If your slots contains synonym add a column named synonym
* Tab for invocation name must be named `INVOCATION_NAMES`

### slots must have the following Structure

LIST_OF_TERMS | synonym
--- | ---
rain | rain
rainy day | rain
rainstorm | rain
rainfall | rain

### Utterances must have the following structure

LaunchIntent | AMAZON.YesIntent
--- | ---
LaunchIntent | AMAZON.YesIntent
start | ohh yes
give me something | yeah
put some fireworks | here we go

### Invocation names must have the following structure

invocationName | environment
--- | ---
lost in production | production
lost in development | development

### Intent must have the following structure

intent | slotType | slotName | environment
--- | --- | --- | --- |
LaunchIntent | | | |
SuperIntent | LIST_OF_REQUESTS | {request} |  |
TestIntent | LIST_OF_REQUESTS | {request} | development |

> In this case Test Intent will only be available at development interaction model

### Tabs to download should have the following structure

columnName | columnNameTwo | columnNameThree | columnNameFour
--- | --- | --- | --- |
columnName | columnNameTwo | columnNameThree | columnNameFour
itemAttr | itemAttrTwo | itemAttrThree | itemAttrFour

> it must have 2 column rows. Known bug at spreadsheet npm package
