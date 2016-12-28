<h1>Azra Bot</h1>
#### This is a slack Chat-bot that automates the task of organizing meetings with the team members.


## 1. Objective

The challenge here was to schedule a meeting efficiently at an optimal timing at which full attendance of all the team members is most probable. According to the empirical software analysis, the effectiveness of scrum meetings in today’s agile era depends on collaboration and contribution of each and every team mate. For solving the problem of no-shows or bad-time meetings, we developed a slack chat bot which returns the most convenient time for the team members and thereby assuring their availability while avoiding the tax of manual meeting setup.

Azra bot finds the optimal timing based on following factors:

1.	Each team member is free at that particular time slot
2.	This time slot lies in office work hours i.e. 9 AM to 5 PM
3.	Priorities are given to each time slot such as: Meetings at lunch time should be avoided so they would have lowest priority.
Meetings in early morning should be avoided as employees might be sleepy.
Meetings in afternoon excluding lunch time slot should be given more priority as maximum constructive work is performed during these hours.

Accordingly we have assigned the priorities to each timeslot. So Azra bot will return the most recent time-slot for which all the team members are available and the slot has highest priority. It also takes care that the meeting-hours perfectly fit in schedule and meetings conclude before end of working hours.

This optimal scheduling ensures that:

- Meeting attendees are available at that time slot

- Attendees will be pro-active and this will ensure effectiveness of meetings.

In agile methodology, stand-up meetings, weekly/monthly meetings play very important for success of the project. It has been analyzed that ‘Ineffective meetings’ is one the top four reasons for failure of agile methodology in projects. So with this Azra bot and thereby scheduling meetings at optimal time slot, we can overcome this challenge.  

When we want to add particular team member to existing meeting, we have to check whether that team member is available for that time slot and if not then we must find newer time slot. Checking the availability of each and every team member is cumbersome but using Azra bot we can also add new members to existing meeting and Azra bot returns whether new members are available for that particular time-slot. If the new members are busy then we can cancel the existing meeting and reschedule so as to confirm that all the team members attend the meeting. This functionality of Azra bot also solved and reduced the efforts of manual lookup into every team members’ calendars to find free time.

To summarize, Azra bot solves challenges in:

- Finding optimal time when team members are available and are highly productive.

- Adjusting or updating the time slot when we add new member to existing meeting and she is unavailable for that particular time-slot.

- Scheduling the meetings directly into google calendars of team members. (Automation of scheduling meetings)

- Cancelling or updating meetings directly into google calendars of team members. (Automation of updating meetings)


## 2. Primary Features

The bot has three main features: it can create, update and delete meetings for a Slack team. The organizer has options of providing constraints on the max time, and date on the meeting. The bot then looks up the Google calendars of the meeting attendees and provides a suitable meeting time for them.

##### Priority feature

Currently, the bot decides the meeting time based on two main constraints: the availability of attendees and the higher priorities that we have given to times around 10-11 am and after 2 pm, the time slots which have been found to be the most productive for software engineers.

##### Functionalities

1. Google Calendar API authorization

Every user on the Slack team needs to authorize the access to his/her Calendar for Azra. This is done by entering '@azra auth' on any channel. This provides a link for the user on the personal chat with azra where he needs to give the private access token. This way, the user gives Calendar access to Azra.

2. Setting up meeting

The bot can create a meeting for a list of attendees whose calendars it has authorization to. The triggers are '@azra setup' or '@azra schedule'. The bot takes the emails of attendees, the duration, and the constraints on date and time, if any, as inputs. The bot then returns the suitable time for the team to have the meeting. The organizer can either accept or decline the meeting suggestion.

3. Adding a new member to a meeting

The bot can add a new member to an existing meeting. The trigger is '@azra add'. The bot asks for the new member email ID and the meeting ID to which the member has to be added to. The bot answers by either saying that the meeting has been updated or it can't add the new member because he was busy.

4. Canceling a meeting

The bot can cancel a meeting with the trigger '@azra cancel'. The bot asks for the meeting ID to be cancelled. Then cancels its from the calendars of the members of the meeting.
