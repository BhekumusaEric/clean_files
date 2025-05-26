# Code Clinic Project - GitLab Setup Guide

## GitLab Project Structure

### Repository Setup
1. **Main Branch Protection**
   - Protect main branch from direct pushes
   - Require merge requests for all changes
   - Require at least 1 approval for merge requests

2. **Branch Strategy**
   - `main` - Production-ready code
   - `develop` - Integration branch for features
   - `feature/story-id-description` - Individual feature branches
   - `hotfix/issue-description` - Critical bug fixes

### Issue Board Configuration

#### Labels Setup
Create the following labels for issue management:

**Priority Labels:**
- `priority::high` (Red)
- `priority::medium` (Orange)  
- `priority::low` (Yellow)

**Type Labels:**
- `type::user-story` (Blue)
- `type::bug` (Red)
- `type::technical-task` (Purple)
- `type::epic` (Dark Blue)

**Status Labels:**
- `status::ready` (Green)
- `status::in-progress` (Orange)
- `status::review` (Yellow)
- `status::blocked` (Red)
- `status::done` (Dark Green)

**Epic Labels:**
- `epic::user-management` (Light Blue)
- `epic::time-slots` (Light Green)
- `epic::booking-system` (Light Purple)
- `epic::calendar-integration` (Light Orange)
- `epic::cli-interface` (Light Yellow)
- `epic::data-persistence` (Light Gray)

#### Issue Templates

**User Story Template:**
```markdown
## User Story
**As a** [user type]  
**I want** [functionality]  
**So that** [benefit]

## Acceptance Criteria
- [ ] Criterion 1
- [ ] Criterion 2
- [ ] Criterion 3

## Definition of Done
- [ ] Code is written and tested
- [ ] Unit tests pass
- [ ] Code is reviewed
- [ ] Documentation updated
- [ ] Feature is demo-ready

## Story Points
Estimate: [1, 3, 5, 8, 13]

## Dependencies
- [ ] Dependency 1
- [ ] Dependency 2

## Notes
[Additional context or technical notes]
```

**Bug Report Template:**
```markdown
## Bug Description
Brief description of the bug

## Steps to Reproduce
1. Step 1
2. Step 2
3. Step 3

## Expected Behavior
What should happen

## Actual Behavior
What actually happens

## Environment
- OS: [e.g., Ubuntu 20.04]
- Python Version: [e.g., 3.9.0]
- Browser (if applicable): [e.g., Chrome 95.0]

## Screenshots/Logs
[Attach relevant screenshots or log files]

## Priority
[High/Medium/Low]
```

### Issue Board Columns
Set up the following columns in your GitLab issue board:

1. **Backlog** - All unassigned stories
2. **Ready** - Stories ready for development
3. **In Progress** - Currently being worked on
4. **Review** - Code review in progress
5. **Testing** - Feature testing phase
6. **Done** - Completed and merged

### Milestone Setup
Create milestones for each iteration:

- **Iteration 0: Planning & Setup** (Week 1)
- **Iteration 1: Core Features** (Week 2)
- **Iteration 2: Integration** (Week 3)
- **Iteration 3: Enhancement** (Week 4)
- **Iteration 4: Polish & Testing** (Week 5)

### Merge Request Templates

**Feature Merge Request Template:**
```markdown
## Description
Brief description of changes

## Related Issues
Closes #[issue-number]

## Changes Made
- [ ] Change 1
- [ ] Change 2
- [ ] Change 3

## Testing
- [ ] Unit tests added/updated
- [ ] Manual testing completed
- [ ] All tests pass

## Screenshots
[If applicable, add screenshots of UI changes]

## Checklist
- [ ] Code follows team standards
- [ ] Self-review completed
- [ ] Documentation updated
- [ ] No merge conflicts
```

### CI/CD Pipeline Setup

**`.gitlab-ci.yml` Template:**
```yaml
stages:
  - test
  - lint
  - security

variables:
  PIP_CACHE_DIR: "$CI_PROJECT_DIR/.cache/pip"

cache:
  paths:
    - .cache/pip/
    - venv/

before_script:
  - python -V
  - pip install virtualenv
  - virtualenv venv
  - source venv/bin/activate
  - pip install -r requirements.txt

test:
  stage: test
  script:
    - python -m pytest tests/ -v --cov=src/
  coverage: '/TOTAL.+?(\d+\%)$/'
  artifacts:
    reports:
      coverage_report:
        coverage_format: cobertura
        path: coverage.xml

lint:
  stage: lint
  script:
    - flake8 src/
    - black --check src/

security:
  stage: security
  script:
    - bandit -r src/
```

### Project Wiki Setup
Create the following wiki pages:

1. **Home** - Project overview and quick links
2. **Getting Started** - Setup instructions
3. **API Documentation** - Code documentation
4. **Deployment Guide** - How to deploy the system
5. **Troubleshooting** - Common issues and solutions

### Integration with Miro
1. **Link Issues to Miro Cards**
   - Include GitLab issue URL in Miro card description
   - Use same story ID in both systems

2. **Status Synchronization**
   - Update GitLab issue status when moving Miro cards
   - Use GitLab webhooks to notify team of changes

3. **Daily Workflow**
   - Start with Miro board review in stand-up
   - Move to GitLab for detailed technical work
   - Update both systems at end of day

### Team Workflow

#### Daily Process
1. **Morning Stand-up** (15 mins)
   - Review Miro board
   - Update GitLab issue status
   - Identify blockers

2. **Development Work**
   - Create feature branches from develop
   - Work on assigned GitLab issues
   - Regular commits with meaningful messages

3. **End of Day**
   - Update issue status
   - Create merge requests for completed work
   - Update Miro board

#### Weekly Process
1. **Iteration Planning** (Monday)
   - Review backlog
   - Estimate new stories
   - Assign work for the week

2. **Mid-week Check-in** (Wednesday)
   - Review progress
   - Identify risks
   - Adjust plans if needed

3. **Iteration Demo** (Friday)
   - Demo completed features
   - Gather feedback
   - Update documentation

4. **Retrospective** (Friday)
   - Review what went well
   - Identify improvements
   - Plan action items

### Monitoring and Reporting
- Use GitLab's built-in analytics
- Track velocity using story points
- Monitor merge request metrics
- Review code quality trends
