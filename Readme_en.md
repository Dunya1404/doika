Doika is a module that helps to accept donations using bank cards and set up a new approach to the fundraising of Belarusian non-profit public organizations on their sites

## The current tasks of the project

1. Refactoring of iteration’s code 1.2  for transfering to the current (1.3) iteration. The transfer of frontend on vue.js
2. Specify (discuss) the tasks according to [directions](https://github.com/diglabby/doika/milestones)
3. Learn API BePaid [recurring payments](https://docs.bepaid.by/ru/subscriptions/intro)

## How to start development?
1. Browse status and roadmap of the project’s development on the milestones page.[milestone](https://github.com/diglabby/doika/milestones?direction=asc&sort=due_date&state=open).
2. How to deploy a local  environment for development [instruction] (TODO).
3. View the [documentation](https://realtimeboard.com/app/board/o9J_k0X88dM=/). 
- [The architecture of the files and base](https://realtimeboard.com/app/board/o9J_k0X88dM=/?moveToWidget=3074457346027045333)
- [The flowcharts](https://realtimeboard.com/app/board/o9J_k0X88dM=/?moveToWidget=3074457346144718504)
- [The list of classes](https://realtimeboard.com/app/board/o9J_k0X88dM=/?moveToWidget=3074457346135802429)
- [The Wiki](https://github.com/diglabby/doika/wiki/) part “for developers”.
- If you have questions and  difficulties , ask current team members (@fr0zen, @tyuba4, @Сёмка, @SvetaN) to give access to slack ( it’s possible to get invitation to the Slack channel by contacting us through the [form](https://docs.google.com/forms/d/e/1FAIpQLSf3q7HMtfJly4wCrRyIlHDdAzFExSjw2vqbA62XFJHofjMqjg/viewform)).
- Attention!We make pull requests to the dev branch.

[How to make a contribution](CONTRIBUTING.md)

## Development requirements

* [Apache](https://httpd.apache.org/download.cgi) (rewrite mod on, for virtual host directory too: AllowOverride All )
* MySQL >= 5.7 PostgreSQL, SQLite, MSSQL Server [Full list](https://laravel.com/docs/5.7/database)
* PHP >= 7.1.3
* OpenSSL PHP Extension, PDO PHP Extension, Mbstring PHP Extension, Tokenizer PHP Extension, XML PHP Extension, Ctype PHP Extension, JSON PHP Extension ([PHP Extensions](https://github.com/diglabby/doika/blob/master/composer.json#L8-L9)), BCMath PHP Extension
* On the basis of the framework Laravel 5.6 (you need Composer for installation)
* [Coding-Standard](https://github.com/diglabby/doika_1.2/wiki/%D0%9A%D0%BE%D0%B4%D1%8B%D0%BD%D0%B3-%D1%81%D1%82%D0%B0%D0%BD%D0%B4%D0%B0%D1%80%D1%82) 
* [Composer](https://getcomposer.org/download/)
* [NPM](https://nodejs.org/en/download/)
* [The example of  bug’s design](https://github.com/diglabby/doika_1.2/wiki/%D0%9F%D1%80%D1%8B%D0%BA%D0%BB%D0%B0%D0%B4-%D0%B0%D1%84%D0%B0%D1%80%D0%BC%D0%BB%D0%B5%D0%BD%D0%BD%D1%8F-%D0%B1%D0%B0%D0%B3%D0%B0)
* Attention! We work with requests (Pull request) on the GitHub to the dev branch(!)    

## For developer.Installation

## linux

1.  Open the repository https://github.com/diglabby/doika.git and create a fork
2. Add fork’s content of the repository to the base of your site using git clone. Switch to the dev branch using git checkout (for example, git checkout dev)
3. It’s necessary to define a group and user for all module’s files with the command:`sudo chown -R www-data:www-data`
4. Run the command `composer install` composer install from the terminal. You should run it from the base doika’s  directory.
5. Run the command `npm install` from the terminal. You should run it from the base doika’s  directory.
6. Perform the frontend’s build `npm run dev`
7. Prepare the file's config. To do this create the file’s copy .env.example in the doika’s folder and name it .env (tip:execute the command `cp .env.example .env`)
8. Add your data to the .env file DB_DATABASE={your_database} DB_USERNAME={your_username} DB_PASSWORD={your_password}
9. Open the database `php artisan migrate`. Import the doika.sql file in the database. Pay attention to the MySQL version when errors occur.
10. Generate the key for laravel: go to the doika’s folder and run through `php artisan key:generate`
11. The installed version should run on your local host with the path http://[host-name]/doika/admin/login
12.  Use the following  login information. Login:  demo@example.com Password:demo

### win (Open Server)

setting:
1. АStart Open Server settings, Domains tab, manual control, write the name of the domain, for example doika, domain folder, choose localhost
2. Open Modules tab, select Apache 7.2, php 7.2, mySQL 5.7, save, start the server
3. Open the repository https://github.com/diglabby/doika.git and click "save" clone or download and copy url
4. Go to the folder localhost and copy the project there using git clone https://github.com/diglabby/doika.git
5. Go to doika and using git switch to dev branch (git checkout dev)
6. Import the doika.sql file in the database (also open PhpMyAdmin, create a new database, open it, click import and select the doika.sql file)
7. Change the file's config. Change the file's name .env.example to .env and open it. DB_DATABASE = doika, DB_USERNAME = root (if you haven't changed) DB_PASSWORD = (empty if you haven't set password), change the line APP_KEY = на APP_KEY = base64:8ObMpr3jB1o5SQ3az2pqXo9tSPGAZOponr4eHBoDs9Y =
8. Type http: // doika / doika / admin in browser, impose demo@example.com demo

## Project structure (in the development)
what are the key files for (config file, installer file, where the front is, where the back is, what notes on the paths)

## What do I need to install the module?
For Republic of Belarus
* From the organizational side: the organization must have the official state registration, non-profit status (Article 553 of the Civil Code of the Republic of Belarus: donations can be accepted only by non-profit organizations) and an account in any Belarusian Bank. Collection of funds from individuals can be carried out for any purpose that does not contradict the statutory purpose of the non-profit organization.
* On the legal side: the domain of a public organization must be registered to a legal entity in the State Supervisory Department for Telecommunications of the Republic of Belarus. The main registration term: website hosting on the territory of Belarus.
* On the technical side: to ensure the security of payment data on your page with the module, we recommend using the https protocol. Server environment: apache, php, mysql.

## How to install the module?
The latest version and detailed installation manual to Doika_1.2 is [here](https://github.com/diglabby/doika_1.2/wiki/%D0%A3%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D1%9E%D0%BA%D0%B0-%D0%BC%D0%BE%D0%B4%D1%83%D0%BB%D1%8F-%D0%BD%D0%B0-%D1%85%D0%BE%D1%81%D1%82%D1%8B%D0%BD%D0%B3). 

## Licenses and restrictions
We use the following licenses:
* [GNU GPL 3.0](https://www.gnu.org/licenses/gpl-3.0.en.html) -for a code written in the project
* [Creative Commons Attribution Share-Alike](https://choosealicense.com/licenses/cc-by-sa-4.0/) -  for all the content including images, technical documentation

The product is distributed "as it is". That means any modifications you make all by yourself, or agree with the development team on a specific cost (falanster.by@gmail.com).

## External links
* [Presentation web-page](https://doika.falanster.by/)
* [PowerPoint presentation](https://docs.google.com/presentation/d/144zEv4DyBoa0jDKwee30Rip0oKZ8QzkeUKaNCRWy1qY/edit#slide=id.g42bd4a5055_0_28)


## I still have questions...
Visit the page of the most frequently asked questions about the Doika project [FAQ](https://github.com/diglabby/doika/wiki/FAQ)


