# TalentFlow – A Mini Hiring Platform (Front-End Only)
# ALSALA AHMED-CE22B038

## Overview
TalentFlow is a front-end React application that simulates a hiring management platform for HR teams. It enables managing **Jobs**, **Candidates**, and **Assessments** without a backend. All data is stored locally using **IndexedDB** via **Dexie** or **localForage**, and API calls are simulated using **MirageJS** or **MSW**.

---

## Features

### Jobs Management
- Create, edit, archive, and reorder jobs  
- Pagination and filtering by title, status, and tags  
- Validation for required title and unique slug  
- Drag-and-drop reordering with optimistic updates and rollback  
- Deep linking to job details `/jobs/:jobId`

### Candidates Management
- Virtualized list for 1000+ candidates  
- Client-side search (name, email) and server-like filtering (stage)  
- Candidate profile `/candidates/:id` with timeline of status changes  
- Move candidates between stages via Kanban board  
- Notes with `@mentions` (render-only, suggestions from local list)

### Assessments
- Job-specific assessment builder  
- Add sections and questions (single-choice, multi-choice, text, numeric, file upload)  
- Live preview pane for fillable forms  
- Validation rules (required, numeric range, max length)  
- Conditional questions (e.g., show Q3 only if Q1 === "Yes")  
- Responses stored locally

---

## Tech Stack
- React 18+  
- Vite  
- React Router DOM  
- MirageJS / MSW  
- Dexie / localForage  
- React Beautiful DnD  
- React Virtualized  
- Material UI  

---

## Installation & Setup

```bash
# Clone the repository
git clone https://github.com/yourusername/talentflow.git
cd talentflow

# Install dependencies
npm install

# Start development server
npm run dev
```
## Folder Structure
```
src/
 ┣ components/        # Reusable UI components
 ┣ pages/             # Jobs, Candidates, Assessments pages
 ┣ hooks/             # Custom React hooks
 ┣ services/          # API simulation and data services
 ┣ mocks/             # MirageJS or MSW setup
 ┣ db/                # IndexedDB configuration
 ┣ utils/             # Helper functions
 ┣ App.jsx
 ┗ main.jsx
 ```

 ## Simulated API Endpoints
## Jobs
- GET /jobs?search=&status=&page=&pageSize=&sort=
- POST /jobs
- PATCH /jobs/:id
- PATCH /jobs/:id/reorder
## Candidates
- GET /candidates?search=&stage=&page=
- POST /candidates
- PATCH /candidates/:id
- GET /candidates/:id/timeline
## Assessments
- GET /assessments/:jobId
- PUT /assessments/:jobId
- POST /assessments/:jobId/submit
## Bonus Features
- Dark mode toggle
- Analytics dashboard for jobs and candidates
- Export/import local data
- Error boundary and retry logic
## Author: Az7dev
License: MIT