# Calendar service

## Contents

- [Calendar service](#calendar-service)
	- [Contents](#contents)
	- [Description](#description)
	- [Backlog](#backlog)

## Description

This is the microservice dedicated to calendar management. After studying the possible implementation solutions it was agreed that:

- The microservice will make use of the Google Calendar service
- The microservice will be implemented in Typescript (Developer preference)

## Backlog

- [x] Connect to Google Cloud Platform
- [x] Get all events in calendar
- [x] Get events by participant
- [ ] Get events by type
- [x] Get events in range of time
- [x] Create event
- [ ] Add event types
- [ ] Check if time slot if empty before adding the event
- [ ] Attach a meeting to the event
- [ ] Add participants to the event
- [x] Delete an event by ID
- [ ] Delete an event by participant
- [ ] Delete an event in time range
- [ ] Update event info
- [ ] Check if time slot if empty before updating event start and end dates
- [ ] Add/remove participants
- [ ] Move a set of events from a range of time to another
- [ ] Add medicine taking management (example: take 2 pills of X 3 times a day)
- [ ] Add regular doctor checkups
- [ ] Notify user by upcoming events
