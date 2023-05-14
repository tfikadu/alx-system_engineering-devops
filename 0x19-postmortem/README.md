Postmortem 
Failing is normal and failing is actually a great opportunity to learn and improve. Any great Software Engineer must learn from his/her mistakes to make sure that they won’t happen again. Failing is fine, but failing twice because of the same issue is not. A postmortem is a tool widely used in the tech industry. After any outage, the team(s) in charge of the system will write a summary that has 2 main goals:
To provide the rest of the company’s employees easy access to information detailing the cause of the outage.
And to ensure that the root cause(s) of the outage has been discovered and that measures are taken to make sure it will be fixed.
For this school project, I created an imaginary situation that didn't happen to any of the projects that I've contributed to. But it's a good example to help other developers and the ones starting their career in the Software Engineering field avoid some similar disastrous situation and to valorize the significance of Postmortem.
CASE
I was developing an application for a type of query with GraphQL and ReactJS using Apollo as a client, where some types of responses were tested by a Lambda AWS. 


Issue summary
On 12/05/2023 Starting from 10:35 PM EAT until 11:42 AM EAT, The entire application stopped working, the user interface did not allow any action, and they only showed code errors


Apparent Reason
A badly installed update of the apollo client was damaging the data query to be brought from the server to the client


Timeline
The following events took place on Friday, May the 12th, 2023:
10:35 pm -The problem was detected because the application did not show any data in its interface, data that is loaded by GraphQL queries brought from the Lambda AWS
10:45 pm - First it was verified that the base code in the interface had not been altered in any of the Reactjs components
10:57 pm- Second, the integrity of the Lambda service was verified.
11:15 pm - Third-party test integrity of queries, APIs between client and server
11:40 pm - All the dependencies were reinstalled, one by one and we began to test the application in each one.
11.46 pm - In the end a dependency was not downloaded correctly and generated a runtime error for Apollo, which affected the integration of queries between client and server
Root cause and Resolution
The interruption of the service was caused by a dependency called Apollo, which allows integrating the GraphQL and Lambda queries, the Apollo was in version 2.0 and happened to be installed in its most recent version 3.0, but the download had problems and generated the unit will be installed correctly. Fortunately it was just a matter of reinstalling that dependency and normalizing the service.


Issue Image




