# HSL Map project

This is a collection repository for links and general documentation about all projects belonging to the Map project.

## Architecture and data flow [diagrams](Process%20schema/README.md)

## Projects and apps

A list of all current and relevant repositories under the map project umbrella. Each repository includes more detailed documentation.

- [hsl-map-publisher](https://github.com/HSLdevcom/hsl-map-publisher) - the backend component of the stop poster generator app. Also includes the poster React app and poster parts as SVG files. Also the base of [hsl-timetable-container](https://github.com/HSLdevcom/hsl-timetable-container) hosted by Digitransit team
- [hsl-map-publisher-ui](https://github.com/HSLdevcom/hsl-map-publisher-ui) - the frontend component of the stop poster generator app.
- [hsl-routemap-server](https://github.com/HSLdevcom/hsl-routemap-server) - a spin-off project from the stop poster project for generating route maps. This is the server component.
- [hsl-map-generator-server](https://github.com/HSLdevcom/hsl-map-generator-server) - the server that generates map images with HSL's map style. Used for stop posters and station maps.
- [hsl-map-generator-ui](https://github.com/HSLdevcom/hsl-map-generator-ui) - an UI for generating static map images. Essentially a frontend for `hsl-map-generator-server` and `hsl-routemap-server`
- [hsl-map-web-ui](https://github.com/HSLdevcom/hsl-map-web-ui) - also known as "kuljettajaohje", it's a relatively simple map app that shows all current HSL routes.
- [hsl-route-map-poc](https://github.com/HSLdevcom/hsl-route-map-poc) - a simple map app that shows all HSL's routes.
- [hsl-map-site](https://github.com/HSLdevcom/hsl-map-site) - The application redirects from a stop URL to the route planner.

- [hsl-jore-postgis](https://github.com/HSLdevcom/hsl-jore-postgis) a repository containing build scripts for PostgreSQL database for storing Jore data
- [jore-graphql-import](https://github.com/HSLdevcom/jore-graphql-import) - the data importer for the JORE GraphQL API. Contains the schema for the PostgreSQL database as well as SQL functions and data import logic. It runs from a Docker container that automatically downloads the newest JORE export and imports it into the jore-graphql PostgreSQL database, _overwriting_ the previous data.
- [jore-graphql](https://github.com/HSLdevcom/jore-graphql) - a repository containing the Dockerfile that builds the Postgraphile-powered JORE GraphQL API from `hsl-jore-postgis`.
- [jore-tileserver](https://github.com/HSLdevcom/jore-tileserver) - Jore stops and routes from `hsl-jore-postgis` as vector tiles.

- [hsl-map-style](https://github.com/HSLdevcom/hsl-map-style) - the Mapbox-compatible vector style for all HSL maps. Used in most other apps.
- [hsl-map-server](https://github.com/HSLdevcom/hsl-map-server) - Tessera server that hosts different types of tiles (vector, raster). The server is currently hosted by the Reittiopas team, and this server is responsible for hosting map tiles for all background maps used by HSL.
- [OpenMapTiles](https://github.com/HSLdevcom/OpenMapTiles) - a library for generating vector tiles from OSM data.
- [osm2vectortiles](https://github.com/HSLdevcom/osm2vectortiles) - a deprecaded library for generating vector tiles from OSM data. `OpenMapTiles` is going to replace this, but still used until old maps are closed.
- [tilelive-hsl-ticket-sale](https://github.com/HSLdevcom/tilelive-hsl-ticket-sales) - serializes ticket sales vector tiles to protobufs.
- [tilelive-hsl-parkandride](https://github.com/HSLdevcom/tilelive-hsl-parkandride) - - serializes park & ride places vector tiles to protobufs.
- [tilelive-otp-citybikes](https://github.com/HSLdevcom/tilelive-otp-citybikes) - serializes city bike vector tiles to protobufs.
- [tilelive-otp-stops](https://github.com/HSLdevcom/tilelive-otp-stops) - serializes otp stops to protobufs.
- [tilelive-gl](https://github.com/HSLdevcom/tilelive-gl) - a fork of another project called tilelive-gl. This was used until recently in the `map-generator-server`, and still in `hsl-map-server`. The main repo is unmaintained, Mapbox-gl-native should be used directly instead.


### Deprecated or unused projects

This is a list of deprecated or otherwise older or unused projects that were started by the Map project.

- [jore-geometry-matcher](https://github.com/HSLdevcom/jore-geometry-matcher) - this should be executed after running `jore-graphql-import` to smoothen out the routes and match them to map geometry. Currently integrated to `jore-graphql-import` repository
- [pymapmatch](https://github.com/HSLdevcom/pymapmatch) - forked helper module used in the `jore-geometry-matcher`.
- [hsl-ticket-zone-map](https://github.com/HSLdevcom/hsl-ticket-zone-map) - a very simple embeddable map that shows the new ticket zones that will come into effect in 2019. Superseded by the zones showing up in the journey planner (Digitransit).
- [tile-merge-stream](https://github.com/HSLdevcom/tile-merge-stream) - helper module. Not used as far as we know.
- [map-utils](https://github.com/HSLdevcom/map-utils) - Python map utils and a stop query in Javascript. Unused as far as we know.
- [hsl-map-deployer](https://github.com/HSLdevcom/hsl-map-deployer) - deprecated repository for deploying projects into dev & prod servers. Contains the docker-compose and ngnix configs. This can be used for creating local dev environment.
- [hsl-stop-info](https://github.com/HSLdevcom/hsl-stop-info) - a replacement for the ["Stop tag page"](http://tag.hsl.fi/tag/16682?a) using GatsbyJS and aiming to be a lot more useful.
- [map-reports](https://github.com/HSLdevcom/map-reports) - a tool for managing reports about OSM faults and validating OSM data. Unfinished and will be moved out of the Map project.
- [hsl-map-validator](https://github.com/HSLdevcom/hsl-map-validator)
- [tilelive-otp-routes](https://github.com/HSLdevcom/tilelive-otp-routes) - serializes otp routes to protobufs.


## URLs and endpoints

These are the most important URL's and endpoints we use in the map project. Consult the readme of the specific project you are working on for more detailed information.

- [https://kartat.hsl.fi](https://kartat.hsl.fi) - this is the production server. The base url will redirect to hsl.fi, so you need to append the correct subdirectory where the app that you want to access lives.
- [https://dev.kartat.hsl.fi](https://dev.kartat.hsl.fi) - this is the development server. Do not expect it or any apps running on it to be available at any time, it is used for testing things that are in active development. The base url also redirects to hsl.fi on this server, so be sure to append the subdirectory of the project that you want to access.
- [/kuljettaja](https://kartat.hsl.fi/kuljettaja/) - the driver instruction app, or "kuljettajaohje", lives here. Project: [hsl-map-web-ui](https://github.com/HSLdevcom/hsl-map-web-ui).
- [/kartta](https://kartat.hsl.fi/kartta/) - the url for the map generator UI. Project: [hsl-map-generator-ui](https://github.com/HSLdevcom/hsl-map-generator-ui). Requires login.
- [/map-generator/generateImage](https://kartat.hsl.fi/map-generator/generateImage) - the POST endpoint for the map generator server. Check projects that use it for usage, like generator-ui and publisher. Project: [hsl-map-generator-server](https://github.com/HSLdevcom/hsl-map-generator-server).
- [/linjakartta](https://kartat.hsl.fi/linjakartta/) - where you can view the simple route map. Project: [hsl-route-map-poc](https://github.com/HSLdevcom/hsl-route-map-poc).
- [/julkaisin](https://kartat.hsl.fi/julkaisin/) - this is the UI of the service that generates stop posters. Requires login.
- [/jore/graphql](https://kartat.hsl.fi/jore/graphql) - the graphQL endpoint for the JORE API. Contains a subset of data from the JORE database. POST only. Replace the last segment with `/graphiql` to access the Graph*i*QL documentation. Projects: [jore-graphql](https://github.com/HSLdevcom/jore-graphql) and [jore-graphql-import](https://github.com/HSLdevcom/jore-graphql-import).
