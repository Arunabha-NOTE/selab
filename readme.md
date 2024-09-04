# Software Requirements Specification (SRS)
**Project:** Social Networking Site  
**Date:** 04/09/2024 
**Version:** 1.0  
**Author:** Arunabha Mukhopadhyay

---

## Table of Contents

1. [Introduction](#introduction)
   - [1.1 Purpose](#11-purpose)
   - [1.2 Scope](#12-scope)
   - [1.3 Definitions, Acronyms, and Abbreviations](#13-definitions-acronyms-and-abbreviations)
   - [1.4 References](#14-references)
   - [1.5 Overview](#15-overview)
2. [Overall Description](#overall-description)
   - [2.1 Product Perspective](#21-product-perspective)
   - [2.2 Product Functions](#22-product-functions)
   - [2.3 User Classes and Characteristics](#23-user-classes-and-characteristics)
   - [2.4 Operating Environment](#24-operating-environment)
   - [2.5 Design and Implementation Constraints](#25-design-and-implementation-constraints)
   - [2.6 Assumptions and Dependencies](#26-assumptions-and-dependencies)
3. [Specific Requirements](#specific-requirements)
   - [3.1 External Interface Requirements](#31-external-interface-requirements)
   - [3.2 Functional Requirements](#32-functional-requirements)
   - [3.3 Performance Requirements](#33-performance-requirements)
   - [3.4 Logical Database Requirements](#34-logical-database-requirements)
   - [3.5 Design Constraints](#35-design-constraints)
   - [3.6 Software System Attributes](#36-software-system-attributes)
   - [3.7 Security Requirements](#37-security-requirements)
4. [Appendices](#appendices)
   - [4.1 Glossary](#41-glossary)
   - [4.2 Use Cases](#42-use-cases)
5. [Other Nonfunctional Requirements](#other-nonfunctional-requirements)
   - [5.1 Performance Requirements](#51-performance-requirements)
   - [5.2 Safety Requirements](#52-safety-requirements)
   - [5.3 Security Requirements](#53-security-requirements)
   - [5.4 Software Quality Attributes](#54-software-quality-attributes)
   - [5.5 Business Rules](#55-business-rules)
6. [Other Requirements](#other-requirements)

---

## 1. Introduction <a name="introduction"></a>

### 1.1 Purpose <a name="11-purpose"></a>

This SRS document outlines the functional and non-functional requirements for developing a Social Networking Site. The document serves as a guide for the development team, project managers, stakeholders, and clients to ensure all requirements are captured and understood. It will facilitate the design, implementation, and validation phases of the project.

### 1.2 Scope <a name="12-scope"></a>

The Social Networking Site will allow users to create profiles, post updates, send friend requests, and communicate through messaging. The system will include features for user authentication, profile management, and privacy settings. The project aims to deliver a secure and user-friendly platform for social interaction.

### 1.3 Definitions, Acronyms, and Abbreviations <a name="13-definitions-acronyms-and-abbreviations"></a>

- **SRS**: Software Requirements Specification
- **SNS**: Social Networking Site
- **UI**: User Interface
- **API**: Application Programming Interface
- **IaC**: Infrastructure as Code
- **CI/CD**: Continuous Integration/Continuous Deployment
- **OAuth**: Open Authorization, a protocol for token-based authentication
- **CRUD**: Create, Read, Update, Delete

### 1.4 References <a name="14-references"></a>

- IEEE 830-1998 Standard for Software Requirements Specifications
- [Reference 2: Add any additional references here]

### 1.5 Overview <a name="15-overview"></a>

This document provides a detailed overview of the system requirements, including functional and non-functional requirements. Section 2 describes the overall system, including its perspective, functions, and constraints. Section 3 details the specific requirements, including external interfaces, performance, and security. The appendices provide additional context, including use cases and a glossary.

---

## 2. Overall Description <a name="overall-description"></a>

### 2.1 Product Perspective <a name="21-product-perspective"></a>

The Social Networking Site is a web-based application designed to facilitate social interactions between users. It will integrate with external authentication services such as OAuth for secure user login. The system will be built on a microservices architecture, allowing for scalable and modular development. The site will be accessible via any modern web browser and optimized for performance and usability.

### 2.2 Product Functions <a name="22-product-functions"></a>

The major functions of the Social Networking Site include:

- **User Registration and Authentication**: Users can register, log in, and recover passwords.
- **Profile Management**: Users can create, update, and manage their profiles, including privacy settings.
- **Social Interactions**: Users can post updates, send friend requests, and message each other.
- **Search Functionality**: Users can search for other users and content.
- **Content Moderation**: Administrators can monitor and manage user-generated content.

### 2.3 User Classes and Characteristics <a name="23-user-classes-and-characteristics"></a>

- **General Users**: Individuals who use the platform for social networking. They require an intuitive interface and responsive performance.
- **Administrators**: Users with elevated privileges responsible for managing the platform, moderating content, and handling user issues.

### 2.4 Operating Environment <a name="24-operating-environment"></a>

The Social Networking Site will operate in a web environment, accessible via major web browsers (e.g., Chrome, Firefox, Safari). The backend will be deployed on cloud infrastructure (GCP, Azure, or AWS), ensuring scalability and high availability.

### 2.5 Design and Implementation Constraints <a name="25-design-and-implementation-constraints"></a>

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

### 2.6 Assumptions and Dependencies <a name="26-assumptions-and-dependencies"></a>

- Users have access to stable internet and modern web browsers.
- The system will integrate with third-party authentication providers.
- Cloud infrastructure and CI/CD tools will be available for deployment and development processes.

---

## 3. Specific Requirements <a name="specific-requirements"></a>

### 3.1 External Interface Requirements <a name="31-external-interface-requirements"></a>

- **User Interfaces**: 
  - The UI must be responsive and intuitive, supporting various screen sizes (desktop, tablet, mobile).
  - The design will follow accessibility standards (e.g., WCAG).

- **API Interfaces**: 
  - The system will provide RESTful APIs for integration with mobile apps and external services.
  - API endpoints will be secured using OAuth tokens.

### 3.2 Functional Requirements <a name="32-functional-requirements"></a>

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

### 3.3 Performance Requirements <a name="33-performance-requirements"></a>

- The system shall support at least 10,000 concurrent users without significant performance degradation.
- The system shall load the main user interface within 3 seconds under normal conditions.
- The API shall respond to requests within 200ms on average.

### 3.4 Logical Database Requirements <a name="34-logical-database-requirements"></a>

- The system shall store user profiles, posts, friend connections, and messages in a relational database.
- The system shall maintain audit logs of all user activities for a minimum of 1 year.

### 3.5 Design Constraints <a name="35-design-constraints"></a>

- The frontend will use **Angular** for the application framework and **NgRx** for state management.
- The backend will use **Java** with **Spring Boot** for RESTful service development.
- Cloud deployment will utilize **GCP**, **Azure**, or **AWS** with **Ansible** or **Terraform** for infrastructure as code.
- CI/CD processes will be managed using **GitLab Pipelines** and **CircleCI**.

### 3.6 Software System Attributes <a name="36-software-system-attributes"></a>

- **Security**: 
  - The system shall use **bcrypt** for password hashing.
  - OAuth will be implemented for secure third-party authentication.
  
- **Reliability**: 
  - The system shall have 99.9% uptime, supported by cloud-based infrastructure.
  
- **Maintainability**: 
  - The system codebase will be modular, leveraging microservices for easier updates and maintenance.
  
- **Scalability**: 
  - The system architecture will support horizontal scaling to handle growing user loads.

### 3.7 Security Requirements <a name="37-security-requirements"></a>

- The system shall implement role-based access control (RBAC) to restrict access based on user roles.

---

## 4. Appendices <a name="appendices"></a>

### 4.1 Glossary <a name="41-glossary"></a>

- **Friend Request**: A request sent by one user to another to become friends on the platform.
- **OAuth**: An open-standard authorization protocol that allows secure access to user data without exposing user credentials.
- **Microservices**: A software architecture style that structures an application as a collection of loosely coupled services.

### 4.2 Use Cases <a name="42-use-cases"></a>

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

---

- ## 5. Other Nonfunctional Requirements <a name="other-nonfunctional-requirements"></a>

### 5.1 Performance Requirements <a name="51-performance-requirements"></a>

- The system shall support at least 10,000 concurrent users with no noticeable performance degradation.
- Page load times shall not exceed 3 seconds for 95% of all user interactions.
- The system shall handle 100 requests per second with an average response time of less than 200 milliseconds.

### 5.2 Safety Requirements <a name="52-safety-requirements"></a>

- The system shall prevent unauthorized access to user data by implementing strict access controls.
- User data shall be backed up daily, with backups retained for 30 days.
- In case of a data breach, the system shall have a mechanism to notify affected users within 24 hours.

### 5.3 Security Requirements <a name="53-security-requirements"></a>

- All user passwords shall be hashed using **bcrypt** with a minimum of 12 salt rounds.
- The system shall implement **OAuth 2.0** for secure third-party authentication.
- The system shall enforce HTTPS for all communications to protect data in transit.
- Role-based access control (RBAC) shall be implemented to restrict access based on user roles.

### 5.4 Software Quality Attributes <a name="54-software-quality-attributes"></a>

- **Reliability**: The system shall maintain 99.9% uptime, supported by redundant cloud infrastructure.
- **Scalability**: The system shall be capable of horizontal scaling to accommodate increased user loads.
- **Maintainability**: The codebase shall be modular and adhere to clean code principles, making it easy to update and maintain.
- **Usability**: The user interface shall be intuitive and follow established usability standards.

### 5.5 Business Rules <a name="55-business-rules"></a>

- Only users aged 13 and above can register on the platform.
- Users must accept the terms of service and privacy policy before account creation.
- Administrators shall have the authority to suspend or ban accounts that violate the platform’s community guidelines.

---

## 6. Other Requirements <a name="other-requirements"></a>

- The system shall support multiple languages, with localization for at least English, Spanish, and French.
- The database schema shall be designed to comply with GDPR requirements, allowing users to request data deletion.
- The system shall be designed with reuse in mind, enabling components to be reused in future projects.

