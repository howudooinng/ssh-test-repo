# Day - 10

# Git Branching Strategy

For any organization, the primary goal is that the customers get the releases on time and promptly.

To deliver releases with new changes frequently, it is very important to have a very efficient branching strategy.

Customers get releases on time, so branching is important for small tasks to be delivered on time.

---

# What is a Branch?

A branch is a separation.

You have an application named **Calculator - V1** and then you have changes which are made, and it becomes **Calculator - V2**.

After development and testing, when you are confident that it is ready to work, you merge it into the main application as **Calculator - V2** and remove the older version. This then starts working as the main application.

---

# Example (Real Scenario)

Earlier, Uber was just supporting cab booking, and then they wanted to add Uber Bikes.

The Uber Cabs functionality was already in production, and they wanted to add the bike functionality to their application to attract even more customers.

Uber was not confident about the bike feature initially, so they started developing the bike functionality in a separate branch.

They created a **Bike Branch** and continued development and testing there.

After the team became confident, the bike functionality was added to the main working application, and the branch that was created for the development and testing of the bike functionality was deleted.

The main application then started working with both:

* Cab Booking
* Bike Booking

for the end users (customers using the Uber application).

---

# Feature Branch Example

**CALCULATOR → GitHub Repository**

The application is being developed with new fixes and commits on the existing GitHub repository.

Now the team decides to add new features to the application.

Instead of making changes directly in the main codebase, a **Feature Branch** is created.

After development and testing are completed successfully, the feature branch gets merged into the **Main/Master Branch**.

You can have multiple feature branches in an organization, and as each feature becomes ready, it gets merged into the Main/Master branch.

---

# Release Branch

To deliver the application to the customer, we usually build the application from the **Release Branches**.

Once we are satisfied with the application, we ship the Release Branch to the customer.

### Key Points

* Master/Main branch is usually kept for active development.
* Release Branch is only kept for the final shipping of the new feature or application to the customer.
* Production deployments are generally done from Release Branches.

---

# Hot Fix Branch

Hot Fix Branches are used for immediate fixes that need to be delivered quickly to customers.

The hotfix gets merged into:

1. Main/Master Branch
2. Release Branch

After that, the code is shipped from the Release Branch while keeping the Main branch updated with the latest fixes.

---

# Interview Questions

## What is a Hot Fix Branch?

A Hot Fix Branch is a temporary branch created to fix critical production issues that need to be delivered immediately to customers.

After testing, the fix is merged into both the Main/Master Branch and the Release Branch.

---

## What is a Feature Branch?

A Feature Branch is a separate branch created to develop a new functionality or enhancement without affecting the Main/Master Branch.

Once development and testing are completed, the feature branch is merged into the Main/Master Branch.

---

## What is the Main Branch?

The Main (or Master) Branch is the primary branch of the repository that contains the latest integrated code from all completed feature developments.

It serves as the central branch for active development.

---

## What is a Release Branch?

A Release Branch is a branch created from the Main Branch that contains only production-ready code.

It is used for final testing, stabilization, and deployment to customers.

---

# Practical Example

### Date: 11 June

**Codebase:** Calculator

**Branch:** Main/Master

Some changes need to be added to the Calculator application.

Instead of touching the Main Branch or the production-running codebase, we create a **Feature Branch** for that functionality.

When we are confident with both the coding and testing of the feature branch, we merge it into the Main/Master Branch.

Since many changes are developed simultaneously, multiple Feature Branches are usually created for an application to add new functionalities.

---

# Why Do We Use a Release Branch?

We use a Release Branch because we want to ship only the final production-ready code to customers on time.

The Release Branch contains only the production-ready changes and nothing else.

---

# Why Not Directly Ship Using the Main Branch?

Because the Main Branch usually has active development going on simultaneously by multiple developers.

Shipping from the Main Branch can accidentally ship:

* In-progress code
* Untested features
* Partially completed enhancements

This is incorrect and creates poor delivery standards within an organization.

If a project ships code directly from the Main Branch:

* Developers may block each other.
* Teams may have to wait for other developers to finish their work.
* Product enhancements get delayed.
* Releases become less predictable.

Therefore, organizations use Release Branches to ensure only stable and tested code reaches customers.

---

# Common Branch Types

```text
MASTER / MAIN  --> Branch
FEATURE        --> Branch
RELEASE        --> Branch
HOTFIX         --> Branch
```

# Flow of Development

```text
Main Branch
     |
     +----> Feature Branch A ----+
     |                           |
     +----> Feature Branch B ----+----> Main Branch
     |                           |
     +----> Feature Branch C ----+

Main Branch
     |
     +----> Release Branch ----> Production

Production Issue
     |
     +----> Hotfix Branch
                 |
                 +----> Main Branch
                 |
                 +----> Release Branch
                 |
                 +----> Production
```
