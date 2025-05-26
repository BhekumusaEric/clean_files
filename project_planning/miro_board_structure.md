# Code Clinic Project - Miro Board Structure Guide

## Board Layout Overview
Your Miro board should be organized into clear sections that support agile project management and WTC monitoring requirements.

## Section 1: Team Information (Top Left)
### Team Details Card
```
Team Name: [Your Team Name]
Project: Code Clinic System
Mentor: [Mentor Name]
Start Date: [Project Start Date]

Team Members:
• [Name 1] - [Role] - [Email] - Individual Exercises: [Status]
• [Name 2] - [Role] - [Email] - Individual Exercises: [Status]
• [Name 3] - [Role] - [Email] - Individual Exercises: [Status]
• [Name 4] - [Role] - [Email] - Individual Exercises: [Status]

Daily Stand-up: [Time] at [Location/Platform]
Communication: [Slack/WhatsApp/etc.]
```

### Project Vision
```
Vision: Create a peer-to-peer learning system that enables students 
to volunteer their time helping other students with coding problems, 
integrated with Google Calendar for seamless scheduling.

Success Metrics:
• Students can register and book help sessions
• Volunteers can offer and manage time slots
• Google Calendar integration works seamlessly
• CLI interface is user-friendly
• System handles 50+ concurrent users
```

## Section 2: Product Backlog (Left Side)
### Epic Swimlanes
Create horizontal swimlanes for each epic:

**Epic 1: User Management**
- Student Registration (3 pts)
- Volunteer Registration (3 pts)

**Epic 2: Time Slot Management**
- Add Volunteer Slots (5 pts)
- View Available Slots (3 pts)

**Epic 3: Booking System**
- Book a Session (8 pts)
- Cancel Booking (5 pts)

**Epic 4: Google Calendar Integration**
- Calendar Authentication (8 pts)
- Event Management (5 pts)

**Epic 5: CLI Interface**
- CLI Commands (8 pts)

**Epic 6: Data Persistence**
- Data Storage (5 pts)

### Story Card Template
```
Story ID: US-X.X
Title: [Story Title]
As a [user type]
I want [functionality]
So that [benefit]

Acceptance Criteria:
• [Criterion 1]
• [Criterion 2]
• [Criterion 3]

Story Points: X
Priority: High/Medium/Low
Dependencies: [List any dependencies]
```

## Section 3: Iteration Boards (Center)
### Create 5 iteration boards side by side:

#### Iteration 0: Planning & Setup
**Columns:**
- To Do
- In Progress  
- Review
- Done

**Sample Cards:**
- Project Setup (5 pts)
- Team Kickoff (2 pts)
- Environment Setup (3 pts)
- Google API Research (5 pts)

#### Iteration 1-4: Development Iterations
**Columns for each:**
- Backlog
- To Do
- In Progress
- Review
- Done

## Section 4: Retrospectives (Right Side)
### Create sections for each iteration:

#### Iteration X Retrospective
**What Went Well (Green sticky notes)**
- [Team achievements]
- [Successful practices]
- [Good decisions]

**What Could Be Improved (Yellow sticky notes)**
- [Challenges faced]
- [Process issues]
- [Technical difficulties]

**Action Items (Red sticky notes)**
- [Specific improvements for next iteration]
- [Process changes]
- [Technical debt to address]

## Section 5: Risk & Dependency Tracking (Bottom)
### Risk Register
```
Risk: [Description]
Impact: High/Medium/Low
Probability: High/Medium/Low
Mitigation: [Strategy]
Owner: [Team Member]
Status: Open/Mitigated/Closed
```

### Dependency Tracker
```
Dependency: [Description]
Type: Internal/External
Impact: [What's blocked]
Status: Pending/Resolved
Owner: [Responsible person]
```

## Section 6: Definition of Done (Bottom Right)
```
Definition of Done Checklist:
□ Code is written and follows team standards
□ Unit tests are written and passing
□ Code is reviewed by another team member
□ Integration tests pass
□ Documentation is updated
□ Feature is demo-ready
□ No critical bugs
□ Acceptance criteria are met
□ Code is merged to main branch
```

## Miro Board Best Practices

### Color Coding
- **Blue:** User stories and features
- **Green:** Completed items
- **Yellow:** In progress items
- **Red:** Blocked or high-risk items
- **Purple:** Technical tasks
- **Orange:** Bugs or issues

### Card Movement Rules
1. Only move cards during stand-ups or planned sessions
2. Update card status when moving between columns
3. Add comments when cards are blocked
4. Tag team members when review is needed

### Daily Updates
- Move cards to reflect current status
- Add new impediments or risks
- Update story point estimates if needed
- Add notes about progress or blockers

### Weekly Reviews
- Review completed work
- Update velocity calculations
- Assess risk status
- Plan next iteration commitment

## Integration with GitLab
- Link Miro cards to GitLab issues
- Use same story IDs in both systems
- Update both systems during stand-ups
- Use GitLab for detailed technical discussions
- Use Miro for high-level planning and visualization
