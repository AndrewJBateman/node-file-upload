# :zap: Node File Upload

* Uploads image files selected by the user from an Ionic frontend to a Node.js backend folder.
* **Note:** to open web links in a new window use: _ctrl+click on link_

![GitHub repo size](https://img.shields.io/github/repo-size/AndrewJBateman/node-file-upload?style=plastic)
![GitHub pull requests](https://img.shields.io/github/issues-pr/AndrewJBateman/node-file-upload?style=plastic)
![GitHub Repo stars](https://img.shields.io/github/stars/AndrewJBateman/node-file-upload?style=plastic)
![GitHub last commit](https://img.shields.io/github/last-commit/AndrewJBateman/node-file-upload?style=plastic)

## :page_facing_up: Table of contents

* [:zap: Node File Upload](#zap-node-file-upload)
	* [:page_facing_up: Table of contents](#page_facing_up-table-of-contents)
	* [:books: General info](#books-general-info)
	* [:camera: Screenshots](#camera-screenshots)
	* [:signal_strength: Technologies](#signal_strength-technologies)
	* [:floppy_disk: Setup](#floppy_disk-setup)
	* [:computer: Code Examples](#computer-code-examples)
	* [:cool: Features](#cool-features)
	* [:clipboard: Status & To-Do List](#clipboard-status--to-do-list)
	* [:clap: Inspiration](#clap-inspiration)
	* [:file_folder: License](#file_folder-license)
	* [:envelope: Contact](#envelope-contact)

## :books: General info

* Very simple backend using node with express and multer to load image files.
* Client frontend uses Ionic-Angular or Ionic-React to show user controls to upload file from PC file system.

## :camera: Screenshots

![Example screenshot](./img/frontend.png)

## :signal_strength: Technologies

**Frontends:**

* [Ionic v6](https://ionicframework.com/)
* [Angular v13](https://angular.io/)
* [ionic/angular v6](https://www.npmjs.com/package/@ionic/angular) angular building blocks for Ionic
* [ionic/react v5](https://www.npmjs.com/package/@ionic/react) react building blocks for Ionic

**Backend:**

* [cors](https://www.npmjs.com/package/cors) Cross Origin Resource Sharing Connect/Express middleware
* [Express v4](https://expressjs.com/) Node.js middleware, includes body parsing
* [Morgan v1](https://www.npmjs.com/package/morgan) HTTP request logger middleware for node.js
* [Multer v1](https://www.npmjs.com/package/multer) Middleware for handling `multipart/form-data`.
* [Busboy](https://github.com/mscdex/busboy) used by Multer as a streaming parser for HTML form data for node.js

## :floppy_disk: Setup

**/Ionic-Angular & /Ionic-React Frontends:**

* `cd client-angular` then `npm i` to install Angular frontend dependencies
* `cd client-react` then `npm i` to install React frontend dependencies
* I had to have a Google Chrome CORS extension activated for this to work
* Angular frontend: Run `ionic serve` & navigate to `http://localhost:8080/` or `ng serve` & navigate to `http://localhost:4200/` to run server. The app will automatically reload if you change any of the source files.
* React frontend: Run `npm run start` & navigate to `http://localhost:3001/`
* The apps will automatically reload if you change any of the source files.

**/server-express Backend:**

* `cd server-express` then `npm i` to install backend dependencies
* Run `node index.js` for a node.js server. Backend does not update automatically as nodemon not used

## :computer: Code Examples

* Extract from `server-express/index.js` to show use of dependencies and posting of objects to uploads folder.

```javascript
app.use(cors());
app.use(morgan("combined"));
app.use(express.json());
app.use(express.urlencoded({ extended: true }));

app.post("/upload", upload.single("photo"), (req, res) => {
  console.log(req.file);
});

app.post("/uploads", upload.array("photos[]"), (req, res) => {
  console.log(req.files);
});
```

## :cool: Features

* Tutorial shows different front-ends that can be used to pass objects to the backend
* Backend 'uploads' folder is automically created if it does not exist already.

## :clipboard: Status & To-Do List

* Status: Working
* To-Do: Nothing. There is repeated frontend ionic-angular code and scope for refactoring - I am leaving it as is for now.

## :clap: Inspiration

* [Joshua Morony: Youtube: How to upload files to a server with Ionic](https://www.youtube.com/watch?v=tcWTl7tBT5E&ck_subscriber_id=433042050)

## :file_folder: License

* This project is licensed under the terms of the MIT license.

## :envelope: Contact

* Repo created by [ABateman](https://github.com/AndrewJBateman), email: gomezbateman@yahoo.com
