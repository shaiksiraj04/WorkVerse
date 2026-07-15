> ⚠️ **Internal Engineering Document**
>
> This Database Design Document defines the MongoDB architecture for the WorkVerse MVP.
> It explains how data is stored, how collections relate to each other, and how the database is designed to support future scalability.

# 🗄️ Database Design Document

# WorkVerse

**Version:** 1.0

**Project:** WorkVerse

**Founder:** Mahammed Sirajuddin

**Prepared By:** WorkVerse Engineering Team

**Status:** Planning Phase

**Date:** July 2026

---

# 📑 Table of Contents

1. Database Overview
2. Database Technology
3. Collections
4. Collection Schemas
5. Relationships
6. Indexing Strategy
7. Validation Rules
8. Future Database Expansion

---

# 1. Database Overview

WorkVerse uses **MongoDB Atlas**, a cloud-based NoSQL database.

A document-oriented database was selected because it provides:

- High scalability
- Flexible schema
- Fast development
- Easy integration with the MERN stack

---

# 2. Database Technology

Database:

- MongoDB Atlas

ODM:

- Mongoose

Database Type:

- NoSQL Document Database

---

# 3. Database Collections

The MVP includes the following collections:

- Users
- Roles
- Tasks
- TaskSubmissions
- Progress
- Certificates
- AIChats

---

# 4. Collection Schemas

## Users

Stores student information.

Fields:

- _id
- name
- email
- googleId
- profilePicture
- college
- skills
- currentRole
- xp
- level
- dailyStreak
- completedTasks
- createdAt
- updatedAt

---

## Roles

Stores available career roles.

Fields:

- _id
- roleName
- category
- description
- difficulty
- icon
- totalTasks
- createdAt

---

## Tasks

Stores industry simulation tasks.

Fields:

- _id
- roleId
- title
- description
- difficulty
- instructions
- expectedOutcome
- resources
- estimatedTime
- xpReward
- createdAt

---

## TaskSubmissions

Stores completed task information.

Fields:

- _id
- userId
- taskId
- solution
- aiFeedback
- score
- status
- submittedAt

---

## Progress

Tracks learning progress.

Fields:

- _id
- userId
- currentLevel
- totalXP
- completedRoles
- completedTasks
- streak
- lastCompletedTask
- updatedAt

---

## Certificates

Stores generated certificates.

Fields:

- _id
- userId
- roleId
- certificateId
- issuedDate
- downloadUrl
- verificationCode (Future)

---

## AIChats

Stores AI Mentor conversations.

Fields:

- _id
- userId
- question
- response
- timestamp

---

# 5. Relationships

User

↓

Selects

↓

Role

↓

Contains

↓

Tasks

↓

Submitted As

↓

TaskSubmission

↓

Updates

↓

Progress

↓

Unlocks

↓

Certificate

AIChats are linked directly to the User.

---

# 6. Indexing Strategy

Indexes improve database performance.

Recommended indexes:

Users

- email
- googleId

Tasks

- roleId
- difficulty

TaskSubmissions

- userId
- taskId

Certificates

- certificateId

AIChats

- userId

---

# 7. Validation Rules

## Users

- Name is required
- Email must be unique
- Google ID is required
- XP cannot be negative

---

## Roles

- Role name required
- Category required

---

## Tasks

- Title required
- Difficulty required
- Estimated time required

---

## TaskSubmissions

- Solution required
- User ID required
- Task ID required

---

## Certificates

- Certificate ID must be unique
- User ID required

---

# 8. Future Database Expansion

Future collections may include:

- Recruiters
- Companies
- Colleges
- Notifications
- Payments
- Achievements
- Leaderboards
- Teams
- MockInterviews
- ResumeBuilder

The database is designed to allow these collections to be added without restructuring the existing schema.

---

# 📌 Database Design Principles

Every collection follows these principles:

- Simplicity
- Scalability
- Performance
- Security
- Flexibility
- Data Integrity

---

# 📌 Engineering Philosophy

The database is optimized for:

- Fast reads
- Efficient writes
- Future expansion
- Clean relationships
- Easy maintenance

The goal is to support both the MVP and future enterprise-scale growth without major redesign.