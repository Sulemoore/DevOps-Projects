#### Step 1: Update S3

- Go to S3 and open the bucket created by Elastic Beanstalk

![Screenshot 2023-09-21 at 11 41 45 PM](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/809d8a06-fca0-48a5-8d0e-a6fa52018acc)

- Select the object "resources" and then click permissions

![Screenshot 2023-09-21 at 11 42 33 PM](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/1917c09a-f2b5-420c-91dd-8a7011daf492)

- Go ro Edit Object Ownership - Select ACLs enabled and Save.

![Screenshot 2023-09-21 at 11 43 03 PM](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/63d1e6e7-2984-4684-900a-2a51aa91ece4)

![Screenshot 2023-09-21 at 11 43 12 PM](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/bfe05144-a405-4357-a71c-28289f0d7613)

![Screenshot 2023-09-21 at 11 47 53 PM](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/852def0a-343e-4b51-a7a8-b38cd249f4a6)


#### Step 2: Update Elastic Beanstalk

- Go to EBStalk and click on configurations on the left

 ![Screenshot 2023-09-21 at 11 52 33 PM](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/2633bf19-d3aa-49fa-9678-413629f554fe)

- Click on edit instance traffic and scaling

![Screenshot 2023-09-21 at 11 53 05 PM](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/e514cde6-70bd-4afb-adcf-d531b87d552b)

- Go down all the way to Processes, check the radio button - Actions - Edit.
- Drop down Healthcheck and go down to Path.
- Append /login

![Screenshot 2023-09-21 at 11 55 57 PM](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/38f43022-7980-472d-ad90-346c2634a389)

  
- Go down to Sessions and enable session stickiness

![Screenshot 2023-09-21 at 11 57 49 PM](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/5211aa49-b01d-45ae-8b48-61b9baa1aa84)

- Add Listener

  #### Step 2: Security Group
  - Add the Security group of the Instances created by the Beanstalk to intereact with the Backend Security group

![Screenshot 2023-09-22 at 12 10 35 AM](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/5d00d5ae-2488-48de-a3f0-b9bea833b97b)

  - Add more rules
![Screenshot 2023-09-22 at 12 12 20 AM](https://github.com/Sulemoore/DevOps-Projects/assets/101164153/dd954464-2b44-490d-9f12-8f763f73a663)
