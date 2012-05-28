# Supported Hosting Services

AppFlower should work fine with most hosting solutions available these days. And if you are in doubt about how to get started you could also just use the hosted and optimized web-stack at appflower.com. Which is built for appflower applications.

## High-end
For higher demands, you should go for a fully stacked web-server environment, we suggest using reverse-proxies, caching, cdn, load-balancing and high-availability on all layers of you deployment. A basic starting point, would be to deploy 2x reverse-proxies (varnish/nginx), 2x web-servers (apache/nginx), 2x database servers. And remember to setup good backup and recovery procedures.

## Low scale
The recommended way of hosting is either a low cost VPS (Virtual Private Server) or a dedicated server (if you're application requires more resources), since these provide more or less full access, and therefore make it is easer to manage and maintain AppFlower applications.

As for shared hosting accounts, the situation is a bit more complex, since these might greatly differ in terms of usability and technology provided. As a rule of thumb, however, we can say that AppFlower works fine with all those hosts where Symfony 1.4 is installed or supported. It's best to ask your hosting company about this to make sure it works with your host too. Should they fail to meet this requirement, you can always find a list of  <a href="http://trac.symfony-project.org/wiki/HostsSupportingSymfony" >Symfony-friendly hosts</a>.

AppFlower.com both provides a high-end scalable solution and low-priced plans, to fit your needs. See http://appflower.com/plans-and-pricing


# Requirements

<a href="http://www.appflower.com/doc/1_2/learn_requirements">Read the requirements for AppFlower.</a>
