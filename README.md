Monolithic Applications Lab Submission
=====================================

This project implements a Monolithic Web Application using FastAPI and SQLite.
It demonstrates performance bottlenecks, load testing using Locust, and code optimization.

The goal of this lab is to:
• Understand monolithic architecture
• Detect slow routes
• Perform load testing
• Optimize inefficient logic
• Compare performance before and after improvements


Technologies Used
----------------
• Python
• FastAPI
• SQLite
• Jinja2 Templates
• Locust (Load Testing)


Project Structure
----------------
main.py              - FastAPI routes
database.py          - Database connection
checkout/            - Checkout logic
templates/           - HTML pages
locust/              - Load testing scripts
insert_events.py     - Sample data loader
requirements.txt     - Dependencies
fest.db              - SQLite database


Application Features
--------------------
• User login and registration
• Event listing
• Event registration
• My Events dashboard
• Checkout system
• Load testing support


Performance Bottlenecks Identified
----------------------------------
/checkout
  Cause: inefficient loops and repeated calculations
  Result: ~4000 ms response time

/events
  Cause: heavy CPU loop (3 million iterations)
  Result: ~2000 ms response time

/my-events
  Cause: dummy computation loop
  Result: ~2200 ms response time


Optimizations Applied
---------------------
• Removed unnecessary loops
• Eliminated dummy computations
• Replaced repeated calculations with direct summation
• Reduced CPU workload


Performance Comparison
-----------------------
Route        Before     After
/checkout    ~4000 ms   ~150–400 ms
/events      ~2000 ms   ~100–200 ms
/my-events   ~2200 ms   ~150–200 ms

Result: Faster responses, lower CPU usage, zero failures under load


How to Run
-----------
Install dependencies:
pip install -r requirements.txt

Start server:
uvicorn main:app --reload

Open browser:
http://localhost:8000


Load Testing (Locust)
----------------------
Run:
locust -f locust/checkout_locustfile.py

Open:
http://localhost:8089


Learning Outcomes
-----------------
• Monolithic architecture concepts
• Performance bottleneck detection
• Load testing with Locust
• Code optimization techniques
• Measuring response time improvements


Author
------
SRN: PES2UG23AM013
Course: Cloud Computing Lab
Assignment: Monolithic Applications Lab

