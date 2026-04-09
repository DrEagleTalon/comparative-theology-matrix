# Comparative Theology Matrix

An interactive reference tool mapping doctrinal positions across various Christian denominations and Sunni Islam on 110+ belief topics. Built for interfaith dialogue, da'wah preparation, and comparative religion study with a focus on American faith communities.

---

## What this is

This project started as a da'wah and interfaith dialogue preparation tool. The goal is to map where different Christian traditions agree, disagree, and overlap with each other and with Sunni Islam — not as a definitive theological verdict, but as a research aid for honest, informed conversation.

Every belief is scored on a scale:

| Score | Meaning |
| ----- | --------- |
| +2 | Strongly affirms |
| +1 | Affirms |
| 0 | Divided or middle ground |
| -1 | Negates |
| -2 | Strongly negates |
| — | Not applicable to this tradition |

Scores are drawn from official confessions, catechisms, and recognized community standards. Where a denomination has no binding official position, common practice is used and noted. This is a research tool, not a fatwa, and not a substitute for direct engagement with scholars or community representatives.

---

## Files in this repo

```text
theology_matrix.html    Primary tool — open in any browser, no installs needed
theology_matrix.xlsx    Raw data backup — three sheets, same data, color coded
README.md               This file
```

---

## How to use the HTML file

**Simplest — double-click it.** It opens in Chrome, Firefox, or Edge and runs fully offline with no internet connection needed after download.

**In VS Code with live editing:**

1. Install the [Live Server extension](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) by Ritwick Dey
2. Open VS Code, go to File → Open Folder, select the folder this repo is in
3. Right-click `theology_matrix.html` in the sidebar
4. Click "Open with Live Server"
5. Your browser opens the file and auto-refreshes every time you save a change

---

## How to use the sorting and filtering features

The HTML tool includes powerful sorting and filtering options to help you explore the data:

### Filtering

- **Search Beliefs**: Use the search box to filter beliefs by text or category.
- **Filter by Category**: Click category buttons (All, Theology, Christology, etc.) to show only beliefs in that category.
- **Filter by Tradition**: Click tradition buttons to show/hide specific denominations or religious groups.

### Sorting Rows

- **By Tradition Scores**: Click any denomination header to sort rows by that tradition's doctrinal scores (descending → ascending → unsorted).
- **By Category**: Click the "Category" header to sort rows alphabetically by category (ascending → descending → unsorted).
- **By Belief Text**: Click the "Belief / doctrine" header to sort rows alphabetically by belief description (ascending → descending → unsorted).

### Clearing Sorts

- **Clear Sort Button**: Click the "Clear Sort" button next to the search box to instantly reset all sorting and return to the default view.

### Future Sorting Features

- **Column Sorting by Belief**: Planned feature to reorder denomination columns by their scores for a specific belief (by clicking the belief row header). Currently commented out but will be re-enabled in a future update.

---

## How to add a new belief row

Open `theology_matrix.html` in VS Code. Press `Ctrl+F` and search for:

```js
// ── ADD NEW BELIEFS BELOW
```

You will land directly on the data section. Copy any existing line and paste a new one. The format is:

```js
["Category", "Your belief text here", [RCC, SBC, UMC, AG, LCMS, PCA, JW, AMI, MEN, SDA, LDS, ISL]],
```

The 12 numbers correspond to the 12 traditions in this order:

```text
RCC  = Roman Catholic
SBC  = Southern Baptist Convention
UMC  = United Methodist Church (post-2024)
AG   = Assemblies of God
LCMS = Lutheran Church — Missouri Synod
PCA  = Presbyterian Church in America
JW   = Jehovah's Witnesses
AMI  = Old Order Amish (Elkhart-LaGrange settlement)
MEN  = Conservative Mennonite (Goshen/Elkhart area)
SDA  = Seventh-day Adventist
LDS  = Latter-day Saints
ISL  = Sunni Islam (mainstream traditional position)
```

Use `null` instead of a number if the belief category is not applicable to that tradition.

Save the file. If Live Server is running, the browser updates immediately.

---

## How to add a new denomination

Search for:

```js
// ── ADD NEW DENOMINATIONS BELOW
```

Add a new entry to the `DENOMS` array following the existing pattern:

```js
{id:"XXX", name:"Full Denomination Name", broad:"Broad Category"},
```

Then go to every belief row in the `BELIEFS` array and add one score at the end of its score list, in the same position as your new denomination.

---

## How to add beliefs using the in app form

The HTML file has a "+ Add belief" button in the toolbar. This opens a form where you can add a belief and scores without touching any code. Entries added this way are saved in your browser's local storage and persist between sessions. To make them permanent in the file, copy the entry into the `BELIEFS` data section in the code.

---

## Categories currently covered

- Theology (nature of God, Trinity, predestination)
- Christology (Jesus — divinity, resurrection, return, atonement)
- Soteriology (salvation — faith, works, grace, baptism, eternal security)
- Scripture (inerrancy, sola scriptura, continuing revelation, tahrif)
- Sacraments (Eucharist, baptism, confirmation, confession, foot-washing)
- Ecclesiology (church governance, women's ordination, apostolic succession)
- Eschatology (millennium, rapture, hell, soul sleep, purgatory, resurrection)
- Mariology (Theotokos, perpetual virginity, veneration, assumption)
- Ethics — Family (abortion, contraception, homosexuality, marriage, divorce, polygamy, modesty)
- Ethics — Substance (alcohol, tobacco, pork, coffee, gambling, usury)
- Worship (liturgy, charismatic gifts, tongues, musical instruments, fasting, prayer direction)
- Social-Political (pacifism, just war, political participation, technology, mutual aid, capital punishment)
- Interfaith (exclusivism, tahrif, covenantal status of Jews, Muhammad as prophet)

---

## Traditions covered

| ID | Full Name | Broad Category |
| --- | --- | --- |
| RCC | Roman Catholic Church | Catholic |
| SBC | Southern Baptist Convention | Protestant — Baptist |
| UMC | United Methodist Church (post-2024) | Protestant — Methodist |
| AG | Assemblies of God | Protestant — Pentecostal |
| LCMS | Lutheran Church — Missouri Synod | Protestant — Lutheran |
| PCA | Presbyterian Church in America | Protestant — Reformed |
| JW | Jehovah's Witnesses | Restorationist |
| AMI | Old Order Amish (Elkhart-LaGrange) | Anabaptist |
| MEN | Conservative Mennonite (Goshen/Elkhart) | Anabaptist |
| SDA | Seventh-day Adventist | Adventist |
| LDS | Latter-day Saints | LDS |
| ISL | Sunni Islam | Islam |

---

## Notes on methodology

Scores reflect the official doctrinal position of each tradition where one exists — drawn from confessions, catechisms, council documents, and denominational statements. For the Old Order Amish and Conservative Mennonite, scores reflect actually practiced community standards in the Elkhart-LaGrange and Goshen settlements specifically, not general Anabaptist theology in the abstract, since these communities vary significantly by region and district.

The UMC scores reflect the post-General Conference 2024 position following the removal of the incompatibility language on homosexuality and the lifting of the ban on LGBTQ ordination and same-sex marriage.

Islam is included as one of the 12 columns — not as the standard everything is measured against, but as a full participant in the comparison. The Islam Similarity tab in the HTML tool ranks denominations by doctrinal proximity to Sunni Islam as a practical da'wah reference, not as a theological claim.

Where genuine internal disagreement exists within a denomination on a topic, a 0 is used rather than falsely representing one faction's position as the whole tradition's position.

---

## Context

**Scope:** This tool is designed for interfaith dialogue, comparative religion study, and da'wah preparation across **American faith communities**. It can be applied and adapted to any region or context where these traditions are present.

**Why I started here:** The initial dataset focuses on northern Indiana because that's where I am and where I see the most immediate need. This region includes one of the largest Old Order Amish settlements in the world (Elkhart and LaGrange counties), a strong Catholic presence anchored by Notre Dame in South Bend, significant Conservative Mennonite communities in the Goshen area, and a wide range of evangelical Protestant congregations. It's an ideal testing ground for mapping diverse Christian traditions alongside Islam.

**Future development:** The tool is designed to scale. If you have expertise in other regions, communities, or traditions, contributions are welcome. The framework accommodates any denomination and any number of belief topics. Denominations and scores can be added via pull request or collaboration.

---

## Changelog

All changes to this project are logged in [`CHANGELOG.txt`](./CHANGELOG.txt) in CSV format for easy parsing and version tracking. Each entry includes:

- **Date**: YYYY-MM-DD
- **Version**: Semantic versioning (e.g., 1.0.0)
- **Branch**: Git branch name where change was made
- **User**: GitHub username or contributor name
- **Description**: Summary of change (beliefs added, traditions updated, bug fixes, etc.)
- **Approved By**: Reviewer or maintainer who approved the change (if applicable)
- **Scope**: `data` (beliefs/denominations), `feature` (new functionality), `bugfix`, `docs`, or `structure`

Example:

```csv
Date,Version,Branch,User,Description,Approved By,Scope
2026-04-09,1.0.0,main,DrEagleTalon,Initial release with 12 traditions and 110+ beliefs,self,data
2026-04-10,1.1.0,dev/northern-indiana,Contributor,Added 5 new doctrinal beliefs to Eschatology,DrEagleTalon,data
```

When you commit changes on any branch, update both the README changelog section and the standalone `CHANGELOG.txt` file so that history is tracked and easily viewable.

---

## License

This data is compiled from public confessional documents and theological sources. It is provided as a reference tool for education, dialogue, and research. No claim is made that any tradition's full theology is captured in a single numeric score.
