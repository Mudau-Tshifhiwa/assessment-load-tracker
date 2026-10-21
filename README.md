# Assessment Load Tracker

A web system that helps students and lecturers keep the number of tests and quizzes per week under control, so students are not overwhelmed.


## Problem

Students sometimes face too many tests and quizzes in one week, which can hurt their performance. Lecturers usually cannot see what other modules are scheduling.

## What the system does

- Students see how many tests and quizzes they are writing each week.
- Lecturers schedule assessments in the system, which notifies the students.
- Before an assessment is saved, the system checks the enrolled students' load for that week. If any student already has **3** assessments, the lecturer gets a warning.
- If the lecturer proceeds anyway, the override is stored with a reason, so it can be reviewed later.

## Key rules

- A week runs **Monday to Friday**. Assessments can only be scheduled on weekdays.
- The weekly limit is **3** and is a configurable setting.
- Assessments created by lecturers are official. Students can also add personal assessments, which never trigger lecturer warnings.
- Overriding a warning requires a reason, and every override is logged.

## Roles

- **Student:** enrols in modules, views weekly load, adds personal assessments, reads notifications.
- **Lecturer:** manages modules and assessments, sees warnings, can override with a reason.
- **Admin:** reviews all overrides.

## Functional requirements

### Accounts and roles
- [ ] **FR1** Users can register and log in as a Student or a Lecturer.
- [ ] **FR2** A student can only see their own data. A lecturer can only manage their own modules.

### Modules and enrolment
- [ ] **FR3** A lecturer can create modules (code, name).
- [ ] **FR4** A student can enrol in or leave modules.

### Assessments
- [ ] **FR5** A lecturer can create, edit, and delete an assessment for their module (title, type: quiz or test, date, optional time and venue). The date must be a weekday.
- [ ] **FR6** A student can add a personal assessment (title, date, optional module).
- [ ] **FR7** Each assessment's type and date are stored and can be queried by week.

### Student view
- [ ] **FR8** A student sees a weekly view of all their assessments (official and personal) with a count for the week.
- [ ] **FR9** Weeks that reach the limit are visibly highlighted.

### Warning system
- [ ] **FR10** When a lecturer saves an assessment, the system finds all students enrolled in that module and counts their existing assessments in that week.
- [ ] **FR11** If any student already has 3 or more, the lecturer sees a warning with the number of affected students and the date.
- [ ] **FR12** The lecturer can cancel, change the date, or proceed.
- [ ] **FR13** If they proceed, they must enter a reason, and the override is saved permanently.
- [ ] **FR14** The system can suggest the nearest weeks with a lighter load.

### Override log
- [ ] **FR15** A lecturer can view their own override history.
- [ ] **FR16** An admin can view all overrides, with filters by lecturer, module, and week.

### Notifications
- [ ] **FR17** When an assessment is created, edited, or deleted, enrolled students get an in-app notification.
- [ ] **FR18** Students can mark notifications as read.

### Out of scope for now
Email or SMS, calendar sync, mobile app, timetable integration.

## Roadmap

- [ ] **Stage 0:** repo, README, branch workflow
- [ ] **Stage 1:** database design (tables on paper, then SQL)
- [ ] **Stage 2:** backend API (login, modules, assessments)
- [ ] **Stage 3:** weekly count query and warning logic
- [ ] **Stage 4:** web pages for students and lecturers
- [ ] **Stage 5:** notifications and override log

## Tech stack

To be decided.

## Learning goals

This project exists to learn full-stack development by building it myself: databases, a backend API, a frontend, and using Git and GitHub to track the work.

## Git workflow

- One GitHub Issue per functional requirement.
- One branch per feature, for example `feature/fr10-weekly-count`.
- Small commits with clear messages.
- Merge into `main` through pull requests.
- Tag a release when each stage works.
