### Steps

- Download the [cli](https://developer.salesforce.com/tools/salesforcecli)
- Authorization:  `sfdx auth:web:login`
- Command to list the authenticated org detail, you can futher use the token returned by this command to use the SF API
  ```
  sfdx force:org:display -o {your_email}
  ```
- Example command to fetch all my cases: the OwnerId is your SF id, you can find it in the url on your user page
  ```
  sfdx force:data:soql:query --query \"SELECT Id, CaseNumber, Account.Name, Subject, Status FROM Case WHERE OwnerId={user_id} AND IsClosed = false\" -o {your_email}
  ```
- Example command to fetch case details by id
  ```
  sfdx force:data:record:get -o {your_email} -s Case -i {case_id}
  ```
