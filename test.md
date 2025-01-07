graph TD
    Start["Start"] -->|Created Account?| CreatedAccount{Created Account?}
    CreatedAccount -->|Yes| RegainAccess["Help regain access"]
    CreatedAccess -->|Login.gov| LoginGovAccess["Login.gov: Trouble signing in?"]
    CreatedAccess -->|ID.me| IDmeAccess["ID.me: I can't sign in?"]
    CreatedAccount -->|No| EmailCheck["Unique Email?"]
    EmailCheck -->|Yes| AccountType["Choosing Account Type"]
    EmailCheck -->|No| SetupEmail["Set up email"]
    AccountType -->|SSN?| SSN{SSN?}
    SSN -->|Yes| PhoneOrAddress{Phone/Address?}
    SSN -->|No| IDmeNoSSN["ID.me (Video Call)"]
    PhoneOrAddress -->|Yes| StateID{State ID?}
    PhoneOrAddress -->|No| IDmeNoPhone["ID.me (Video Call)"]
    StateID -->|Yes| IDUpload{ID Photos?}
    StateID -->|No| Passport{Passport?}
    Passport -->|Yes| IDmePassport["ID.me"]
    Passport -->|No| OtherID{Other ID?}
    OtherID -->|Yes| IDmeOtherID["ID.me (Video Call)"]
    OtherID -->|No| NoDocs["Get Docs or Contact Info"]
    IDUpload -->|Yes| AccountPref{Preference?}
    IDUpload -->|No| Verification{Verification Method?}
    Verification -->|Video| IDmeVideo["ID.me (Video)"]
    Verification -->|In-Person| LoginGovInPerson["Login.gov (In-Person)"]
    Verification -->|No Pref| AccountPref

    AccountPref -->|Gov| LoginGov["Login.gov"]
    AccountPref -->|Non-Gov| IDme["ID.me"]
    AccountPref -->|No Pref| Both["Both Options"]

    LoginGov --> MFA_LoginGov["MFA Login.gov"]
    IDme --> MFA_IDme["MFA ID.me"]

    MFA_LoginGov -->|Gov Employee?| GovEmployee{Gov Employee?}
    GovEmployee -->|Yes| PIVorCAC["PIV/CAC + Another"]
    GovEmployee -->|No| SecurityKeyLoginGov{Security Key?}
    SecurityKeyLoginGov -->|Yes| SetupSecurityKey["Setup Security Key"]
    SecurityKeyLoginGov -->|No| MobileDeviceLoginGov{Mobile Device?}
    MobileDeviceLoginGov -->|Yes| AppOrUnlock["App or Unlock"]
    MobileDeviceLoginGov -->|No| LandlineLoginGov{Landline?}
    LandlineLoginGov -->|Yes| PhoneCodesLoginGov["Phone Codes"]
    LandlineLoginGov -->|No| BackupCodesLoginGov["Backup Codes"]

    MFA_IDme -->|Security Key?| SecurityKeyIDme{Security Key?}
    SecurityKeyIDme -->|Yes| SetupSecurityKeyIDme["Setup Security Key"]
    SecurityKeyIDme -->|No| MobileDeviceIDme{Mobile Device?}
    MobileDeviceIDme -->|Yes| MFAOptionsIDme["Code Generator, Push, Passkey"]
    MobileDeviceIDme -->|No| OtherDeviceIDme{Other Device?}
    OtherDeviceIDme -->|Yes| PasskeyIDme["Passkey"]
    OtherDeviceIDme -->|No| LandlineIDme{Landline?}
    LandlineIDme -->|Yes| PhoneCodesIDme["Phone Codes"]
    LandlineIDme -->|No| BackupCodesIDme["Backup Codes"]

    SetupSecurityKey --> End["End"]
    AppOrUnlock --> End
    PhoneCodesLoginGov --> End
    BackupCodesLoginGov --> End
    SetupSecurityKeyIDme --> End
    MFAOptionsIDme --> End
    PasskeyIDme --> End
    PhoneCodesIDme --> End
    BackupCodesIDme --> End
