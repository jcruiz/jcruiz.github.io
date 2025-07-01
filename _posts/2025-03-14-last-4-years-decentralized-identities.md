---
layout: page
title: "Four years immersed in Verifiable Credentials"
date: 2025-03-14 16:45
comments: true
categories: [product management, technology]
published: false
---

Goal: 
- Explain the importance and value of verifiable credentials
- Share a view on the challenges for adoption
- Share a list of case studies of real enterprise adoption
Intro
From the moment that [Heroku](add link to announcement) decided to remove support to free dynos, my site and blog went dark. I've been neglegting(find the right term) to re-start my blog and personal playground for a while but seemed that I could never find continuous, uninterrupted time to focus and get it done until now. One of the things that has kept me busy is the project that I've been working on for the past 4 years at Microsoft that is known today as Entra Verified ID, in this post I share my journey into the universe of Web 3 and Verifiable Credentials, the challenges and some examples of real case scenarios of how companies can add more trust to the web. 
<!--more-->

## What is Verifiable Credential and what's the connection with Web 3
The concept of Verifiable Credentials and underlying technologies can be complex for some. The analogy that I often use is the COVID-19 vaccination record/pass, most of us at some point in the last few years had a physical or digital record issued by a local health authority to proof that you received a COVID-19 vaccine - in other words that's one of your COVID-19 identities. You could present this identity as a proof to other authorities that you were vaccinated.

But how a COVID-19 identity that is issued by let's say, Colombia, could be trusted when you presented at the airport in the Netherlands? as with most of our physical and digital identities, identities can be tampered and even if the identity if your proof the reality is that such identity is technically owned by the issuing party not by you acting as the subject. In order of a given organization (party) to accept an identity from another organization (party) contractual agreements, technology integrations and validations need to be implemented. That comes at a cost... and doesn't take in consideration other types of identities.

You might come across the term "self-sovereign-identities", Verifiable Credentials are a form of self-sovereign identities in which the credentials, the issuers and the verifiers (parties that validate other credentials) are universally identifiable and any credential from a subject can be verified in real time. Without requiring a technical integration, an organization can verify that any claims (information stored in the credential such as name/last name) are present and that the issuing authority (party) is valid. All of this done via the set of public keys that each party pocesses.

So in our COVID-19 vaccination record/pass, the authorities at any airport in the world could validate both the keys and full name details from the subject presenting the credential as well as the keys from the Colombia department of health are valid. In addition, the verifying authority could required for example that the passport name and surname match with the COVID-19 vaccination record/pass claim. Pretty cool nah?

If we take the same concepts to the Web of today, imagine if all profile on twitter can be easily validated or if a Verifiable Credential need to be presented to access banks, services or perfom actions on them. The web could be more trustworthy and all the issues we see around impersonations, fake profies, bots, etc. could be drastically reduced as there are easy ways to validate and create trust. That's what the concept of Web 3 or the Web of trust derives.

## All of that sounds great but how is the adoption of Web 3?


