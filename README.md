# AI Voice Receptionist

A browser-based AI voice receptionist that qualifies callers, checks live availability, books appointments, logs calls, and handles unsuccessful requests safely.

## Overview

This project demonstrates how a service business can respond to callers outside normal working hours without relying entirely on voicemail or manual call handling.

The receptionist holds a natural voice conversation, identifies the reason for the call, collects the necessary details, checks the business calendar, and books an available appointment.

## The Problem

Service businesses can lose valuable enquiries when calls arrive after hours, during busy periods, or when staff members are unavailable.

A missed call may mean:

- A lost appointment
- A potential customer contacting a competitor
- Incomplete caller information
- Extra administrative work for the business owner

## What the System Does

The system:

1. Welcomes the caller and identifies the reason for the call.
2. Collects the caller’s name and relevant information.
3. Asks qualifying questions based on the requested service.
4. Checks live availability in Google Calendar.
5. Offers available appointment times.
6. Books the caller’s selected time.
7. Logs the conversation and booking.
8. Sends the business owner a written summary.
9. Captures a callback request when the booking cannot be completed.

## Workflow Architecture

The Vapi assistant manages the voice conversation and calls n8n tools when it needs to check availability, book an appointment, or request a callback.

The n8n workflow connects the assistant to:

- Google Calendar for live availability and booking
- Google Sheets for call and lead logging
- Gmail for owner notifications

## Key Design Decision

The receptionist does not guess when the calendar or booking system is unavailable.

Instead, it apologises and captures a callback request. This turns a technical failure into a recoverable lead rather than creating a false or duplicate appointment.

## Failure Handling

The system was designed to handle:

- Fully booked days
- Unavailable requested times
- Calendar or tool failures
- Incomplete caller information
- Unsupported requests
- Calls that require human attention

## Tech Stack

- Vapi
- n8n
- Google Calendar
- Google Sheets
- Gmail
- JavaScript
- Webhooks

## Screenshots

### Workflow Canvas

![AI Voice Receptionist workflow](screenshots/workflow-canvas.png)


## Demo

Recorded walkthrough coming shortly.

## Repository Contents

- `voice-receptionist.json` — sanitised n8n workflow export
- `screenshots/workflow-canvas.png` — workflow architecture

## Security

Credentials, API keys, personal information, account identifiers, and live webhook URLs have been removed from the public workflow export.

Anyone importing the workflow must connect their own accounts and replace the placeholder configuration values.

## Status

Completed and tested as a portfolio demonstration. The workflow can be adapted to the calendar, qualification rules, services, and escalation process of a specific business.
