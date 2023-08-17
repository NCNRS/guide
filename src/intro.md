# Welcome to Night City
`Night City` provides automated red team infrastructure deployment, monitoring, and an easy to use inteface for executing an offensive campaign.

You can run a full setup on a single computer or easily scale different parts by adding different services on other servers. All the setup and communication is handled by `Night City` so you don't have to worry about the different challenges that come with scaling distributed systems.

# Services 
`Night City` is composed of many different services that work together and can be scaled up or down depending on your needs. The following repositories make up Night City.

## Cyberdeck
This is the main UI that you'll interact with. From here you can see the status of all your machines and services. You can also launch automated attacks against targets, scale your services, and monitor your progress. 

The UI allows you to quickly gain an overview your entire operation while also being able to drill down into the logs of all the tools used if needed.

## Fixer
This service is what enables `Night City` to easily manage and scale services across multiple machines. It is a message queue that is responsible for coordinating all the tasks and services.

Most operations are started from the `Cyberdeck` and sent to the `Fixer` which then forwards them to the correct service that can run the job. After the job is done the results are sent back to the `Fixer` which in turn sends them to the `Cyberdeck`. Then the reaulta are processed and made available through the GUI.

## Quickhacks
Quickhacks can be automatically ran from the `Cyberdeck`. Many of the `Quickhacks` are open source programs you are familiar with ran in a docker container. This just adds a thin wrapper around them to perform additional post-processing and to make them compatiple with the `Fixer`.

This means that `Quickhacks` can easily be scaled up and down across multiple servers, so if you need extra processing power for just a short amount of time you can easily add more for a specific task.

## Rockerboys
These are phishing servers that allow you to quickly deploy phishing sites and tools that look legitimate. You can also mamage other types of phishing campaigns though these services.

## Operators
These are your C2 servers and their related infrastructure. From these services you can manage all your compromised devices via implants. 

A number of different C2 servers are supported and more are being added.

## Datachips
This service lets you upload a `datachip` and indexes it and makes it full text searchable through the `Cyberdeck` UI.

We provide several different datachips such as:
- CVEs
- CTF writeups
- Security blog posts

The main benefit of datachips is that it allows full text search of these sources directly available in the `Cyberdeck` UI rather than trying to hunt down related information from google.







