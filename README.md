# Let Salesforce talk to Google APIs

1. Get a Google service account with API access and credentials
2. Convert p12 file to jks, have a working jdk installed (I use openjdk)
   `keytool -importkeystore -srckeystore ./serviceaccountfilename.p12 -destkeystore googlecalendarapiserviceaccount.jks -srcstorepass notasecret -srcalias privatekey -srcstoretype pkcs12 -deststoretype jks -destalias googlecalendarcertificate -deststorepass notasecret`
3. Create Remote Site Setting for `https://www.googleapis.com`, Identity Provider and upload jks to Key Manager
4. Have fun with GoogleApi Class after editing header variables. This is the only class in this repo. 
5. This is just an example. Do not use in production.

# Resources

- (Details on Setting Up a Service Account)[https://support.google.com/a/answer/7378726?visit_id=637790410769497914-3552970873&rd=1&src=supportwidget0&hl=en]
- (Google Cloud: Calling Protected Cloud Function from Salesforce)[https://cloud.google.com/architecture/calling-protected-cloud-functions]
