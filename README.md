# DishCovery -- Discover the perfect dish


## Overview

- The 'Recipe Finder' application aims to help users discover recipes based on ingredients, cuisine, dietary restrictions, and cooking time.
- It will provide a user-friendly interface for browsing, saving, and sharing recipes. The backend will handle user authentication, recipe storage, and API integration for fetching recipe data.

## Tech Stack
  - Frontend: ReactJS
  - Backend: Node.js (Express)
  - Database: MongoDB (for recipe and user data storage)
  - API Integration: External recipe APIs (e.g., Spoonacular API)
  - Authentication: JWT (JSON Web Token)
  - Deployment: AWS (EC2, S3) or Vercel for frontend

## Core Features
 - User Registration and Login :- Users can sign up and log in to access personalized features.
 - Recipe Search :- Search for recipes by ingredients, cuisine, or dietary preferences.
 - Recipe Details :- View detailed information about each recipe, including ingredients, cooking instructions, and nutritional info.
 - User Profile :- Users can save favorite recipes and create custom recipe collections.
 - API Integration :- Integrate with an external recipe API for extensive recipe data.
 - Responsive Design :- The application will be mobile-friendly.

## High-Level Architecture
      
  - Frontend (ReactJS)
    - Pages: Home, Search, Recipe Details, User Profile, Login, Registration.
    - Components: Navbar, RecipeCard, SearchBar, RecipeDetails, UserProfile.
    - State Management: Context API or Redux (for managing global state).
    - Backend (Node.js, Express)

  - Routes: /api/users, /api/recipes, /api/search.
    - Controllers: UserController, RecipeController.
    - Middleware: Authentication (JWT), Error Handling.
    - Database Models: User, Recipe, Favorite.
    - Database (MongoDB)
    
  - Collections: users, recipes, favorites.

## API Endpoints
- User Registration (/api/users/register)

     - Method: POST
     - Request Body: email, password, fullName
     - Response: 201 Created
     - User Login (/api/users/login)

- Method: POST
  - Request Body: email, password
  - Response: 200 OK with JWT token
  - Search Recipes (/api/recipes/search)

- Method: GET
    - Query Params: ingredients, cuisine, diet
    - Response: List of recipes
    - Get Recipe Details (/api/recipes/{recipeId})

- Method: GET
    - Response: Recipe details
    - Save Favorite Recipe (/api/users/{userId}/favorites)

- Method: POST
    - Request Body: recipeId
    - Response: 201 Created



## Domain Driven Design Diagram

```mermaid
---
title: Roomies Radar - Updated Class Diagram
---

classDiagram

    class User {
        +String userId
        +String email
        +String password
        +String fullName
        +Profile profile
        +List~Favorite~ favorites
        +register()
        +login()
        +saveFavorite(recipeId)
    }

    class Profile {
        +String profileId
        +String userId
        +String preferences
        +List~Recipe~ savedRecipes
        +viewRecipe(recipeId)
    }

    class Favorite {
        +String favoriteId
        +String userId
        +String recipeId
        +saveRecipe()
        +removeRecipe()
    }

    class Recipe {
        +String recipeId
        +String title
        +String description
        +List~Ingredient~ ingredients
        +Nutrition nutrition
        +List~Instruction~ instructions
        +fetchRecipeDetails(recipeId)
    }

    class Ingredient {
        +String ingredientId
        +String name
        +String quantity
        +String unit
    }

    class Nutrition {
        +int calories
        +int protein
        +int fat
        +int carbs
    }

    class Instruction {
        +int stepNumber
        +String description
    }

    class JWT {
        +String token
        +generateToken(userId)
        +validateToken(token)
    }

    class ExternalAPI {
        +fetchRecipes(query)
        +fetchRecipeDetails(recipeId)
    }

User --> Profile : "has a"
    User --> Favorite : "can save"
    User --> JWT : "authenticates with"
    Profile --> Recipe : "views"
    Recipe --> Ingredient : "contains"
    Recipe --> Nutrition : "provides"
    Recipe --> Instruction : "has steps"
    Favorite --> Recipe : "saves"
    Recipe --> ExternalAPI : "fetches data from"
```

## Explanation
- User: Represents the main user entity, which interacts with the system.
- Profile: Contains user preferences and saved recipes.
- Favorite: Manages saved recipes for each user.
- Recipe: Represents a recipe with details like ingredients, nutrition, and instructions.
- Ingredient: Represents an ingredient used in a recipe.
- Nutrition: Provides nutritional information for a recipe.
- Instruction: Represents a step in the recipe instructions.
- JWT: Handles user authentication.
- ExternalAPI: Fetches recipe data from an external API.

# Commands I Used to commit and push:

- git init (Even there is an hidden files I have initializes just for best practice)

- git add .

- git add filename.extension (used to add separate files in the commit list)

- git commit -m "READEME"

- git push origin main


# Pre-requisites

- Just one windows or Linux or Mac OS system and little bit of knowledge about git commands.
- Use VsCode to create and write the code in html and css. This is the best IDE for most of the programming languages.
- Use extensions which are related to HTML, CSS, live server and more to finish your work faster.

# Contributions

Want to learn with my code by editing:

It's pretty straingforward :

<img align="left" alt="Java" width="30px" style="padding-right:10px;" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" />


```git clone <repository url>```

## BUILT WITH

* A lot of interest and respect towards Knowledge.
* An International Student @NORTHEASTERN_UNIVERSITY

## MADE BY BURRA SAI KALYAN
