BeyondChats Content Intelligence Platform

A full-stack system that scrapes legacy blog content, enhances it using AI and search-engine insights, and presents both original and improved articles through a modern web interface.

This project demonstrates backend scraping, API design, automation with Node.js, LLM-based content transformation, and frontend rendering using React.

Architecture Overview

The project consists of three independent but connected components:

Laravel Backend

Scrapes blog articles from BeyondChats

Stores content in a database

Exposes REST APIs for article management

Node.js Automation Service

Fetches the latest article from the backend

Searches Google for competing articles

Scrapes and analyzes top-ranking content

Uses an LLM to rewrite the article

Publishes the improved version back to the backend

React Frontend

Displays both original and updated articles

Responsive, clean, and professional UI

Tech Stack
Backend

Laravel 10

PHP 8+

MySQL / PostgreSQL / SQLite

Guzzle HTTP Client

Symfony DomCrawler

Automation

Node.js 18+

Puppeteer

Axios

Cheerio

OpenAI API

Frontend

React

Vite

Axios

Project Structure
beyondchats-fullstack/
│
├── backend-laravel/
│   ├── app/
│   ├── database/
│   ├── routes/
│   └── artisan
│
├── node-bot/
│   ├── index.js
│   └── package.json
│
└── frontend-react/
    ├── src/
    ├── index.html
    └── package.json

Backend Setup (Laravel)
Requirements

PHP 8+

Composer

MySQL / PostgreSQL / SQLite

Installation
cd backend-laravel
cp .env.example .env
composer install
php artisan key:generate
php artisan migrate

Scrape Oldest Articles
php artisan scrape:beyondchats

Run Server
php artisan serve


API will be available at:

http://127.0.0.1:8000/api/articles

Node.js Automation Setup
Requirements

Node.js 18+

Google Chrome (for Puppeteer)

OpenAI API Key

Installation
cd node-bot
npm install

Environment Variable
export OPENAI_KEY=your_openai_api_key

Run Automation Script
node index.js


This will:

Fetch the latest article

Find competing articles on Google

Rewrite content using AI

Publish the updated article to Laravel

Frontend Setup (React)
Installation
cd frontend-react
npm install
npm run dev


The UI will be available at:

http://localhost:5173

API Endpoints
Method	Endpoint	Description
GET	/api/articles	List all articles
GET	/api/articles/{id}	Fetch single article
POST	/api/articles	Create article
PUT	/api/articles/{id}	Update article
DELETE	/api/articles/{id}	Delete article
Key Features

Automated scraping of legacy blog content

Structured storage with versioning (original vs updated)

AI-powered content enhancement

Google search intelligence integration

Clean REST API design

Responsive frontend interface

Notes & Limitations

Google scraping via Puppeteer may require additional configuration in cloud environments

LLM usage requires a valid API key

This project is intended for educational and demonstration purposes

Possible Improvements

Add authentication and roles

Use job queues for scraping and rewriting

Replace Google scraping with SERP APIs

Add SEO metadata support

Dockerize for one-command deployment

Add automated tests

License

This project is provided for demonstration and educational purposes.

Author

Built as a full-stack engineering exercise demonstrating real-world backend, automation, and frontend integration.
