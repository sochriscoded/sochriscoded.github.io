+++
date = '2026-09-03T15:14:13-06:00'
draft = false
title = 'Building Hard Things'
+++

## To Do Hard Things

One of my favorite poems, Invictus, along with Teddy Roosevelt's speech became one of the most important pieces of literatures in my life. I have learned rather quickly that to become something more, you must be willing to do things that are hard for you in ways you cannot expect.

It is rather blase to say, but there really is no growth is a comfort zone, and as we get better at things, our comfort zone shifts in ways we cannot anticipate. It is part of the reason I am so focused on writing things by hand, pushing myself to keep my skills and abilities, and gaining new or interesting ones as I try new things. =

Thus, I'm going to build an ERP. Or at the least I am going to try.

## What is an ERP?

An Enterprise Resource Planning System is a service that provides all of the resources a company needs to manage their human, material, and customer capital. SAP and WorkDay are good examples of famous or popular ERPs that people use every day. SAP is a broad system that utilizes its own language: ABAP to design build, and handle business logic for everyday use.

## But Why? This is Hell on Earth

I am an SAP Developer by day, yes, please lament me. That means I work with SAP all day, every day and I get to be very familiar with its systems and services. On my first day of work, I was told by my boss that "SAP is an ocean you can spend a lifetime swimming and never explore the full depths of."

Plenty of people will go their whole career without even remotely getting to the bottom of SAP, and working on this system s has helped me realize that there's a lot to learn by mirroring their systems and design as I develop myself into a better engineer.


## Okay, How am I going to do this thing?

## Phase 0: The Language

It's not fun if I just build a kernel. No, I want to build a whole language that resembles, but isn't, ABAP. It will be bytecode/VM style, so that it can run anywhere that Barf Suite (trademark pending) can run.

As it will of course be the best language of all time, and it will be business-oriented, it will be the Best Business Language (BBL) and the mascot will be Drizzled the Bodatious Raindrop (Drizzy for short.)

## Phase 1: Kernal Foundations

**Step 0: Decisions and scaffolding**

I want to start with asking the tough questions, and especically having to grappel with the fact that there are things I don't know yet. In particualar, how will I handle the data? I intend to build a kernal that handles all of the data, services, and base layer, separating the user from the actually DB processes.

SAP's kernal includes:
-	disp+work (main dispatcher process)
-	Work process executables
-	Database library files
-	RFC libraries
-	SAP startup framework
-	ICM/Web Dispatcher components
- ABAP Virtual Machine 

In essense, I am building a large-scale operating system for business data and transactions, while also building a virtual machine for a business-oriented language (yes, I will be doing that too!)

In doing so, I would have to determine Logical Units of Work, how to handle database locks like the SAP enqueue system, whether or not I want a HANA-like system for caching of data (think of redis if you are normal), database connections, among a host of other things.

This will be the most difficult part, as it will push my own abilities in what I know about business systems and services.

To celebrate this momentous undertaking, I will be naming my wonderful system the Business Undersystem Referential Framework (BARF) Suite. Or BARF for short.

Step 1: Session Context and the Message System

SAP is heavily involved in using message-passing as part of its design. As everything stems from this, it will be the first thing I have to build and design initially.

### Step 2: Primitive Types and Data

From there, I will need to determine my primitive types which my ERP will rely on. We use a lot of chars and char-derived types in SAP, and I have to decide if that's something I want to keep.

### Step 3: The Data Dictionary

All of our data, composite or otherwise, will need to be in the data dictionary, something that SAP uses to define everything from people, badge numbers, effective dates, to more complex things like infotype tables and structures. Everything in the system has to be defined in the data dictionary, and the data dictionary must be a tool that the system can rely on as well.

### Step 4: The DB interface and the Open SQl question

Something that SAP uses is called open SQL. This allows for direct management of the infotype tables using sql language, but I have to decide if this is what I want for this system, or if I want to borrow from C# and LINQ.

The DB interface allows for someone to use a different database instead of oracle or postgres, and open sql allows for sql-like management without needing to interface with the DB directly.

### Step 5: Number Ranges

I will have to take a series of number ranges for things like currencies, time, and other nonsense into the equation, but these are essential to any system and services so they get included here.

## Phase 3: Transaction Integrity

Argueably the most important part of the whole kernel. Ensuring that all processes are correct is a complex task that will be left to the Enqueue Server, the LUW Manager, and all data changes are performed under authorization and with documentation.

### Step 7: The Enqueue Server

In borrowing from SAP, I will need to design and build an enqueue server. This is the lock server that allows for records to process one at a time, without cross-changing data.

### Step 8: The LUW Manager

This is the heart of the entire system, the logical unit of work manager. This handles everything from the enqueuing and dequeuing of information, committing as all or nothing, and data integrity management.

### Step 9: Authorizations and change documents

The user seeking to make changes must have the appropriate authorizations neccisary to make the change they are requesting.

## Phase 4: Proof and Presentation

### Step 10: The "MVP"

This will be the first time I demonstrate the whole vertical stack works and functions as expected.

### Step 11: the Dynpro runtime
A Dynamic Program or "dynpro" for short, is a way for a program to display data to the user. It is meta data, that can then be translated to a GUI, or web or TUI. Part of this will be building the renderer that displays the data.

### Step 12: The IDE/Workbench/GUI

What separates a standard enterprise build system from something like SAP is the Workbench. This is a tightly coupled system of screens that allow for the development of, transport, and design of, business software and the viewing of data. If you are familiar with SAP, then you know about SE11, SE80, SM37, SM36, SE11, SE16, and so on. These Tranaction codes display a particular part of the workbench that you can then use to manage or modify something in the dictionary, code, or services.

The goal isn't replicate 1 for 1 these T-codes, but to build up my own system of screens that can get a user to a different action or view.

## Phase 5: The Application Platform

### Step 13: Business Framework

The business framework is best understood as an organizational model. everything the business customizes themselves lives here.

### Step 14: Procure to Pay
This is a full flow action that gets the data from buying something, to the accounting books. At this point, you are writing business logic in the new BBL language that demonstrates the system works.

## Phase 6: Enterprise Plumbing

### Step 15: Background Processes
This will be defining and scheduling jobs. the equivalent of SM36 and SM37 in SAP, while ensuring idempotency.

### Step 16: Async integration
RFC, message documents in the IDoc pattern with control record, data records, and status records, outbound and inbound processing, partner profiles, and distribution.

### Step 17: Enhancement and Transport
This is where the customer can be able to make adjustments to meet their own needs my creating their own exits, BADIs, and the transport system for importing data from the development environment to the QA environment, to the Production environment.



# And Beyond

Beyond this, it will be designing and building out modules like HCM or SCMS related materials and integrating them with this new platform. It will be a lengthy project over a great number of years, but considering how much you can learn from doing something like this, it will be interesting to see what happens in 3-5 years from now.







