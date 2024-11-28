<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mobile App Sign-In</title>
    <style>
        body, html {
            margin: 0;
            padding: 0;
            height: 100%;
            overflow: hidden;
            font-family: 'Arial', sans-serif;
        }

        /* Full-screen video background */
        .video-background {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            object-fit: cover; /* Ensures the video covers the entire screen */
            z-index: -1; /* Places the video behind all content */
        }

        /* Gradient overlay to enhance text visibility */
        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(to bottom, rgba(0, 31, 61, 0.7), rgba(233, 30, 99, 0.7));
            z-index: 0; /* Below the content but above the video */
        }

        .container {
            width: 592px;
            background: #000; /* Black background for the sign-in box */
            border-radius: 8px;
            padding: 20px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.1);
            box-sizing: border-box;
            display: flex;
            flex-direction: column;
            justify-content: flex-start;
            min-height: 500px;
            text-align: center;
            z-index: 1; /* Content above the video */
            margin: auto;
            position: relative;
            top: 50%;
            transform: translateY(-50%);
        }

        .container img {
            width: 150px;
            height: 150px;
            display: block;
            margin: 0 auto 20px;
        }

        h2 {
            color: #fff;
            font-size: 18px;
            margin-bottom: 15px;
        }

        .form-group {
            margin-bottom: 12px;
            display: flex;
            flex-direction: column;
            align-items: flex-start;
        }

        .form-group label {
            font-size: 12px;
            color: #fff;
            margin-bottom: 6px;
        }

        .form-group input,
        .form-group select {
            width: 100%;
            padding: 8px;
            font-size: 12px;
            border: 1px solid #fff;
            border-radius: 4px;
            background-color: #333;
            color: #fff;
            box-sizing: border-box;
        }

        .form-group input#username,
        .form-group input#phone,
        .form-group select#gender,
        .form-group input#invitation-code,
        .form-group input#login-password,
        .form-group input#confirm-password,
        .form-group input#withdrawal-password {
            background-color: #fff;
            border: 1px solid #808080;
            color: #000;
        }

        .agreement-container {
            display: flex;
            flex-direction: row;
            align-items: center;
            gap: 10px;
        }

        .agreement {
            font-size: 12px;
            color: #fff;
        }

        .agreement a {
            color: #3498db;
            text-decoration: none;
        }

        .button-container {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .button {
            width: 100%;
            padding: 10px;
            background-color: #e91e63;
            color: #fff;
            font-size: 14px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        .button:hover {
            background-color: #d81b60;
        }

        .button.secondary {
            background-color: #7f8c8d;
        }

        .button.secondary:hover {
            background-color: #95a5a6;
        }

        .footer {
            text-align: center;
            margin-top: 10px;
            font-size: 12px;
            color: #fff;
        }

        .footer a {
            color: #3498db;
            text-decoration: none;
        }

        @media (max-width: 768px) {
            .container {
                width: 80%;
                padding: 20px;
            }

            .container img {
                width: 80px;
                height: 80px;
            }

            h2 {
                font-size: 16px;
            }
        }

        @media (max-width: 480px) {
            .container {
                width: 90%;
                padding: 15px;
            }

            .container img {
                width: 60px;
                height: 60px;
            }

            h2 {
                font-size: 14px;
            }
        }
    </style>
</head>
<body>
    <!-- Video Background -->
    <video class="video-background" autoplay muted loop>
        <source src="C:\Users\Administrator\Desktop\video.svg.mp4" type="video/mp4">
        <source src="C:\Users\Administrator\Desktop\video.svg.mp4" type="video/webm">
        <source src="C:\Users\Administrator\Desktop\video.svg.mp4" type="video/ogg">
        Your browser does not support the video tag.
    </video>

    <!-- Gradient Overlay -->
    <div class="overlay"></div>

    <!-- Sign-In Form -->
    <div class="container">
        <img src="logo.svg" alt="App Logo">
        <h2>Sign In</h2>
        <form>
            <div class="form-group">
                <label for="username">Username</label>
                <input type="text" id="username" name="username" required>
            </div>
            <div class="form-group">
                <label for="phone">Phone Number</label>
                <input type="tel" id="phone" name="phone" required>
            </div>
            <div class="form-group">
                <label for="gender">Gender</label>
                <select id="gender" name="gender" required>
                    <option value="">Select Gender</option>
                    <option value="male">Male</option>
                    <option value="female">Female</option>
                    <option value="other">Other</option>
                </select>
            </div>
            <div class="form-group">
                <label for="invitation-code">Invitation Code</label>
                <input type="text" id="invitation-code" name="invitation-code" required>
            </div>
            <div class="form-group">
                <label for="login-password">Login Password</label>
                <input type="password" id="login-password" name="login-password" required>
            </div>
            <div class="form-group">
                <label for="confirm-password">Confirm Login Password</label>
                <input type="password" id="confirm-password" name="confirm-password" required>
            </div>
            <div class="form-group">
                <label for="withdrawal-password">Withdrawal Password</label>
                <input type="password" id="withdrawal-password" name="withdrawal-password" required>
            </div>
            <div class="agreement-container">
                <input type="checkbox" id="agreement" name="agreement" required>
                <label for="agreement" class="agreement">I agree to the <a href="#">Terms and Conditions</a></label>
            </div>
            <div class="button-container">
                <button type="submit" class="button">Sign In</button>
                <button type="button" class="button secondary" onclick="window.location.href='login.html'">Back to Login</button>
            </div>
        </form>
        <div class="footer">
            <p>Need help? <a href="#">Contact Us</a></p>
        </div>
    </div>
</body>
</html>

