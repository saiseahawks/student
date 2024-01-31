---
toc: true
comments: false
layout: post
title: Login Page
description: Internet and basic protocols
type: tangibles
courses: { compsci: {week: 2} }
---

<html>
<head>
    <title>Login</title>
    <link rel="stylesheet" href="{{ url_for('static', filename='style.css') }}">
</head>
<body>
    <form action="/login" method="post">
        <input type="text" name="username" placeholder="Username" required>
        <input type="password" name="password" placeholder="Password" required>
        <button type="submit">Login</button>
    </form>
    <a href="/signup">Sign up</a>
</body>
</html>


<html>
<head>
    <title>Signup</title>
    <link rel="stylesheet" href="{{ url_for('static', filename='style.css') }}">
</head>
<body>
    <form action="/signup" method="post">
        <input type="text" name="username" placeholder="Username" required>
        <input type="password" name="password" placeholder="Password" required>
        <button type="submit">Sign Up</button>
    </form>
    <a href="/login">Login</a>
</body>
</html>


<html>
<head>
    <title>Home</title>
    <link rel="stylesheet" href="{{ url_for('static', filename='style.css') }}">
</head>
<body>
    <h1>Welcome, {{ username }}!</h1>
    <a href="/logout">Logout</a>
</body>
</html>
