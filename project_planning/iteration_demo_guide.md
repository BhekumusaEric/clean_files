# Code Clinic Project - Iteration Demo Guide

## Demo Format
**Duration:** 5 minutes demo + 10 minutes Q&A  
**Frequency:** End of each iteration (Fridays)  
**Audience:** WTC staff, mentors, external experts  
**Requirement:** Any team member should be able to explain the code  

## Demo Structure Template

### 1. Iteration Summary (1 minute)
**Speaker:** Scrum Master
- Iteration goals recap
- Stories completed vs. committed
- Key achievements and challenges

**Script Template:**
> "In Iteration [X], we committed to [Y] story points and completed [Z]. 
> Our main achievements were [list 2-3 key features]. We faced challenges 
> with [brief mention] but overcame them by [solution]."

### 2. Feature Demonstration (3 minutes)
**Speaker:** Developer who built the feature
- Live demo of working features
- Show user journey through the system
- Highlight integration points

**Demo Flow Example for Iteration 1:**
1. **Student Registration**
   ```bash
   python clinic.py register --name "John Doe" --email "john@student.wethinkcode.co.za" --student-no "12345"
   ```

2. **Volunteer Registration**
   ```bash
   python clinic.py register --name "Jane Smith" --email "jane@student.wethinkcode.co.za" --student-no "67890" --volunteer
   ```

3. **Data Persistence Verification**
   ```bash
   python clinic.py list-users
   ```

### 3. Technical Highlights (1 minute)
**Speaker:** Technical Lead
- Architecture decisions made
- Integration challenges solved
- Code quality metrics

**Key Points:**
- Testing coverage achieved
- Performance considerations
- Security implementations
- Error handling approaches

## Iteration-Specific Demo Plans

### Iteration 1 Demo: Foundation
**Features to Demo:**
- [ ] Student registration via CLI
- [ ] Volunteer registration via CLI
- [ ] Data persistence (JSON storage)
- [ ] Basic error handling
- [ ] Help documentation

**Technical Highlights:**
- Project structure and modularity
- Input validation implementation
- File-based data storage
- CLI argument parsing

**Demo Script:**
```bash
# Show help system
python clinic.py --help

# Register a student
python clinic.py register --name "Alice Johnson" --email "alice@student.wethinkcode.co.za" --student-no "11111"

# Register a volunteer
python clinic.py register --name "Bob Wilson" --email "bob@student.wethinkcode.co.za" --student-no "22222" --volunteer

# Show registered users
python clinic.py list-users

# Show data persistence
cat data.json
```

### Iteration 2 Demo: Time Management
**Features to Demo:**
- [ ] Volunteer slot creation
- [ ] Available slot viewing
- [ ] Basic Google Calendar integration
- [ ] Slot validation

**Demo Script:**
```bash
# Add volunteer slots
python clinic.py add-slot --email "bob@student.wethinkcode.co.za" --date "2024-01-15" --time "14:00" --duration 60

# View available slots
python clinic.py list-slots

# Show Google Calendar integration
# (Open Google Calendar to show created event)
```

### Iteration 3 Demo: Booking System
**Features to Demo:**
- [ ] Session booking
- [ ] Calendar event creation
- [ ] Booking confirmation
- [ ] Slot availability updates

**Demo Script:**
```bash
# Book a session
python clinic.py book --student-email "alice@student.wethinkcode.co.za" --slot-id "12345" --description "Help with Python loops"

# Show booking confirmation
python clinic.py list-bookings

# Verify calendar integration
# (Show Google Calendar with booking details)
```

### Iteration 4 Demo: Advanced Features
**Features to Demo:**
- [ ] Booking cancellation
- [ ] Advanced CLI features
- [ ] Error handling and recovery
- [ ] Performance optimizations

### Iteration 5 Demo: Final System
**Features to Demo:**
- [ ] Complete user journey
- [ ] System reliability
- [ ] Performance metrics
- [ ] Documentation completeness

## Q&A Preparation

### Technical Questions to Expect
1. **"How does your Google Calendar integration work?"**
   - Explain OAuth2 flow
   - Show token management
   - Demonstrate event creation/deletion

2. **"What happens if the Google API is unavailable?"**
   - Show error handling
   - Explain fallback mechanisms
   - Demonstrate graceful degradation

3. **"How do you ensure data consistency?"**
   - Explain validation rules
   - Show transaction handling
   - Demonstrate error recovery

4. **"Can you walk through the code for [specific feature]?"**
   - Be prepared to show and explain any code
   - Highlight design patterns used
   - Explain testing approach

### Code Explanation Readiness
**Every team member should be able to explain:**
- Overall system architecture
- Their specific contributions
- How components integrate
- Testing strategies used
- Error handling approaches

**Code Review Checklist:**
- [ ] All team members have reviewed main modules
- [ ] Everyone understands the data flow
- [ ] Team can explain design decisions
- [ ] Testing approach is clear to all
- [ ] Integration points are understood

## Demo Environment Setup

### Pre-Demo Checklist (30 minutes before)
- [ ] Test environment is working
- [ ] Demo data is prepared
- [ ] Google Calendar access is confirmed
- [ ] Backup demo environment is ready
- [ ] All team members know their parts
- [ ] Screen sharing is tested

### Demo Data Preparation
```bash
# Create clean demo environment
rm -f data.json
rm -f token.json

# Prepare demo users
python clinic.py register --name "Demo Student" --email "demo.student@wethinkcode.co.za" --student-no "99999"
python clinic.py register --name "Demo Volunteer" --email "demo.volunteer@wethinkcode.co.za" --student-no "88888" --volunteer

# Add demo slots (for later iterations)
python clinic.py add-slot --email "demo.volunteer@wethinkcode.co.za" --date "2024-01-20" --time "10:00" --duration 30
```

### Backup Plans
- **Technical Failure:** Have screenshots/videos ready
- **Network Issues:** Use local demo environment
- **Code Issues:** Have previous working version ready
- **Team Member Absence:** Ensure others can cover their parts

## Post-Demo Actions

### Immediate (Within 1 hour)
- [ ] Document all feedback received
- [ ] Note any bugs discovered during demo
- [ ] Update backlog with new requirements
- [ ] Schedule team debrief meeting

### Within 24 hours
- [ ] Create GitLab issues for feedback items
- [ ] Update Miro board with lessons learned
- [ ] Plan fixes for any critical issues
- [ ] Prepare retrospective agenda

### Feedback Integration
- **Positive Feedback:** Document what worked well
- **Improvement Suggestions:** Prioritize and plan implementation
- **Bug Reports:** Create immediate fix plan
- **New Requirements:** Assess impact on remaining iterations

## Success Metrics
- [ ] Demo completed within time limit
- [ ] All planned features demonstrated successfully
- [ ] Team answered technical questions confidently
- [ ] Received constructive feedback
- [ ] No critical bugs discovered
- [ ] Stakeholders expressed confidence in progress
