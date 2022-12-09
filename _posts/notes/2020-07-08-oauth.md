---
title: "oauth"
date: 2020-07-08
draft: true
tags: ["other"]
---

OAuth 2.0 vs OAuth 1.0

- OAuth 2.0 complete rewrite of OAuth 1.0 from ground up, sharing only the overall goals and general user experience.
- OAuth 2.0 is not backwards compatiable.
- OAuth 2.0 - completely new protocol.

---

OAuth and APIs

REST is, in a nutshell, HTTP commands pushing JSON packets over the network.

Developers build a lot of APIs. The API Economy is a common buzzword you might hear in boardrooms today.
Companies need to protect their REST APIs in a way that allows many devices to access them.
In the old days, you’d enter your username/password directory and the app would login directly as you.
This gave rise to the delegated authorization problem.

“How can I allow an app to access my data without necessarily giving it my password?”

---

OAuth is a delegated authorization framework for REST/APIs. It enables apps to obtain limited access (scopes) to a user’s data without giving away a user’s password. It decouples authentication from authorization and supports multiple use cases addressing different device capabilities. It supports server-to-server apps, browser-based apps, mobile/native apps, and consoles/TVs.

You can think of this like hotel key cards, but for apps. If you have a hotel key card, you can get access to your room. How do you get a hotel key card? You have to do an authentication process at the front desk to get it. After authenticating and obtaining the key card, you can access resources across the hotel.

To break it down simply, OAuth is where:

1. App requests authorization from User
2. User authorizes App and delivers proof
3. App presents proof of authorization to server to get a Token
4. Token is restricted to only access what the User authorized for the specific App

https://developer.okta.com/blog/2017/06/21/what-the-heck-is-oauth#saml

https://auth0.com/docs/getting-started/overview
