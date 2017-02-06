# [Newseum](https://devpost.com/software/newseum) - _connecting art with current events_
## Inspiration
We identified our common interests in media and art history, and wanted to find a way to connect them. How might we use art as an entryway to contemporary issues? How might we explore the correlation between breaking news and historical art? These are questions we aimed to answer, all while emphasizing the value and relevance of art history today.

## What it does
The site displays a set of images from the Harvard Art Museum API, and when users select a piece, it displays a thematically similar current events news headline. We wanted to make browsing the news akin to browsing an art gallery.

## How we built it
This site pulls top stories from Bing using [Microsoft's Bing News Search API](https://www.microsoft.com/cognitive-services/en-us/bing-news-search-api) and generates keywords from the stories using [Microsoft's Text Analytics API](https://www.microsoft.com/cognitive-services/en-us/text-analytics-api) and then uses those keywords to displays a set of images from the [Harvard Art Museum API](http://www.harvardartmuseums.org/collections/api). Once we gathered this information, we built this site with [Polymer](https://www.polymer-project.org/1.0/) to pair an image with the most thematically similar headline.

## Setup

#### Prerequisites
First, install [Polymer CLI](https://github.com/Polymer/polymer-cli) using
[npm](https://www.npmjs.com) (we assume you have pre-installed [node.js](https://nodejs.org)).

    npm install -g polymer-cli

#### Start the development server

This command serves the app at `http://localhost:8080` and provides basic URL
routing for the app:

    polymer serve --open

#### Build

This command performs HTML, CSS, and JS minification on the application
dependencies, and generates a service-worker.js file with code to pre-cache the
dependencies based on the entrypoint and fragments specified in `polymer.json`.
The minified files are output to the `build/unbundled` folder, and are suitable
for serving from a HTTP/2+Push compatible server.

In addition the command also creates a fallback `build/bundled` folder,
generated using fragment bundling, suitable for serving from non
H2/push-compatible servers or to clients that do not support H2/Push.

    polymer build

### Preview the build

This command serves the minified version of the app at `http://localhost:8080`
in an unbundled state, as it would be served by a push-compatible server:

    polymer serve build/unbundled

This command serves the minified version of the app at `http://localhost:8080`
generated using fragment bundling:

    polymer serve build/bundled

