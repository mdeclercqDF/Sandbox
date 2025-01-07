```mermaid

graph TD
    A[Start] --> B{Have you created Login.gov or ID.me account before?}
    B -->|Yes| C[Help access original account]
    B -->|No| D[Ensure unique email address exists]
    
    D --> E{Do you have a U.S. SSN?}
    E -->|Yes| F{Do you have U.S. phone number or address?}
    E -->|No| G[Recommend ID.me for non-U.S. SSN]
    
    F -->|Yes| H{Do you have state ID?}
    F -->|No| I[Recommend ID.me for non-U.S. contact]
    
    H -->|Yes| J{Are you willing to upload ID pictures?}
    H -->|No| K{Do you have U.S. Passport?}
    K -->|Yes| L[Recommend ID.me - Use U.S. Passport]
    K -->|No| M{Do you have other IDs?}
    
    M -->|Yes| N[Verify with ID.me video]
    M -->|No| O[Can't verify - Suggest VHIC]
    
    J -->|Yes| P{Do you prefer government or non-government account?}
    J -->|No| Q{Would you prefer video or in-person verification?}
    Q -->|Video| R[ID.me Video Chat]
    Q -->|In-person| S[Login.gov In-person]
    
    P -->|Government| T[Login.gov]
    P -->|Non-Government| U[ID.me]
    P -->|No Preference| V[Explain both options]
    
    T --> W[Choose MFA for Login.gov]
    U --> X[Choose MFA for ID.me]
    
    W -->|PIV/CAC| Y[Use PIV/CAC]
    W -->|Security Key| Z[Use Security Key]
    W -->|No Security Key| AA{Smartphone?}
    AA -->|Yes| AB[Authenticator App or Face/Touch Unlock]
    AA -->|No| AC{Landline?}
    AC -->|Yes| AD[Phone Call Codes]
    AC -->|No| AE[Backup Codes]
    
    X -->|Security Key| AF[Use Security Key]
    X -->|No Security Key| AG{Smartphone?}
    AG -->|Yes| AH[Authenticator App or Push Notification]
    AG -->|No| AI{Tablet/Desktop?}
    AI -->|Yes| AJ[Passkey]
    AI -->|No| AK{Landline?}
    AK -->|Yes| AL[Phone Call Codes]
    AK -->|No| AM[Backup Codes]

    C --> AN[End]
    O --> AN
    S --> AN
    V --> AN
    Y --> AN
    Z --> AN
    AB --> AN
    AD --> AN
    AE --> AN
    AF --> AN
    AH --> AN
    AJ --> AN
    AL --> AN
    AM --> AN
