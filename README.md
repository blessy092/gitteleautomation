1. Objective
To build an automated workflow using n8n that fetches GitHub repository information, enriches the most popular repository with README details, applies conditional logic, and sends notifications through Telegram.
2. APIs Used
API 1 – GitHub Search API
•	Endpoint: https://api.github.com/search/repositories
•	Method: GET
•	Purpose: Fetch the top five Python repositories based on star count.
API 2 – GitHub README API
•	Endpoint: https://api.github.com/repos/{blessyboban}/{repo}/readme
•	Method: GET
•	Purpose: Retrieve README information for the most popular repository.
Notification – Telegram Bot API
•	Purpose: Send the final repository digest and API error notifications to Telegram.
3. Workflow Components
1.	Schedule Trigger – Executes the workflow every hour.
2.	HTTP Request – Fetches GitHub repository information.
3.	Code Node – Sorts repositories and selects the top five.
4.	HTTP Request – Retrieves README metadata for the top repository.
5.	Code Node – Combines repository information and prepares the digest.
6.	IF Node – Checks whether the featured repository has more than 1,000 stars.
7.	Telegram Node – Sends notifications based on the IF condition.
4. Data Transformation
JavaScript is used to:
•	Sort repositories by star count in descending order.
•	Select the top five repositories.
•	Extract repository name, stars, programming language and URL.
•	Prepare the final Telegram digest.
5. Conditional Logic
The IF node checks whether the featured repository has more than 1,000 stars.
•	True: Sends a popular repository alert.
•	False: Sends a normal repository update.
6. Result
The workflow successfully integrates public GitHub APIs with Telegram through n8n, automating repository collection, enrichment, filtering, conditional processing and notification delivery.

