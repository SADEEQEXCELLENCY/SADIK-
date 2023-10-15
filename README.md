<!DOCTYPE html>
<html>
<head>
    <title>Join Market</title>
    <link rel="stylesheet" href="Registrationstyle.css">
</head>
<style type="text/css">



body {
            font-family: Arial, sans-serif;
            background-color: #f2f2f2;
            text-align: center;
        }

        .login-container {
            display: inline-block;
            margin: 20px;
            padding: 20px;
            background-color: #ffffff;
            border: 1px solid #ccc;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .signup-container {
            display: inline-block;
            margin: 20px;
            padding: 20px;
            background-color: #ffffff;
            border: 1px solid #ccc;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }


        h2 {
            margin-bottom: 20px;
        }

        input[type="text"],
        input[type="email"],
        input[type="password"] {
            width: 90%;
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }

        button {
            background-color: #007bff;
            color: #fff;
            border: none;
            border-radius: 5px;
            padding: 10px 20px;
            cursor: pointer;
        }

        button:hover {
            background-color: #0056b3;
        }


</style>


<body>
    
    <div class="signup-container">
        <h2>Sign Up</h2>
        <form id="signup-form">
            <input type="text" id="fullName" placeholder="Full Name">
            <input type="email" id="signupEmail" placeholder="Email">
            <input type="password" id="signupPassword" placeholder="Password">
            <button type="submit">Sign Up</button>
        </form>
    </div>
    
    
    <div class="login-container">
        <h2>Login</h2>
        <form id="login-form">
            <input type="email" id="loginEmail" placeholder="Email">
            <input type="password" id="loginPassword" placeholder="Password">
            <button type="submit">Login</button>
        </form>
    </div>


    <script src="Registration.js"></script>
    
    
    
</body>
</html>

<script type="text/javascript">


const loginForm = document.getElementById("login-form");
            const signupForm = document.getElementById("signup-form");

            const isLoggedIn = localStorage.getItem("isLoggedIn");
            const userName = localStorage.getItem("USERNAME");

            if (isLoggedIn === "true" && userName) {
            
                window.location.href = "../welcome.html";
            } 
            signupForm.addEventListener("submit", function (e) {
                e.preventDefault();

             
                const fullName = document.getElementById("fullName").value;
                const signupEmail = document.getElementById("signupEmail").value;
                const signupPassword = document.getElementById("signupPassword").value;

            
                localStorage.setItem("USERNAME", fullName);
                localStorage.setItem("USER_EMAIL", signupEmail);
                localStorage.setItem("USER_PASSWORD", signupPassword);


                if (fullName !== '' && signupEmail !== '' && signupPassword !== '') {
                    alert("Registration successful. You can now login.");
                }
            });
          
            
   loginForm.addEventListener("submit", function (e) {
                e.preventDefault();

           
                const loginEmail = document.getElementById("loginEmail").value;
                const loginPassword = document.getElementById("loginPassword").value;

          
                const storedEmail = localStorage.getItem("USER_EMAIL");
                const storedPassword = localStorage.getItem("USER_PASSWORD");

                if (loginEmail === storedEmail && loginPassword === storedPassword && loginEmail !== '' && loginPassword !== '') {
                    //
                    alert("Login successful!");
        
localStorage.setItem("isLoggedIn", "true");

window.location.href = '../welcome.html';
                } else {
                    alert("Invalid credentials, no matched account found. Please try again.");
                }
            });



</script>
