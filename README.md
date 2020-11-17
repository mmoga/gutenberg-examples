# Gutenberg Examples

<p align="center"><img src="https://user-images.githubusercontent.com/1039236/47116000-fd775000-d27d-11e8-9c46-761a90cb30a2.gif" alt="Demo"></p>

This was cloned to follow along with the [blocks tutorial.](https://developer.wordpress.org/block-editor/tutorials/block-tutorial/)

Examples for extending
[Gutenberg](https://github.com/WordPress/gutenberg)
with plugins which create blocks.

See also:
[Gutenberg developer documentation](https://wordpress.org/gutenberg/handbook/)

## Installation

Gutenberg Examples are distributed as WordPress plugin.

1. [Download a pre-built zip archive of the latest release](https://github.com/WordPress/gutenberg-examples/releases).
   > Do not download from the "Clone or download" GitHub button, as this includes the source material only. Read the [Development](#development) instructions below if you’re interested in building your own copy of the plugin.
2. Navigate to the **Plugins > Add new** screen in your WordPress administrative dashboard.
3. Click **Add New** at the top of the page.
4. Click **Upload Plugin** at the top of the page.
5. Click **Choose File**, then find and **Upload** the downloaded zip file.
6. After the plugin finishes installing, click **Activate**.
7. You’re done!

## Development

First, you need a WordPress Environment to run the plugin on. The quickest way to get up and running is to use the provided docker setup. Install [docker-ce](https://store.docker.com/search?type=edition&offering=community) and [docker-compose](https://docs.docker.com/compose/install/) by following the most recent instructions on the docker site.

In the folder of your preference, clone this project and enter the working directory:

```
git clone git@github.com:WordPress/gutenberg-examples.git
cd gutenberg-examples
```

To bring up this local WordPress instance run:

```
docker-compose up -d
```

The WordPress should be available at http://localhost:9999

To stop this local WordPress instance later run:

```
docker-compose stop
```

Now go to http://localhost:9999/wp-admin/plugins.php and **Activate** Gutenberg-examples plugin. The docker script has mapped the gutenberg-examples folder to this now activated plugin. Every time you build an example, it is automaticaly updated in the running docker instance. Old block inserted are not updated, you need to add in your page again.

For each of the examples that include an esnext example the following commands are required to build the plugins:

To install the node packages

```
npm install
```

To build the production version of the plugin

```
npm run build
```

To build a development version, change to the local directory of the block you are working on, and run `npm start` to watch for changes and automatically rebuild as you develop.

```
cd 01-basic-esnext/
npm start
```

<br/><br/><p align="center"><img src="https://s.w.org/style/images/codeispoetry.png?1" alt="Code is Poetry." /></p>
