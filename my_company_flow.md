```mermaid

stateDiagram-v2
    [*] --> HomePage
    HomePage --> MyCompanyDropdown: Click "My Company" dropdown
    
    state MyCompanyDropdown {
        [*] --> Options
        Options --> ViewAllUsers: Select "View All Users"
        Options --> AddOperator: Select "Add Operator"
    }
    
    ViewAllUsers --> DisplayUsersList: Show list of all users
    DisplayUsersList --> [*]
    
    AddOperator --> DisplayAddOperatorForm: Show add operator form
    DisplayAddOperatorForm --> SubmitForm: Fill and submit form
    SubmitForm --> UpdateUsersList: Add new user/operator
    UpdateUsersList --> [*]

```