# Install dependencies:

- Install Node.js - [https://nodejs.org/en/](https://nodejs.org/en/)
- Install Node Version Manager – Switch between node versions - [https://github.com/creationix/nvm](https://github.com/creationix/nvm)
- Install any IDE/Text Editor of your choice – Visual Studio Code, Atom, Sublime Text 3
- Install any API Environment software of your choice – Postman, Insomnia

## Pre-requisite:
- Navigate to `etc/hosts` file and Add `dev.recruit.com` right beside the line that displays `127.0.0.1` – This is to indicate that we are whitelisting dev.recruit.com as a localhost address. Sample of the edit below:

![whitelist](https://imgur.com/P1vGA33.png)

# Database

**Note:** Requires version 5.7 to run the entire software application. For those requiring help downgrading from MariaDB to MySQL, kindly follow this tutorial - [https://gist.github.com/odan/c799417460470c3776ffa8adce57eece](https://gist.github.com/odan/c799417460470c3776ffa8adce57eece)

1.	Use any SQL IDE of your preference.
2.	Copy the Databse.sql script and run it in the IDE.
3.	Remember to change the user credentials.
4.	The database should be setup and ready to use.


# Portal

1.	Install and run Node v6.10.3
2.	`cd` into the TRN-Portal folder
3.	Run `npm i`
4.	Run `npm run start` to start the client-portal
5.	Navigate to [http://dev.recruit.com:8080](http://dev.recruit.com:8080) to view the portal and login
6.	Login credentials: `sampleuser@abc.com` / `user123`


# Server

1.	Install and run Node v8.1.2
2.	`cd` into the TRN-Server folder
3.	Run `npm i`
4.	Change the Database password inside `lib/utils/config.js` - Required to be in sync with the password you chose for when setting up the database
5.	Run `npm run start` to start the back-end server
6.	Server is available for API CRUD operations via [http://dev.recruit.com:8030](http://dev.recruit.com:8030)


# Production Usage

In order to use the portal and server in your production environment, kindly update the following files:

## Portal

1. Update the  `config/index.js` file.
2. Under the `build` object, update the `serviceUrl` with your Production URL of your choice.

## Server

1. Update the `config/production.json` file.
2. Replace `<<YOUR_PRODUCTION_IP_ADDRESS>>` with your Production IP Address of your VPS instance.
2. Replace `http://<<YOUR_PORTAL_URL>>` and `https://<<YOUR_PORTAL_URL_WITH_HTTPS>>` with your Production Portal URL you have setup.