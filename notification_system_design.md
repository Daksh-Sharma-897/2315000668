# Notification Priority Inbox System Design

## Objective

Display the most important notifications to users based on category importance and recency.

## Categories

* Security Alerts → Weight 5
* Academic Deadlines → Weight 3
* Event Reminders → Weight 2
* Administrative Notices → Weight 1

## Priority Formula

Priority Score = Weight × e^(-λ × DaysSinceSent)

Where λ = 0.1

## Flow

1. Load notifications.
2. Calculate priority score.
3. Sort notifications in descending order.
4. Return top 10 notifications.

## Components

### Logging Middleware

Logs all incoming requests.

### Backend

* Stores notifications
* Calculates priority scores
* Sorts notifications
* Returns top 10 notifications

### Frontend

* Fetches notifications from backend
* Displays them in priority order

## Time Complexity

Priority Calculation: O(n)

Sorting: O(n log n)

Top 10 Extraction: O(10)
