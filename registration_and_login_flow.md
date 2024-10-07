```mermaid
%%{init: 
  {'theme': 'base', 
   'themeVariables': 
    {
      'primaryBorderColor': #636d83',
      'backgroundColor': '#282c2d'
    }
  }
}%%

stateDiagram-v2
    [*] --> LoginPage
    LoginPage --> IntermediatePage : Click Registration Button
    IntermediatePage --> RegistrationPage : Click Customer Button
    RegistrationPage --> EnterDetails : Display Registration Fields
    EnterDetails --> SubmitRegistration : Enter Details
    SubmitRegistration --> ByDSendsContactNumberToCommerce : Details Goes To ByD
    ByDSendsContactNumberToCommerce --> SignInPage : Commerce Saves The Contact Number
    SignInPage --> RequestOTP : Enter Mobile Number
    RequestOTP --> EnterOTP : Click Request OTP
    EnterOTP --> VerifyOTP : Enter OTP
    VerifyOTP --> LoggedIn : OTP Verified
    LoggedIn --> [*]
```