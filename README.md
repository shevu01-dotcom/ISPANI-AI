Name: ISPANI SmartWork AI Assistant
Purpose:
A workplace AI assistant that helps employees and managers save time by generating professional emails, converting meeting notes into actionable summaries, and creating structured daily or weekly task plans.

Main dashboard

Your prototype can have a simple dashboard:

              SMARTWORK AI ASSISTANT
        Your AI-powered workplace productivity tool
        
        
 ┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐
 │  📧 Email       │ │  📝 Meetings    │ │  📅 Task Planner │
 │  Generator      │ │  Summarizer     │ │  & Scheduler    │
 └─────────────────┘ └─────────────────┘ └─────────────────┘

             
              ⚠ Responsible AI Notice
 AI-generated content may contain errors. Always review
 information before sending, sharing or acting on it.
Smart Email Generator
User inputs

The user selects:

Audience

Client
Manager
Team
Colleague

Tone

Formal
Casual
Persuasive
Professional

Purpose

Meeting request
Follow-up
Apology
Thank you
Project update
Request for information

Additional information

Example:

"The project deadline has moved from Friday to Monday. Ask the team to submit their outstanding work by Thursday."

AI output

The system generates:

Subject
Greeting
Email body
Closing
Appropriate tone for the selected audience
Prompt design

Use a structured prompt rather than simply asking:

"Write an email."

A better prompt is:

You are a professional workplace communication assistant.

Generate an email using the following requirements:

Audience: {audience}
Tone: {tone}
Purpose: {purpose}
Context: {user_input}

Requirements:
Keep the message clear and concise.
Adapt the language to the selected audience.
Do not invent facts, dates, names or commitments.
Maintain a professional and respectful tone.
Include an appropriate subject line.
If important information is missing, identify it instead
   of making assumptions.

Return:
Subject:
Email:

This demonstrates prompt engineering because you are controlling the AI's role, inputs, constraints and output format.
Meeting Notes Summarizer

The user pastes meeting notes or uploads/transcribes them.

Example input
Project meeting – 17 September

Sarah will complete the marketing report by Friday.
John will contact the client about the new requirements.
The team agreed that the product launch will take place
on 30 September.

The budget needs to be reviewed before launch.
Mary suggested adding another testing phase.
The team agreed to discuss this at the next meeting.
AI output

Your prototype should automatically identify:

Meeting Summary

A short overview of what was discussed.

Key Decisions
Decision	Details
Product launch	30 September
Budget	Must be reviewed before launch
Testing	Additional testing to be discussed
Action Items
Task	Responsible person	Deadline
Complete marketing report	Sarah	Friday
Contact client	John	Not specified
Review budget	Not specified	Before launch
Prompt
You are a meeting productivity assistant.

Analyse the meeting notes below.

Extract and clearly separate:

Meeting summary
Key decisions
Action items
Responsible person for each action
Deadlines
Unresolved issues

Important rules:
- Only use information contained in the meeting notes.
- Do not invent names, deadlines or decisions.
- If information is missing, write "Not specified".
- Distinguish between decisions and suggestions.
- Present action items in a table.

Meeting notes:
{meeting_notes}

This is a strong example of structured extraction prompting.
AI Task Planner / Scheduler

The user enters their tasks.

Example:

Prepare project report
Respond to client emails
Team meeting
Update project budget
Complete presentation
Research competitors

The user can also provide:

Available working hours
Date
Task duration
Priority
Deadline
Priority levels

Use:

🔴 High — urgent/important
🟡 Medium — important but not urgent
🟢 Low — can be completed later

Example output

Thursday – Daily Plan

Time	Task	Priority
08:30–09:30	Prepare project report	🔴 High
09:30–10:00	Respond to client emails	🔴 High
10:00–11:00	Team meeting	🔴 High
11:15–12:00	Update project budget	🟡 Medium
13:00–14:00	Complete presentation	🟡 Medium
14:00–15:00	Research competitors	🟢 Low
Prompt
You are an AI task planning assistant.

Create a realistic {daily/weekly} work schedule.

Tasks:
{tasks}

Available working hours:
{working_hours}

Deadlines:
{deadlines}

Priority information:
{priorities}

Requirements:
Prioritise urgent and deadline-sensitive tasks.
Avoid scheduling overlapping tasks.
Include reasonable breaks.
Do not schedule work outside the user's available hours.
Do not invent deadlines.
Identify tasks where insufficient information is provided.
Explain briefly why high-priority tasks were scheduled first.

Return the result as:
- Schedule
- Priority level
- Reason for priority
- Unscheduled/deferred tasks
Responsible AI safeguards — 10% of grading

This section is important because your prototype should demonstrate that you understand AI limitations, rather than simply showing that the AI works.

A. Disclaimer

Display this on the application:

Responsible AI Notice:
This application uses artificial intelligence to generate and organise information. AI-generated content may contain errors, omissions or inappropriate assumptions. Users must review and verify outputs before sending emails, making decisions, assigning responsibilities or taking action.

You can also display a warning before sending an email:

⚠️ Review before sending: Please verify names, dates, recipients, commitments and other important information.

B. Validation steps

Build a simple validation process into each feature.

Email

Before displaying "Send":

✓ Recipient checked
✓ Tone selected
✓ Names verified
✓ Dates verified
✓ AI-generated content reviewed

The user should have to click:

"I have reviewed this email"

before the prototype allows the email to be copied/sent.

Meeting summarizer

Show:

Source verification:
The summary was generated from the meeting notes provided. Verify action owners and deadlines against the original meeting record.

Task planner

Show:

Planning reminder:
AI-generated schedules are suggestions. Check workload, deadlines and availability before relying on the schedule.
Handling AI limitations and bias

Include a dedicated Responsible AI section in your prototype.

Explain that the model can:

Misinterpret ambiguous meeting notes.
Generate incorrect information.
Assign an action to the wrong person if notes are unclear.
Misunderstand tone or workplace context.
Produce biased or inappropriate wording.
Over-prioritise tasks if insufficient information is provided.
Your solution

The prototype should therefore:

Never invent missing information.
Mark missing information as "Not specified."
Ask users to verify important information.
Keep a human in control of final decisions.
Allow users to edit AI-generated content.
Clearly label AI-generated outputs.
Provide the original meeting notes alongside the summary where possible.
Avoid using sensitive personal information unnecessarily.

Recommended prototype technology

For a relatively simple assessment prototype, you can use:

Front end

Lovable for creating the web application interface.

AI

An LLM API such as the OpenAI API or another approved AI model.

Data

A simple database such as Supabase if you need to save:

Tasks
Meeting summaries
Generated emails
User preferences
Optional tools
ChatGPT — prompt development/testing
Gemini — comparison/testing
Notion AI — research/productivity comparison
Lovable — application prototype
Supabase — database/authentication

If your assessment doesn't require a production backend, you can keep the prototype simpler and use sample data.
Suggested Lovable build prompt

If you're building this in Lovable, you can start with a prompt like this:

Build a modern responsive web application called
"SmartWork AI Assistant".

The application is an AI-powered workplace productivity
assistant with three main features:

Smart Email Generator
Meeting Notes Summarizer
AI Task Planner & Scheduler

Create a clean professional dashboard with three feature cards.

EMAIL GENERATOR:
- Allow users to select audience: Client, Manager, Team,
  Colleague.
- Allow tone selection: Formal, Casual, Persuasive,
  Professional.
- Allow the user to select the email purpose.
- Provide a large text area for context.
- Generate an email with subject, greeting, body and closing.
- Include Edit, Regenerate and Copy buttons.
- Include a "Review before sending" warning.

MEETING SUMMARIZER:
- Provide a large text area for meeting notes.
- Generate:
  - Meeting summary
  - Key decisions
  - Action items
  - Responsible people
  - Deadlines
  - Unresolved issues
- Display action items in a table.
- Use "Not specified" when information is missing.
- Include an AI verification warning.

TASK PLANNER:
- Allow users to enter multiple tasks.
- Allow priority selection: High, Medium, Low.
- Allow deadlines and estimated duration.
- Allow daily or weekly planning.
- Allow users to specify working hours.
- Generate a structured schedule.
- Display tasks in a timeline/calendar-style interface.
- Identify unscheduled tasks.

RESPONSIBLE AI:
Create a visible Responsible AI panel explaining:
- AI outputs may contain errors.
- Users must verify important information.
- AI must not invent missing information.
- AI-generated schedules are recommendations.
- Users remain responsible for final decisions.

Add a global AI disclaimer:
"AI-generated content may contain errors. Please review
and verify outputs before relying on them."

Use a professional, accessible and responsive UI.

