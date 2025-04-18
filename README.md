# Braacket Bulk Add

Bulk import tournaments into [Braacket](https://braacket.com). Supports both Challonge and Start.gg brackets.

There is no Braacket API, so this automates a headless browser that clicks through adding tournaments. It takes about 40 seconds per tournament.

## Install

```
npm install
```

### Dependencies

* [Node.js](https://nodejs.org/en)

* [Puppeteer](https://pptr.dev/) - Used to automate a browser. It's recommended to use the following when in the repository directory when installing:

```
npm i puppeteer-core
```

## Usage

Fill out `config/default.json` with your Braacket credentials and league name (this is found in the braacket URL at braacket.com/league/**LEAGUE NAME**), and then run one of the following:.

```
node braacket-bulk-add.js FILE
```

```
node braacket-bulk-add-no-player-import.js FILE
```

Where `FILE` is a newline-separated list of tournament URLs. For start.gg events, be sure to include the `EVENT_ID` in the URL list. The `braacket-bulk-add-no-player-import.js` simply does not automatically import and match players to the database, as braacket's automated name picking can be a bit unreliable.

### challonge-tourneys.js

The `challonge-tourneys.js` script can be used to get a list of all
tournaments created by a Challonge organization.