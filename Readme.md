
POST Operation (Create)
<img width="1600" height="728" alt="image" src="https://github.com/user-attachments/assets/92f6c140-69f3-4c95-aaef-4560022e2d98" />

GET Operation (Read)
<img width="1600" height="384" alt="image" src="https://github.com/user-attachments/assets/c76de713-88f3-412e-879e-dd0bb77c652a" />

DELETE operation : 
<img width="1600" height="758" alt="image" src="https://github.com/user-attachments/assets/facb9059-d5ac-4315-b92b-52983e1c9231" />




Dynamo DB Snapshot:
<img width="1700" height="1298" alt="image" src="https://github.com/user-attachments/assets/9a612f63-68e1-460c-b884-ccf72091a73c" />



Challenges : 
Setting up a simple CRUD with AWS Lambda and DynamoDB was trickier than I expected, mostly because of the wiring, not the code. I kept getting 500s until I realized queryStringParameters and body can be None, my TABLE_NAME env var wasn’t set, and my role didn’t have the right DynamoDB permissions. Using CloudWatch logs to print the incoming event helped me see what the API Gateway was actually sending. I also learned DynamoDB is key-based (no joins or auto-increment), so everything revolves around the partition key, and curl was the easiest way to test each method. Overall, I learned to be careful with event shapes, permissions, and simple checks before blaming the code.
