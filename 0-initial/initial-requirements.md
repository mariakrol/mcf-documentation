# Context and Problem
The Happy Cat Box Company, a non-automated company, noticed that after three months of operation, the testers cats were 
working with less efficiency. The number of toys tested dropped from five per day in the beginning to one per day after 
three months. After some anonymous surveys, the company discovered that the main reason was fatigue: the cat testers 
spend all their energy on work, after which they cannot do their usual things, such as scratching, dropping glasses from
surfaces, etc., which makes them even more tired.
To solve this problem, the Happy Cat Box Company decided to establish a subsidiary company, Make Cats Free (MCF), whose
main purpose would be to reduce the unnecessary work of the test cats. To that end, MCF will help delegate the routine 
tasks of poking and jar tossing to a carefully selected pool of workers consisting of the best of the cat breed (the top
3% of talent among cats). The workers will be paid, and the client cats will pay us for our services.
MCF plans to use the most advanced algorithms for screening workers and the most advanced matching between cat clients 
(for now, only Happy Cat Box testers, but the company plans to expand in the future) and workers. With screening and 
matching, the company plans to differentiate itself from the competition. To do this, it plans to implement the project 
from scratch according to the given requirements. Money is not critical at the moment, the Happy Cat Box is ready to 
spend as much as it will take. The development team will be assembled after our analysis of the required system.

# Requirements list
- `[US-010]` All tester cats (clients) are automatically logged into the system. They will see a dashboard with ordered 
services and a "Request Help" button.
- `[US-020]` When requesting a service, clients will see a form where they can describe what needs to be done, select the 
type of service, and see the approximate cost.
- `[US-021]` Service types are set in the admin by managers.
- `[US-030]` Any completed or canceled task should be paid in full by the user.
- `[US-031]` Update (15/05): Failed tasks must also be paid in full by the client.
- `[US-040]` If the client has paid more than 10k conventional cat-units in total, he gets a 5% discount, if more than 
20k 6% discount. For each 10k, the discount increases by 1%, up to a maximum discount of 12%.
- `[US-050]` The cost is determined after selecting the vendor for the service (matching). The cost calculation is given
by a secret formula that nobody knows yet, so for the first version, it is enough to set a constant value of 100 
conditional cat-units for each service.
- `[US-060]` The people who came up with the unique matching system uses different terms than the rest of the company: 
"reference sample" (customer) and "normal sample" (worker). No one knows how this came about, but the algorithm developers 
refuse to retrain.
- `[US-070]` The matching algorithm, which is common to each sample, consists of a series of steps that calculate ratings 
and other values. The system is somewhat similar to map-reduce. The developers decided to implement all the logic 
themselves in any language since they don't want to share the algorithm. Our goal is to use the implemented steps in the 
order we want, which can sometimes change while being able to add or edit steps as we need them.
- `[US-071]` Matching needs information about workers (including their strengths and weaknesses) and past results to work 
properly.
- `[US-072]` Matching takes a task and a client and returns the best candidate for the task. It is this candidate that the 
system automatically assigns to the task. And calculates the cost of the service.
- `[US-073]` Updated (12/05): Matching always gets a worker, there are no situations where no worker is found for the task.
- `[US-080]` Every cat that wants to become an MCF worker must be tested so the company can be sure that the cat is in the 
top 3% of cats in the world.
- `[US-081]` We expect 1k applications a day from random cats, also, based on feedback, our competitors may try to DDoS us 
at this point. They've done this to other companies many times before, and the companies closed in disgrace.
- `[US-090]` To be tested, you must leave an application on the website, after which a manager will contact the cat and 
assign a series of tests to assess the potential candidate's level.
- `[US-110]` Managers should be able to configure a set of tests for each individual cat
- `[US-120]` Based on the results of the tests, the cat is either added to the general pool of workers with the resulting 
characteristics (strengths/weaknesses) and other information about the cat (name, age, breed, coat color, photo), or 
rejected.
- `[US-130]` If the worker doesn't come to the job for any reason, the job is automatically rejected and the customer is 
offered to place a new order (essentially a copy) for another convenient date. A new worker is added to the order.
- `[US-131]` Updated (12/05): for a canceled task, the client pays the full price as described in `[US-030]`, for a 
created copy, the client pays the new price again.
- `[US-132]` Updated (12/05): When a new order is created after a cancellation, the user must manually select a new 
convenient date. Then the order is automatically matched according to an innovative matching system. After that, the 
order lives and works like any other order.
- `[US-140]` The Worker can see a list of active jobs for him to help with, as well as a list of completed and canceled 
jobs.
- `[US-150]` Before starting a job, the worker must obtain the supplies needed for the job, including the Job Acceptance
Form. To do this, we need to tell the Supplies Department who and what we need the supplies for.
- `[US-160]` The supplies department workers collect their own orders as they like, we only need to notify the workers
of a new order and provide an "issued" button under each order.
- `[US-170]` Thinking about what else to add to increase customer loyalty, top management decided to use the LLM-based 
catGPT-4, which suggested adding fur-tune cookies to each customer's order with a predicted future. To do this, the 
company found a contractor to prepare the cookies and bring them to the consumable assembly department on each customer's 
order. To get the cookies to the customer, the customer's information is sent to the contractor, and in 10 minutes the 
cookies arrive at the warehouse, where employees place them in the correct set of supplies. Even though it seems strange 
to get each cookie for a customer one by one, we decided to use this company anyway.
- `[US-180]` When the worker arrives at the right time for the order - he needs to check in the application (send a photo 
and click "Continue"). At the end of the work must send a photo of the paper report with the customer's signature that 
everything is done and there are no complaints.
- `[US-190]` Managers can randomly select any completed job and check the quality of work done. To do this, they study
all the information about the worker's work. Sometimes they can call the customer.
- `[US-200]` All canceled or failed jobs are automatically sent to the department to study the quality of work. Managers 
try to understand what happened and how to correct the situation. To do this, they may contact the customer.
- `[US-210]` The result of the quality check is entered into a separate form, which provides the company with a set of 
hypotheses for business improvement.
- `[US-220]` Every week (on Sunday), an amount equal to the total cost of the requested tasks is deducted from the client. 
An invoice is issued for this, and then the write-off process takes place through the method specified by the client.
- `[US-230]` On the last day of the month, the amount equal to the total payments minus any fines for the current month
is charged to the worker. An invoice is issued for this purpose, and then the crediting process takes place through a 
Gold Hat (a unique money transfer service that is not connected to the Gold Crown in any way).
- `[US-240]` The worker receives 60% of the cost of the completed task, canceled tasks are not paid to the worker, for 
failed tasks the worker receives a penalty of 40 conditional cat-units.
- `[US-250]` Client and worker should see a list of everything that has been charged or credited to them.
- `[US-260]` You must show how much money the client will owe at the end of the current week, as well as a list of all
past invoices and their payment status. For the worker, you need to show how much he has earned, penalties, and also
invoices with their status.
- `[US-270]` Sometimes the manager can credit any amount of money to a selected worker at his discretion. You need to 
know who credited the money and for what.
- `[US-280]` To solve the problem of low motivation for MCF managers, a betting system was invented. This system allows 
managers to bet their money on the outcome of each order. We hope this will attract more people to the company. Only 
managers, of which there will be no more than 15, will be able to place bids. We do not expect a large number of bids due 
to the total number of orders.
- `[US-281]` Updated (12/05): We trust the managers, so they divide the money among themselves if they lose and if they 
win. If they all lose, the bank goes to the developers.