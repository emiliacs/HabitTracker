# Project Red: LifeHabits

\*ASP.Net Core(3.1) API with React Native frontend

## What is this?

Application to help user to create habits, with positive reinforcement

User creates habit-entry, in which they can specify:

- How many times habit has to be checked to complete
- Write down reward they get once habit is complete
- Habits can be completed as group
  - All users have their own habit to complete those counts to overall group success
  - One big habit that all contribute towards
- Among other variables

For example, user wants to get up early for every day a month and if they succeed, they get to buy themself a chocolate bar.

### Features

- User validation with JWT
- Email verification

## Frontend

[Link to frontend repository](https://gitlab.com/Pinosto/teamredfrontend)

### Requirements

- Node [Link](https://nodejs.org/en/)

### Install

- Clone repository
- Install npm packages with "npm install"
- Add API URL to .env file
- Run app with "npm start"

## Backend

[Link to backend repository](https://github.com/emiliacs/HabitTrackerBackend)

### Requirements

- ASP.Net Core(3.1) [Link](https://dotnet.microsoft.com/download/dotnet/3.1)
- PostgresSQL database (Not tested with other SQL datanbase options yet)

### Install

Clone and make sure requirements are installed.
REMEMBER to check appsettings.Development.json!
  - Minium
    - DatabaseLogin : EasyLog
    - JWTSettings (AverageLifespan: integers WITHOUT quotemarks)
- If no existing database you can run command on Package Manager Console (Visual Studio 2019) to create a database with testing/demo data
  - Demo user credentials:
    - email: _test@email.com_
    - password: _Salasana1-_

## EndPoints

### User

| Method | URL                                      | Description                     |
| ------ | ---------------------------------------- | ------------------------------- |
| POST   | api/users/                               | Create user                     |
| GET    | api/users                                | Get all users                   |
| GET    | api/users/me                             | Get user with token             |
| GET    | api/users/{userId:int}                   | Get user with id                |
| GET    | /api/users/search?name=value&email=value | get user with name and/or email |
| PATCH  | api/users/verify?verificationcode=value  | Verify user email               |
| PATCH  | api/users/{userId:int}                   | Edit user profile               |
| DELETE | api/users/{userId:int}                   | Delete user with id             |
| POST   | api/login                                | Login user                      |
| POST   | api/logout                               | Logout user                     |

### Habit

| Method | URL                                | Description                         |
| ------ | -----------------------------------|------------------------------------ |
| GET    | api/habits                         | Get all public habits               |
| GET    | api/habits/{habitId:int}           | Get public habit with id            |
| GET    | api/habits/search?habitName=value  | Get all public habits by habit name |
| GET    | api/habits/user/{userId:id}        | Get users private habits            |
| GET    | api/habits/user/name?username=value| Get users public habits             |
| PATCH  | api/habits/{habitId:int}           | Edit habit                          |
| POST   | api/habits/                        | Create new habit                    |
| Delete | api/habits/{habitId:int}           | Delete habit with id                |

### Habit history

| Method | URL                                | Description                         |
| ------ | -----------------------------------|------------------------------------ |
| GET    | api/habithistory                                                     | Get all history                         |
| Get    |  api/habithistory/habit/{habitId:int}                                | Get all history of one habit            |
| GET    | api/habithistory/{userId:int}/sevendayhistory                        | Get user's seven day habit history      |
| GET    |  api/habithistory/user/{userId:int}/search)                          | Get user's all history                  |
| GET    |  api/habithistory/search/{userId:int}?startdate=value&enddate=value  |Get user's history from specific timespan|
| POST   |  api/habithistory                                                    | Add habit to history                    |
| PATCH  |  api/habithistory({historyId:int})                                   | Edit previously made history            |
| Delete |  api/habithistory/{historyId:int}                                    | Delete history with history Id          |
| Delete |  api/habithistory/user/{userId:int}                                  | Delete all user's history               |


