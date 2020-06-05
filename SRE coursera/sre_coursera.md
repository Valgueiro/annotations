# Site Reliability Engineering

## CRE
CRE - Costumer Reliability Engineering
Costumers need to know your SLO's to know what to expect from your service.
If they know your SLO's they can properly calculate theirs.
This communication can remove some friction between you and your costumers

It's good to note that Users decide the reliability on the end.

To calculate what is your "time to repair an error" we can take the reliability percentage and multiply by a certain amount of time.

Ex: 99.9% means that we will have 40 minutes repair time on a 28-day period

With this we can see that, by adding just another 9, our time to repair becomes a lot lower (4 min).

## SLOs for business

SLO's - service level objective

it can answer to the business when it should prioritize it over new features.
The right rate of reliability is based on your users.

SLO's can change based on different events. FOr example, on a black friday the e-commerce might want to have a higher SLO to not lose any sell. So the SLO is higher just on this specific time.  
It's good to note that we can not have 100% reliability. This percentage should be ambitious but achievable. And the SLO's should be consistently reviewed 


## SLOs and SLAS

SLAs - service level agreement, is the agreement between the org and the user about you service reliability. If those are violate, it will have monetary consequences.

So, the best practice is to define a higher SLO (that is an internal metric) to never get on a point where a SLA is violated.

When the SLO's starts to be violated, we should hold up new features to fix this issues.


## Measuring Reliability

SLI - service level indicators. Define metrics to quantify reliability of your system. This should be used to calculate SLO's and SLA's


## Error budget

Error budget is basically the opposite of SLO. It's the percentage that you have to spare with errors before your slo's is violated. This is a good metrics to the SRE teams to hold up new features or not.

Developers can self-regulate and manage risk better with error budgets, it helps to balance development velocity and reliability.

There is a good techniques that can be applied when there are no more error budget but the dev team still need to release a new feature. We can give a set of tokens to senior developers that can be used to roll out something even when the SLO is violated. So, only a critical and very high priority bug needs to be fixed is that it wil be able to go to prod when there is no error budget.

Also, error budget alerts are very good to maintain everyone knowing who the system is performing.


# Setting targets for reliability

Your error rate is proportional to those variables: 
* TTD - time to detect
* TTR - time to resolution
* impact - percentage of your impacted users
* TTF - time to failure (how frequent the failure occurs) same as TBF


![Error rate](error_rate_proportional.png "Error rate")


1. Lower the TDD - pings a human instead of requiring manual investigation to see if there is a failure or monitoring your SLO's complaints.

2. Improve TTR - develop a playbook or change the zone automatically when there is a failure so you have time to fix the bug

3. Reduce impact - limit the number of users that receives a change on certain amount of time
