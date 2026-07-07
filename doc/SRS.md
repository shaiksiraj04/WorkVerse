> ⚠️ **Internal Document**
>
> This Software Requirements Specification (SRS) defines the complete technical blueprint of the WorkVerse MVP.
> It serves as the primary engineering document for designing, developing, testing, and deploying the platform.
> Every feature implemented in WorkVerse must follow the requirements defined in this document.

# 📄 Software Requirements Specification (SRS)

# WorkVerse

**Version:** 1.0

**Document Type:** Software Requirements Specification

**Project Status:** Planning Phase

**Founder:** Mahammed Sirajuddin

**Prepared By:** WorkVerse Engineering Team

**Date:** July 2026

---

# 📑 Table of Contents

1. Introduction
2. Purpose
3. Project Scope
4. Product Overview
5. User Roles
6. Functional Requirements
7. Non-Functional Requirements
8. System Modules
9. Application Pages
10. User Flow
11. Navigation Flow
12. MVP Features
13. Component Architecture
14. API Overview
15. Database Collections
16. Validation Rules
17. Security Requirements
18. Future Enhancements
19. Assumptions
20. Constraints

---

# 1. Introduction

WorkVerse is a career simulation platform that enables students and fresh graduates to experience real IT and Cybersecurity industry workflows before entering the workforce.

Unlike traditional learning platforms, WorkVerse emphasizes practical experience by simulating a professional company environment where learners perform realistic daily tasks based on their selected career role.

---

# 2. Purpose

The purpose of this Software Requirements Specification (SRS) is to define all functional and technical requirements for the WorkVerse MVP.

This document serves as the reference for:

- Product Development
- UI/UX Design
- Backend Development
- Frontend Development
- Database Design
- API Development
- Testing
- Deployment

---

# 3. Project Scope

The MVP will focus on helping students understand how professionals work inside IT companies through role-based simulations.

The first version includes:

- Google Authentication
- Student Dashboard
- Career Role Selection
- Daily Practical Tasks
- AI Mentor
- Progress Tracking
- Certificate Generation

The following are intentionally excluded from Version 1:

- Recruiter Dashboard
- College Dashboard
- Company Dashboard
- Team Collaboration
- Placement Services
- Mobile Application

---

# 4. Product Overview

WorkVerse is not an online course platform.

It is a virtual workplace where students become employees, complete daily work tasks, receive mentorship, and build practical experience before joining their first company.

Core philosophy:

> Experience the job before you get the job.

---

# 5. User Roles

## Student (MVP)

The Student is the only user role in Version 1.

Permissions:

- Login using Google
- Create profile
- Choose career role
- View dashboard
- Complete tasks
- View progress
- Earn XP
- Download certificates
- Interact with AI Mentor
- Edit profile

Future user roles:

- Admin
- Recruiter
- Company
- Mentor

---

# 6. Functional Requirements

The system shall:

- Allow Google authentication.
- Store user information.
- Allow role selection.
- Display assigned tasks.
- Allow task submission.
- Evaluate task completion.
- Update user progress.
- Generate certificates.
- Maintain daily streaks.
- Provide AI mentoring.

---

# 7. Non-Functional Requirements

The application must be:

- Responsive
- Secure
- Fast
- Scalable
- Maintainable
- Accessible
- Reliable
- User-friendly

Target loading time:

Less than 2 seconds.

---

# 8. System Modules

The MVP consists of:

- Authentication Module
- Student Dashboard
- Role Management
- Task Management
- Progress Management
- AI Mentor
- Certificate System
- User Profile

---

# 9. Application Pages

## Landing Page

Purpose:

Introduce WorkVerse.

Main Components:

- Hero Section
- Features
- Benefits
- Testimonials (Future)
- FAQ
- Footer

---

## Login Page

Purpose:

Authenticate users.

Components:

- Google Login Button

---

## Dashboard

Purpose:

Student home screen.

Displays:

- Welcome Message
- Today's Task
- XP
- Progress
- Current Role
- Daily Streak

---

## Role Selection

Purpose:

Allow students to choose a career path.

Initial Roles:

- Full Stack Developer
- Backend Developer
- SOC Analyst

---

## Task Page

Displays:

- Today's Task
- Instructions
- Resources
- Submit Button

---

## AI Mentor

Features:

- Ask Questions
- Explain Concepts
- Give Hints
- Provide Feedback

---

## Progress Page

Displays:

- Completed Tasks
- XP
- Level
- Certificates
- Streak

---

## Certificate Page

Displays:

Completed certificates and download option.

---

## Profile Page

Displays:

- Name
- College
- Skills
- Selected Role
- Progress

---

# 10. User Flow

Landing

↓

Google Login

↓

Dashboard

↓

Role Selection

↓

Today's Task

↓

Task Submission

↓

AI Feedback

↓

Progress Updated

↓

Certificate

---

# 11. Navigation Flow

Landing

↓

Login

↓

Dashboard

├── Profile

├── AI Mentor

├── Progress

├── Certificates

└── Tasks

---

# 12. MVP Features

- Google Authentication
- Student Dashboard
- Role Selection
- Daily Tasks
- AI Mentor
- Progress Tracking
- XP
- Certificates
- Profile Management

---

# 13. Component Architecture

Frontend Components:

- Navbar
- Hero
- Footer
- LoginButton
- Sidebar
- DashboardLayout
- RoleCard
- TaskCard
- ProgressCard
- CertificateCard
- AIChat
- Loader

---

# 14. API Overview

Authentication

POST /auth/google

User

GET /user/profile

Roles

GET /roles

Tasks

GET /tasks/:role

Task Submission

POST /tasks/submit

Progress

GET /progress

Certificates

GET /certificate

AI

POST /ai/chat

---

# 15. Database Collections

MongoDB Collections:

Users

Roles

Tasks

TaskSubmissions

Progress

Certificates

AIChats

---

# 16. Validation Rules

User:

- Name required
- Email required

Task:

- Cannot submit empty answer
- Duplicate submissions not allowed

Authentication:

- Google account required

---

# 17. Security Requirements

- Google OAuth
- JWT Authentication
- Protected Routes
- Input Validation
- Data Sanitization
- Secure API Calls
- HTTPS Deployment

---

# 18. Future Enhancements

- Recruiter Dashboard
- Company Dashboard
- College Dashboard
- More Roles
- AI Task Generation
- Mobile Application
- Team Projects
- Live Mentors

---

# 19. Assumptions

- Users have internet access.
- Users understand basic programming.
- Google Authentication is available.
- MongoDB Atlas is available.

---

# 20. Constraints

- Zero initial budget.
- Single developer.
- MVP only.
- Development time:
    - 1–1.5 hours/day
    - 2–3 hours on Sundays

---

# 📌 Software Engineering Principle

Every feature implemented in WorkVerse must satisfy these requirements:

- Simplicity
- Scalability
- Security
- Performance
- Maintainability
- User Experience

---

# 📌 Product Principle

> Experience the job before you get the job.

Every engineering decision should support this mission.