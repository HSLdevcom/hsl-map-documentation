HSL Map project
===

This is a collection repository for links and general documentation about all projects belonging to the Map project.

Projects and apps
---

A list of all current and relevant repositories under the map project umbrella. Each repository includes more detailed documentation.

- [hsl-map-style](https://github.com/HSLdevcom/hsl-map-style) - the Mapbox-compatible vector style for all HSL maps. Used in most other apps.
- [hsl-map-server](https://github.com/HSLdevcom/hsl-map-server) - Tessera server that hosts different types of tiles (vector, raster). The server is currently hosted by the Reittiopas team, and this server is responsible for hosting map tiles for all background maps used by HSL.
- [hsl-map-publisher](https://github.com/HSLdevcom/hsl-map-publisher) - the backend component of the stop poster generator app. Also includes the poster React app and poster parts as SVG files.
- [hsl-map-publisher-ui](https://github.com/HSLdevcom/hsl-map-publisher-ui) - the frontend component of the stop poster generator app.
- [hsl-map-generator-ui](https://github.com/HSLdevcom/hsl-map-generator-ui) - an UI for generating static map images. Essentially a frontend for hsl-map-generator-server.
- [hsl-map-generator-server](https://github.com/HSLdevcom/hsl-map-generator-server) - the server that generates map images with HSL's map style. Used for stop posters and station maps.
- [hsl-map-web-ui](https://github.com/HSLdevcom/hsl-map-web-ui) - also known as "kuljettajaohje", it's a relatively simple map app that shows all current HSL routes.
- [hsl-map-deployer](https://github.com/HSLdevcom/hsl-map-deployer) - contains the docker-compose and ngnix configs that are deployed to the dev and prod servers. All changes to these configs should go through PRs to this repository.
- [hsl-route-map-poc](https://github.com/HSLdevcom/hsl-route-map-poc) - a simple map app that shows all HSL's routes.
- [jore-graphql](https://github.com/HSLdevcom/jore-graphql) - a repository containing the Dockerfile that builds the Postgraphile-powered JORE GraphQL API.
- [jore-graphql-import](https://github.com/HSLdevcom/jore-graphql-import) - the data importer for the JORE GraphQL API. Contains the schema for the PostgreSQL database as well as SQL functions and data import logic. It runs from a Docker container that automatically downloads the newest JORE export and imports it into the jore-graphql PostgreSQL database, _overwriting_ the previous data.
- [jore-geometry-matcher](https://github.com/HSLdevcom/jore-geometry-matcher) - this should be executed after running `jore-graphql-import` to smoothen out the routes and match them to map geometry.
- [jore-history-graphql](https://github.com/HSLdevcom/jore-history-graphql) - a separate `jore-graphql` instance that contains historical JORE data. Uses a modified importer that does not overwrite data. Used by the Transitlog project.
- [jore-history-graphql-import](https://github.com/HSLdevcom/jore-history-graphql-import) - a modified version of `jore-graphql-import` that does not overwrite previous data when importing. Used for displaying historical route and stop data in the Transitlog project.
- [hsl-routemap-server](https://github.com/HSLdevcom/hsl-routemap-server) - a spin-off project from the stop poster project for  generating route maps. This is the server component.
- [osm2vectortiles](https://github.com/HSLdevcom/osm2vectortiles) - while we are blocked from upgrading to OpenMapTiles (for various reasons and working on it), we have to use this library for generating vector tiles from OSM data.
- [jore-tileserver](https://github.com/HSLdevcom/jore-tileserver) - Jore stops and routes as vector tiles.
- [tilelive-hsl-ticket-sale](https://github.com/HSLdevcom/tilelive-hsl-ticket-sales) - serializes ticket sales vector tiles to protobufs.
- [tilelive-otp-citybikes](https://github.com/HSLdevcom/tilelive-otp-citybikes) - serializes city bike vector tiles to protobufs.
- [tilelive-otp-routes](https://github.com/HSLdevcom/tilelive-otp-routes) - serializes otp routes to protobufs.
- [pymapmatch](https://github.com/HSLdevcom/pymapmatch) - forked helper module used in the geography matcher.

### Unreleased projects

These projects are still being worked on and are not yet ready for primetime.

- [hsl-stop-info](https://github.com/HSLdevcom/hsl-stop-info) - a replacement for the ["Stop tag page"](http://tag.hsl.fi/tag/16682?a) using GatsbyJS and aiming to be a lot more useful.
- [map-reports](https://github.com/HSLdevcom/map-reports) - a tool for managing reports about OSM faults and validating OSM data. Unfinished and will be moved out of the Map project.
- [hsl-map-validator](https://github.com/HSLdevcom/hsl-map-validator)

### Need investigation what these are

- [hsl-map-site](https://github.com/HSLdevcom/hsl-map-site) - the working theory is that this redirects from a stop URL to the route planner.

### Deprecated or unused projects

This is a list of deprecated or otherwise older or unused projects that were started by the Map project.

- [tilelive-gl](https://github.com/HSLdevcom/tilelive-gl) - a fork of another project called tilelive-gl. This was used until recently in the map-generator-server, but it is unmaintained and requires Node v6. Mapbox-gl-native should be used directly instead.
- [hsl-ticket-zone-map](https://github.com/HSLdevcom/hsl-ticket-zone-map) - a very simple embeddable map that shows the new ticket zones that will come into effect in 2019. Superseded by the zones showing up in the journey planner (Digitransit).
- [tile-merge-stream](https://github.com/HSLdevcom/tile-merge-stream) - helper module. Not used as far as we know.
- [map-utils](https://github.com/HSLdevcom/map-utils) - Python map utils and a stop query in Javascript. Unused as far as we know.

URLs and endpoints
---

These are the most important URL's and endpoints we use in the map project. Consult the readme of the specific project you are working on for more detailed information.

- [http://kartat.hsl.fi](http://kartat.hsl.fi) - this is the production server. The base url will redirect to hsl.fi, so you need to append the correct subdirectory where the app that you want to access lives.
- [https://dev-kartat.hsldev.com](https://dev-kartat.hsldev.com) - this is the development server. Do not expect it or any apps running on it to be available at any time, it is used for testing things that are in active development. The base url also redirects to hsl.fi on this server, so be sure to append the subdirectory of the project that you want to access.
- [/kuljettaja](http://kartat.hsl.fi/kuljettaja/) - the driver instruction app, or "kuljettajaohje", lives here. Project: [hsl-map-web-ui](https://github.com/HSLdevcom/hsl-map-web-ui).
- [/kartta](http://kartat.hsl.fi/kartta/) - the url for the map generator UI. Project: [hsl-map-generator-ui](https://github.com/HSLdevcom/hsl-map-generator-ui).
- [/generateImage](http://kartat.hsl.fi/generateImage) - the POST endpoint for the map generator server. Check projects that use it for usage, like generator-ui and publisher. Project: [hsl-map-generator-server](https://github.com/HSLdevcom/hsl-map-generator-server).
- [/linjakartta](http://kartat.hsl.fi/linjakartta/) - where you can view the simple route map. Project: [hsl-route-map-poc](https://github.com/HSLdevcom/hsl-route-map-poc).
- [/julkaisin](http://kartat.hsl.fi/julkaisin/) - this is the UI of the service that generates stop posters.
- [/jore/graphql](http://kartat.hsl.fi/jore/graphql) - the graphQL endpoint for the JORE API. Contains a subset of data from the JORE database. POST only. Replace the last segment with `/graphiql` to access the Graph*i*QL documentation. Projects: [jore-graphql](https://github.com/HSLdevcom/jore-graphql) and [jore-graphql-import](https://github.com/HSLdevcom/jore-graphql-import).
- [/jore-history/graphql (dev)](https://dev-kartat.hsldev.com/jore-history/graphql) - the graphQL endpoint for the JORE _history_ API. Contains historical data from the JORE database going back a year or so. POST only. Replace the last segment with `/graphiql` to access the Graph*i*QL documentation. Projects: [jore-history-graphql](https://github.com/HSLdevcom/jore-history-graphql) and [jore-history-graphql-import](https://github.com/HSLdevcom/jore-history-graphql-import).
