# Dillinger

[![N|Solid][1]][2]

Dillinger is a cloud-enabled, mobile-ready, offline-storage, AngularJS powered HTML5 Markdown editor.

*   Type some Markdown on the left
*   See HTML in the right
*   Magic

# New Features!

*   Import a HTML file and watch it magically convert to Markdown
*   Drag and drop images (requires your Dropbox account be linked)

You can also: - Import and save files from GitHub, Dropbox, Google Drive and One Drive - Drag and drop markdown and HTML files into Dillinger - Export documents as Markdown, HTML and PDF

Markdown is a lightweight markup language based on the formatting conventions that people naturally use in email. As [John Gruber][3] writes on the [Markdown site][4]

> The overriding design goal for Markdown's formatting syntax is to make it as readable as possible. The idea is that a Markdown-formatted document should be publishable as-is, as plain text, without looking like it's been marked up with tags or formatting instructions.

This text you see here is *actually* written in Markdown! To get a feel for Markdown's syntax, type some text into the left window and watch the results in the right.

### Tech

Dillinger uses a number of open source projects to work properly:

*   [AngularJS][5] - HTML enhanced for web apps!
*   [Ace Editor][6] - awesome web-based text editor
*   [markdown-it][7] - Markdown parser done right. Fast and easy to extend.
*   [Twitter Bootstrap][8] - great UI boilerplate for modern web apps
*   [node.js][9] - evented I/O for the backend
*   [Express][10] - fast node.js network app framework [@tjholowaychuk][11]
*   [Gulp][12] - the streaming build system
*   [Breakdance][13] - HTML to Markdown converter
*   [jQuery][14] - duh

And of course Dillinger itself is open source with a [public repository][15] on GitHub.

### Installation

Dillinger requires [Node.js][16] v4+ to run.

Install the dependencies and devDependencies and start the server.

`sh
$ cd dillinger
$ npm install -d
$ node app`

For production environments...

`sh
$ npm install --production
$ npm run predeploy
$ NODE_ENV=production node app`

### Plugins

Dillinger is currently extended with the following plugins. Instructions on how to use them in your own application are linked below.

| Plugin           | README                                  |
| ---------------- | --------------------------------------- |
| Dropbox          | [plugins/dropbox/README.md][17]         |
| Github           | [plugins/github/README.md][18]          |
| Google Drive     | [plugins/googledrive/README.md][19]     |
| OneDrive         | [plugins/onedrive/README.md][20]        |
| Medium           | [plugins/medium/README.md][21]          |
| Google Analytics | [plugins/googleanalytics/README.md][22] |

### Development

Want to contribute? Great!

Dillinger uses Gulp + Webpack for fast developing. Make a change in your file and instantanously see your updates!

Open your favorite Terminal and run these commands.

First Tab: `sh
$ node app`

Second Tab: `sh
$ gulp watch`

(optional) Third: `sh
$ karma test`

#### Building for source

For production release: `sh
$ gulp build --prod` Generating pre-built zip archives for distribution: `sh
$ gulp build dist --prod`

### Docker

Dillinger is very easy to install and deploy in a Docker container.

By default, the Docker will expose port 80, so change this within the Dockerfile if necessary. When ready, simply use the Dockerfile to build the image.

`sh
cd dillinger
docker build -t joemccann/dillinger:${package.json.version}` This will create the dillinger image and pull in the necessary dependencies. Be sure to swap out `${package.json.version}` with the actual version of Dillinger.

Once done, run the Docker image and map the port to whatever you wish on your host. In this example, we simply map port 8000 of the host to port 80 of the Docker (or whatever port was exposed in the Dockerfile):

`sh
docker run -d -p 8000:8080 --restart="always" <youruser>/dillinger:${package.json.version}`

Verify the deployment by navigating to your server address in your preferred browser.

`sh
127.0.0.1:8000`

#### Kubernetes + Google Cloud

See [KUBERNETES.md][23]

### Todos

*   Write MOAR Tests
*   Add Night Mode

## License

MIT

**Free Software, Hell Yeah!**

 [1]: https://cldup.com/dTxpPi9lDf.thumb.png
 [2]: https://nodesource.com/products/nsolid
 [3]: http://daringfireball.net
 [4]: http://daringfireball.net/projects/markdown/
 [5]: http://angularjs.org
 [6]: http://ace.ajax.org
 [7]: https://github.com/markdown-it/markdown-it
 [8]: http://twitter.github.com/bootstrap/
 [9]: http://nodejs.org
 [10]: http://expressjs.com
 [11]: http://twitter.com/tjholowaychuk
 [12]: http://gulpjs.com
 [13]: http://breakdance.io
 [14]: http://jquery.com
 [15]: https://github.com/joemccann/dillinger
 [16]: https://nodejs.org/
 [17]: https://github.com/joemccann/dillinger/tree/master/plugins/dropbox/README.md
 [18]: https://github.com/joemccann/dillinger/tree/master/plugins/github/README.md
 [19]: https://github.com/joemccann/dillinger/tree/master/plugins/googledrive/README.md
 [20]: https://github.com/joemccann/dillinger/tree/master/plugins/onedrive/README.md
 [21]: https://github.com/joemccann/dillinger/tree/master/plugins/medium/README.md
 [22]: https://github.com/RahulHP/dillinger/blob/master/plugins/googleanalytics/README.md
 [23]: https://github.com/joemccann/dillinger/blob/master/KUBERNETES.md