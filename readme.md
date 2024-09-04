# Software Requirements Specification (SRS)  
**Project:** Social Networking Site  
**Date:** 04/09/2024  
**Version:** 1.0  
**Author:** Arunabha Mukhopadhyay

---

## Table of Contents

1. **Introduction**
   - 1.1 Purpose
   - 1.2 Scope
   - 1.3 Definitions, Acronyms, and Abbreviations
   - 1.4 References
   - 1.5 Overview
2. **Overall Description**
   - 2.1 Product Perspective
   - 2.2 Product Functions
   - 2.3 User Classes and Characteristics
   - 2.4 Operating Environment
   - 2.5 Design and Implementation Constraints
   - 2.6 Assumptions and Dependencies
3. **Specific Requirements**
   - 3.1 External Interface Requirements
   - 3.2 Functional Requirements
   - 3.3 Performance Requirements
   - 3.4 Logical Database Requirements
   - 3.5 Design Constraints
   - 3.6 Software System Attributes
   - 3.7 Security Requirements
4. **Appendices**
   - 4.1 Glossary
   - 4.2 Use Cases

---

## 1. Introduction

### 1.1 Purpose

This SRS document outlines the functional and non-functional requirements for developing a Social Networking Site. The document serves as a guide for the development team, project managers, stakeholders, and clients to ensure all requirements are captured and understood. It will facilitate the design, implementation, and validation phases of the project.

### 1.2 Scope

The Social Networking Site will allow users to create profiles, post updates, send friend requests, and communicate through messaging. The system will include features for user authentication, profile management, and privacy settings. The project aims to deliver a secure and user-friendly platform for social interaction.

### 1.3 Definitions, Acronyms, and Abbreviations

- **SRS**: Software Requirements Specification
- **SNS**: Social Networking Site
- **UI**: User Interface
- **API**: Application Programming Interface
- **IaC**: Infrastructure as Code
- **CI/CD**: Continuous Integration/Continuous Deployment
- **OAuth**: Open Authorization, a protocol for token-based authentication
- **CRUD**: Create, Read, Update, Delete

### 1.4 References

- IEEE 830-1998 Standard for Software Requirements Specifications
- [Reference 2: Add any additional references here]

### 1.5 Overview

This document provides a detailed overview of the system requirements, including functional and non-functional requirements. Section 2 describes the overall system, including its perspective, functions, and constraints. Section 3 details the specific requirements, including external interfaces, performance, and security. The appendices provide additional context, including use cases and a glossary.

---

## 2. Overall Description

### 2.1 Product Perspective

The Social Networking Site is a web-based application designed to facilitate social interactions between users. It will integrate with external authentication services such as OAuth for secure user login. The system will be built on a microservices architecture, allowing for scalable and modular development. The site will be accessible via any modern web browser and optimized for performance and usability.

### 2.2 Product Functions

The major functions of the Social Networking Site include:

- **User Registration and Authentication**: Users can register, log in, and recover passwords.
- **Profile Management**: Users can create, update, and manage their profiles, including privacy settings.
- **Social Interactions**: Users can post updates, send friend requests, and message each other.
- **Search Functionality**: Users can search for other users and content.
- **Content Moderation**: Administrators can monitor and manage user-generated content.

### 2.3 User Classes and Characteristics

- **General Users**: Individuals who use the platform for social networking. They require an intuitive interface and responsive performance.
- **Administrators**: Users with elevated privileges responsible for managing the platform, moderating content, and handling user issues.

### 2.4 Operating Environment

The Social Networking Site will operate in a web environment, accessible via major web browsers (e.g., Chrome, Firefox, Safari). The backend will be deployed on cloud infrastructure (GCP, Azure, or AWS), ensuring scalability and high availability.

### 2.5 Design and Implementation Constraints

- **Frontend**:
  - Developed using **HTML**, **Tailwind CSS**, **Angular**, and **NgRx** for state management.
  - **bcrypt** will be utilized for secure password hashing and authentication.

- **Backend**:
  - Developed using **Java** with **Lombok** for streamlined code management.
  - **Spring Boot** for rapid development and deployment, with **Spring Microservices** for a modular and scalable architecture.
  - **Spring Web** will handle microservices deployment.

- **Cloud Native Deployment**:
  - **GCP**, **Azure**, or **AWS** will be used for cloud deployment.
  - **Ansible** or **Terraform** will manage infrastructure as code.

- **CI/CD**:
  - **GitLab Pipelines** and **CircleCI** will manage continuous integration and deployment workflows.

- **Database**:
  - **PostgreSQL** will serve as the primary relational database management system.

- **Testing Framework**:
  - **JUnit** will be the primary testing framework for backend validation.

### 2.6 Assumptions and Dependencies

- Users have access to stable internet and modern web browsers.
- The system will integrate with third-party authentication providers.
- Cloud infrastructure and CI/CD tools will be available for deployment and development processes.

---

## 3. Specific Requirements

### 3.1 External Interface Requirements

- **User Interfaces**: 
  - The UI must be responsive and intuitive, supporting various screen sizes (desktop, tablet, mobile).
  - The design will follow accessibility standards (e.g., WCAG).

- **API Interfaces**: 
  - The system will provide RESTful APIs for integration with mobile apps and external services.
  - API endpoints will be secured using OAuth tokens.

### 3.2 Functional Requirements

#### 3.2.1 User Registration and Authentication
- The system shall allow users to register with an email address and password.
- The system shall allow users to log in using their credentials.
- The system shall support password recovery using email verification.

#### 3.2.2 Profile Management
- The system shall allow users to create and update their profiles.
- The system shall allow users to upload and change profile pictures.
- The system shall allow users to configure privacy settings for their profiles, controlling who can view their information.

#### 3.2.3 Social Interactions
- The system shall allow users to post updates, including text and media.
- The system shall allow users to send, accept, and reject friend requests.
- The system shall allow users to send private messages to other users.

#### 3.2.4 Privacy Settings
- The system shall allow users to control who can view their profile information.
- The system shall allow users to control who can view their posts and updates.

#### 3.2.5 Search Functionality
- The system shall allow users to search for other users by name or email.
- The system shall allow users to search for posts by keywords.

#### 3.2.6 Content Moderation (for Administrators)
- The system shall allow administrators to view, edit, and delete user-generated content.
- The system shall allow administrators to suspend or ban user accounts violating platform policies.

### 3.3 Performance Requirements

- The system shall support at least 10,000 concurrent users without significant performance degradation.
- The system shall load the main user interface within 3 seconds under normal conditions.
- The API shall respond to requests within 200ms on average.

### 3.4 Logical Database Requirements

- The system shall store user profiles, posts, friend connections, and messages in a relational database.
- The system shall ensure data integrity, supporting ACID (Atomicity, Consistency, Isolation, Durability) transactions for critical operations like account creation and message delivery.

### 3.5 Design Constraints

- The system shall be built using a microservices architecture to ensure scalability and modularity.
- The system shall use industry-standard encryption (e.g., AES-256) for data in transit and at rest.
- The system shall comply with relevant data protection regulations (e.g., GDPR).

### 3.6 Software System Attributes

- **Security**: 
  - The system must prevent unauthorized access and ensure data protection through encryption and secure authentication mechanisms.
  - The system shall be compliant with industry-standard security practices (e.g., OWASP Top Ten).

- **Usability**: 
  - The system must be easy to navigate, with clear instructions and a responsive design that works across devices.

- **Scalability**: 
  - The system must be able to scale horizontally to accommodate increasing numbers of users and data volume.

- **Maintainability**: 
  - The system shall be modular, with well-documented code to facilitate updates and maintenance.

- **Reliability**: 
  - The system shall have an uptime of at least 99.9%, with failover mechanisms in place to handle outages.

### 3.7 Security Requirements

- The system shall use **OAuth 2.0** for secure authentication and authorization.
- The system shall encrypt all sensitive data using **AES-256**.
- The system shall implement **HTTPS** for all client-server communication.
- The system shall log all user activities and provide audit trails for security analysis.
- The system shall support

 role-based access control (RBAC) to restrict access based on user roles.

---

## 4. Appendices

### 4.1 Glossary

- **Friend Request**: A request sent by one user to another to become friends on the platform.
- **OAuth**: An open-standard authorization protocol that allows secure access to user data without exposing user credentials.
- **Microservices**: A software architecture style that structures an application as a collection of loosely coupled services.

### 4.2 Use Cases

**Use Case 1: User Registration**  
- **Actors**: New User  
- **Description**: A new user registers on the platform by providing an email address, creating a password, and verifying their email.  
- **Preconditions**: The user must have a valid email address.  
- **Postconditions**: The user account is created, and the user can log in.

**Use Case 2: Posting an Update**  
- **Actors**: Registered User  
- **Description**: A registered user posts an update that appears on their profile and the feed of their friends.  
- **Preconditions**: The user must be logged in.  
- **Postconditions**: The post is visible to the user’s friends, depending on privacy settings.

**Use Case 3: Sending a Friend Request**  
- **Actors**: Registered User  
- **Description**: A registered user sends a friend request to another user.  
- **Preconditions**: The user must be logged in and not already friends with the recipient.  
- **Postconditions**: The friend request is sent and is pending until accepted or declined.

