Server Outage Incident report
By Elijah Efe-osadolor (Efex16)



21st February 2023, we experienced server outage on all our server infrastructure which resulted in our clients inability to use our services and we sincerely apologize for the financial loss our clients have incurred during this period.

Issue Summary


On 21st February, 2023 (11am GMT + 1), we experienced a server outage on all of our server infrastructure which lasted for 52 minutes. As a result of this, our clients experienced a http 500 error which had a 100% impact on their business as they were unable to access our services, which was brought to our notice by our call service representative at the said time. The root cause was not properly testing out all implemented upgrades before pushing to production servers.


Root cause


At 10:45am (GMT + 1) server upgrade was initiated across all our production servers without first releasing on our test environments because we want to beat downtime and return the server back on operation. We did'nt perform all necessary unit testing. Part of the upgrade been shipped to production server required an authentication from a 3rd party software, this new implementation is not supported on the current version present on our servers which resulted in the downtime experienced. We were able to resolve this quickly by first performing a rollback before upgrading with required authentication.


Preventive measures


Pushing all intended changes 1st to our test environments before shipping to life server.
Increase the performance metrics threshold to alert on-call engineers on the event of possible server crash
