# Backend Project

Welcome to the backend project! This repository contains the code for the server-side of our application.

## Prerequisites

Before running the backend project locally, make sure you have the following software and configurations in place:

- Node.js: [Download and install Node.js](https://nodejs.org/)
- npm: Node.js comes with npm, so no additional installation is required.
- MongoDB: Make sure you have a MongoDB instance running, and update the `DATABASE` variable in the `.env` file with your MongoDB connection link.

## Setting Up Environment Variables

Create a `.env` file in the backend directory with the following content:

```env
DATABASE=mongodb://your-mongodb-connection-link
EMAIL=your-email@gmail.com
APP_PASSWORD=your-app-password
```
# Creating Google OAuth2 Client ID and Secret

This guide provides step-by-step instructions on how to create a Google OAuth2 client ID and secret for authenticating with Google APIs. This is particularly useful for applications that need to access services such as Gmail.

## Prerequisites

Before you begin, make sure you have:

- A Google Account
- Access to the [Google Cloud Console](https://console.developers.google.com/)

## Steps

### 1. Create a Project

1. Open the [Google Cloud Console](https://console.developers.google.com/).
2. In the top bar, click on the project dropdown and then click on "New Project."
3. Enter a name for your project and click "Create."

### 2. Enable APIs and Services

1. In the Cloud Console, navigate to the "APIs & Services" > "Dashboard."
2. Click on "+ ENABLE APIS AND SERVICES."
3. Search for and enable the "Gmail API."

### 3. Create Credentials

1. In the Cloud Console, navigate to the "APIs & Services" > "Credentials."
2. Click on "Create Credentials" and select "OAuth client ID."
3. Choose the application type:
   - **Application type:** Web application
   - **Name:** Enter a name for your OAuth client.
   - **Authorized redirect URIs:** Add the URIs where users will be redirected after granting access. For local development, you can use `http://localhost:3000/oauth2callback`.
4. Click "Create."

### 4. Obtain Client ID and Secret

1. Once created, your OAuth client will be listed in the "Credentials" tab.
2. Click on the pencil icon next to your OAuth client to view the details.
3. You will find the **Client ID** and **Client Secret**.

### 5. Download Credentials JSON

1. In the "Credentials" tab, locate the "Download" button next to your OAuth client.
2. Download the credentials JSON file. This file contains the client ID, client secret, and other information needed for authentication.

### Note:

- Keep your client secret secure. Do not expose it in public repositories or share it publicly.
- If you need to change the authorized redirect URIs or other settings, you can do so in the "Credentials" tab.
- For production, use HTTPS for redirect URIs.


## Generating Gmail App Password
To send emails using your Gmail account in a secure manner, you'll need to generate an "App Password" for your Node.js application. Follow these steps:

Enable Two-Factor Authentication (2FA) for your Gmail account. This adds an extra layer of security to your account.

Go to your Google Account.

Navigate to the "Security" section.

Under "Signing in to Google," find the "App passwords" section.

Generate a new App Password for your application. Choose "Mail" and the device/app you're using.

Use this App Password in your Node.js application instead of your regular Gmail password.


After generating Google Auth and Secret Key, and obtaining email credentials with an app password, paste the generated values into the designated placeholders in the server's configuration file.

## Downloading Dependencies

To download the project dependencies, run the following command in the project directory:

```bash
npm install
```

Project Dependencies

1. Nodemailer
Nodemailer is a module for Node.js applications that allows easy email sending. It is used in this project for handling email functionality.

2. Passport Google Auth
Passport-Google-OAuth is a Passport strategy for authenticating with Google using the OAuth 2.0 API. It is commonly used for handling user authentication via Google accounts.

# Project Dependencies

## 1. Nodemailer

[Nodemailer](https://nodemailer.com/) is a module for Node.js applications that simplifies the process of sending emails. It provides a flexible and easy-to-use API for handling email functionality. In this project, Nodemailer is utilized for managing email-related tasks.

## 2. Passport Google Auth

[Passport-Google-OAuth](http://www.passportjs.org/packages/passport-google-oauth20/) is a Passport strategy designed for authenticating with Google using the OAuth 2.0 API. This strategy enables secure and convenient user authentication via Google accounts. In the context of this project, Passport Google Auth is employed for handling user authentication.

