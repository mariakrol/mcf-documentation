# MCF Requirements and Concerns by Subdomain
The main domain of the MCF product is to help solve everyday routine tasks for cat clients.
According to the initial requirements, the main domain can be divided into several subdomains associated with related 
problems:

- **Service order processing**

    The point of contact between the MCF system and the end user. The subdomain solves the problem of service orders.
    The scope of the subdomain covers all steps of the order lifecycle, from creation to readiness to delivery.

- **Finding the Right People and Calculating Costs**

    This subdomain solves the problem of intellectual search for workers and calculation of costs based on an order and
    a worker. It is divided into a separate subdomain from other parts of order preparation because it is known that a 
    separate team works on it, and they have a separate language.

- **Provision of consumables for orders**

    This subdomain solves the problem of interaction with the warehouse. It is separated from the subdomain, which deals 
    with the created order because the set of actors is different. Warehouse stuff does not interact with order lifecycle,
    at the same time service managers and end users do not interact with consumables.

- **Provision of ordered service**

    This subdomain solves a service provisioning problem. It is separated from another subdomain that handles order to 
    provision because this part is outside the system. The problem is solved by an employee in "external environment".

- **Provision of payments**

    All calculations must be done separately, closer to the context of a payment, because the logic of discounts and 
    payments to end users are completely different from the logic of payments to workers. These algorithms are 
    different, but the logic of payment provisioning is completely the same: we just prepare a sum and payment system 
    and delegate to a payment provider.

- **Hiring the Best Workers**

    One of the most important parts of the MCF system. On the one hand, the success of the MCF business depends entirely
    on the quality of hiring, and on the other hand, this part is sold as a separate product. So it has to be absolutely
    independent.

- **Customer Loyalty**

    Loyalty program can be modified or expanded at any time without affecting other parts of the system.

- **Manager motivation**

    This part is semi-secret. Since it can be a source of conflict in the rest of the team will know about it. So the 
    part is developed by a separate team and only management is aware of it.

- **Motivation of workers**

    Since the quality of workers' job is the key of success of MCF, it is important to motivate workers to do the best 
    job they can. can. As for loyalty, the bonus system should be changed separately and should not affect other parts.