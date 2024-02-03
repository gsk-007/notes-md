## Topics 
- HTTP vs HTTPS
- How to set up Google search console
- How to set up Google analytics
- What is a sitemap and how to create one
- Duplicate content
- 404 pages, 301 redirects
- How to diagnose your site for Keyword Cannibalization
- Schema mark up

# HTTP vs HTTPS
HTTP = Hypertext Transfer Protocol
HTTPS = Hypertext Transfer Protocol Secure

The traditional HTTP method transmitted information as clear for all to see as if it was jotted down on a piece of paper (in plain text).
The new protocol uses secure socket layer (SSL) and transport layer security (TLS) to encrypt any information being transmitted.
Meaning that it's relatively difficult, if not impossible, to read if and when intercepted.

# How to set up Google search console
It is a platform that Google provides you with and allows you to see tons of information about your website 
- how the website is indexed in Google 
- how we can optimize the visibility of our website 
- to track any issues

# How to set up Google analytics
There are two different versions of GA
1. Universal Analytics (GA3)
2. Google Analytics 4 (GA4)

Google Analytics 4 is not an upgrade to Universal Analytics 

## Difference between GA3 and GA4?
### GA3
GA3 uses the measurement model which is based on **sessions** and **pageviews** to track data.
As GA3 uses a **session-based-model**, the analytics collects and stores information like pages views, events and transactions as hits.

### GA4
GA4 uses the model which is based on **events** and **parameters**.
For example, in GA4, even a "page view" is considered as an event.

Essentially, GA4 uses an **event-based model** to track data.

# What is a sitemap and how to create one

An XML sitemap is a file that lists out all of the URLs we have on our website.
Using `Yoast SEO` tool in WordPress websites 
# Duplicate content
Duplicate content is content that appears on the Internet in more that one place.
That "one place" is defined as a location with a unique website address (URL).
If the same content appears at more that one web address, you've got duplicate content.

## Why does duplicate content matter?
1. They don't know which version(s) to include/exclude from their indexes.
2. They don't know which version(s) to rank for query results.

`Siteliner` - tool for checking your site for duplicate content

# 404 pages, 301 redirects
A 404 page is also known as an "error page" or "Page Not Found" page.

This page indicates that the user reached the domain they requested, but the URL path provided no information.
404 pages are bad because:
1. They result in a bad user experience
2. Wasted link juice(if popular)

Best way is to use a 301 redirect to the relevant content.

We can find the 404 pages under `Coverage` tab under `Index` in the google search console.

A 301 redirect indicates the permanent moving of a web page from one location to another.
The 301 part refers to the HTTP status code of redirected page.
When to use 301 redirects:
1. Redirecting 404 pages
2. When we want to combine 2 pages into one
	1. Consolidation of Authority
	2. Better content


# How to diagnose your site for Keyword Cannibalization
Keyword cannibalization is when a single website unintentionally target the same keyword across multiple pages.
When we spot this, we have 2 options:
1. De-optimize one of the pages to stop it competing
2. 301 redirect one of the pages to the other

- Using `SEMrush`

# Schema mark up
Schema markup is code that you put on your website to help the search engines return more informative results for users.
If you've ever used rich snippets, you'll understand exactly what schema markup is all about.

![[Pasted image 20231219220131.png | 300]]

## Schema Facts

1. Schema tells the search engines what your data means, not just what it says
2. Schema markup uses a unique semantic vocabulary in microdata format.
3. Schema.org, the website for schema markup, was created by a collaborative team from Google, Bing, and Yahoo.
4. Schema markup was invented for users

## Schema mark up types
- Articles
- Local businesses
- Restaurants
- TV episodes and ratings
- Item reviews
- Movies
- Software applications
- Events
- Products

Use a schema plugin for WordPress website

After adding the schema we can test that using the `Structured Data Testing Tool` by Google
