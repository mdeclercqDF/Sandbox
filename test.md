graph TD
    Start -->|Have you created a Login.gov or ID.me account before?| CreatedAccount{Created Account?}
    CreatedAccount -->|Yes| RegainAccess[Help regain access to existing account]
    RegainAccess -->|Login.gov| LoginGovAccess["Login.gov: Trouble signing in?"]
    RegainAccess -->|ID.me| IDmeAccess["ID.me: I can't sign in to my account"]
    CreatedAccount -->|No| Section2[Email Address Check]
    
    Section2 -->|Do you have a unique email address?| UniqueEmail{Unique Email?}
    UniqueEmail -->|Yes| Section3[Choosing Account Type]
    UniqueEmail -->|No| SetupEmail[Set up a unique email account]

    Section3 -->|Do you have a U.S. Social Security number?| SSN{US SSN?}
    SSN -->|Yes| PhoneOrAddress{US Phone/Mailing Address?}
    SSN -->|No| IDmeNoSSN[Recommend ID.me (Video Call for Non-US)]
    IDmeNoSSN -->|Documents Not Available| NoDocs[Assist with Veteran Health ID or contact info]
    
    PhoneOrAddress -->|Yes| StateID{State-issued ID?}
    PhoneOrAddress -->|No| IDmeNoPhone["Recommend ID.me (Video Call for Non-US)"]
    IDmeNoPhone -->|Documents Not Available| NoDocs

    StateID -->|Yes| IDUpload{Can upload ID photos?}
    StateID -->|No| Passport{Passport or Passport Card?}
    Passport -->|Yes| IDmePassport[Recommend ID.me]
    Passport -->|No| OtherID{Any other forms of ID?}
    OtherID -->|Yes| IDmeOtherID["Recommend ID.me (Video Call if 2+ IDs)"]
    OtherID -->|No| NoDocs

    IDUpload -->|Yes| AccountPref{Account Preference?}
    IDUpload -->|No| VerificationMethod{Verification Method Preference?}
    VerificationMethod -->|Video Call| IDmeVideo[Recommend ID.me (Video Call)]
    VerificationMethod -->|In-Person| LoginGovInPerson[Recommend Login.gov (In-Person)]
    VerificationMethod -->|No Preference| AccountPref

    AccountPref -->|Government| LoginGov[Recommend Login.gov]
    AccountPref -->|Non-Government| IDme[Recommend ID.me]
    AccountPref -->|No Preference| BothAccounts[Recommend both, review privacy policies]

    LoginGov --> MFA_LoginGov[MFA for Login.gov]
    IDme --> MFA_IDme[MFA for ID.me]

    MFA_LoginGov -->|Gov Employee or Military?| GovEmployee{Gov Employee/Military?}
    GovEmployee -->|Yes| PIVorCAC[Recommend PIV/CAC + Another Method]
    GovEmployee -->|No| SecurityKeyLoginGov{Security Key?}
    SecurityKeyLoginGov -->|Yes| SetupSecurityKey[Setup Security Key]
    SecurityKeyLoginGov -->|No| MobileDeviceLoginGov{Mobile Device?}
    MobileDeviceLoginGov -->|Yes| AppOrUnlock[Recommend App or Face/Touch Unlock]
    MobileDeviceLoginGov -->|No| LandlineLoginGov{Landline?}
    LandlineLoginGov -->|Yes| PhoneCodesLoginGov[Recommend Phone Codes]
    LandlineLoginGov -->|No| BackupCodesLoginGov[Recommend Backup Codes]

    MFA_IDme -->|Security Key?| SecurityKeyIDme{Security Key?}
    SecurityKeyIDme -->|Yes| SetupSecurityKeyIDme[Setup Security Key]
    SecurityKeyIDme -->|No| MobileDeviceIDme{Mobile Device?}
    MobileDeviceIDme -->|Yes| MFAOptionsIDme[Choose from: Code Generator, Push Notification, Passkey]
    MobileDeviceIDme -->|No| OtherDeviceIDme{Other Device?}
    OtherDeviceIDme -->|Yes| PasskeyIDme[Recommend Passkey]
    OtherDeviceIDme -->|No| LandlineIDme{Landline?}
    LandlineIDme -->|Yes| PhoneCodesIDme[Recommend Phone Codes]
    LandlineIDme -->|No| BackupCodesIDme[Recommend Backup Codes]

    SetupSecurityKey --> End
    AppOrUnlock --> End
    PhoneCodesLoginGov --> End
    BackupCodesLoginGov --> End
    SetupSecurityKeyIDme --> End
    MFAOptionsIDme --> End
    PasskeyIDme --> End
    PhoneCodesIDme --> End
    BackupCodesIDme --> End
