---
layout: post
title: Final Project Plan
description: A summary regarding the required elements from the Final Project description
courses: {'compsci': {'week': 12}}
type: tangibles
comments: true
---

**Project Plan: Enhancing the NFL Stats Tracker with Algorithmic and Data Structures Components**
Objective
Enhance the existing NFL Stats Tracker project to incorporate algorithmic techniques and data structures, demonstrating proficiency in list comprehensions, sorting/searching algorithms, 2D iteration, and Big(O) complexity analysis.

1. List Comprehensions
    Task: Add functionality to generate summaries of game results using list comprehensions.

    Implementation Steps:

    Use list comprehensions to create summaries of game results based on home and away scores.

2. Sorting / Searching
    Task 1: Implement sorting functionality to sort games based on specified statistics (e.g., score_home).

    Implementation Steps:

    Define a method get_sorted_games in the FootballScoreModel class.
    Use Python’s sorted function to sort games by a specified statistic.

    Task 2: Implement searching functionality to search for games involving a specific team.

    Implementation Steps:

    Define a method search_games in the FootballScoreModel class.
    Use SQLAlchemy’s filtering capabilities to search for games by team name.

3. Big(O) Complexity
    Task: Analyze and document the time and space complexity of sorting and searching algorithms.

    Implementation Steps:

    Analyze the sorting algorithm (sorted): O(n log n) time complexity.
    Analyze the searching algorithm (SQLAlchemy filter): O(n) time complexity (depending on database indexing).
    Document these analyses in the project’s documentation and blog posts.

4. 2D Iteration
    Task: Implement functionality to display game results in a grid format using 2D iteration.

    Implementation Steps:

    Define a method display_game_results_grid in the FootballScoreModel class.
    Use 2D iteration to format and display the game results in a grid.

5. Deployment (Full Stack)
    Task: A complete deployment illustration multiple people using and updating your Full Stack Web Application simultaneously.

    Implementation Steps: 

    Deploy backend with both team members being able to access and make changes to deployed server.