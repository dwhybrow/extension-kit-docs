# Scheduled event

The **Scheduled event** trigger allows a flow to be initiated on a regular basis, based on a user-configured schedule. This trigger is ideal for automating recurring tasks without manual intervention.

## Trigger input

![Image 4: Scheduled event trigger config](https://docs-external.u4pp.com/extensions-kit/images/built-in-triggers/scheduled-event-trigger.png)

### Basic configuration

| **Field** | **Description** | **Required** |
| --- | --- | --- |
| _Occurs_ | Select how often the event should occur from the drop-down: [Daily](https://docs-external.u4pp.com/extensions-kit/built-in-triggers/scheduler/#basic-configuration-daily), [Weekly](https://docs-external.u4pp.com/extensions-kit/built-in-triggers/scheduler/#basic-configuration-weekly), or [Monthly](https://docs-external.u4pp.com/extensions-kit/built-in-triggers/scheduler/#basic-configuration-monthly). | Yes |

#### Basic configuration: Daily

| **Field** | **Description** |  | **Required** |
| --- | --- | --- | --- |
| _Occurs_ | Select _Every_ or _Once at_ from the drop-down. |  | Yes |
| _Every_ | Select to schedule multiple events within a day at a regular interval. |  |  |
|  | _Recurs every (days)_ | Specify the interval, in days, between each scheduled event. For example, set to `1` to trigger the event every day, `2` for every other day and so forth. | Yes |
|  | _Recurrence unit_ | Specify the unit in hours or minutes. | Yes |
|  | _Recurrence amount_ | Enter the amount for the specified unit. | Yes |
|  | _Starting at time (UTC + 00:00)_ | Enter the starting time for the event. | No |
|  | _Ending at time (UTC + 00:00)_ | Enter the ending time for the event. | No |
| _Once at_ | Select _Once at_ to schedule a single event at a specific time of day. |  | Yes |
|  | _Recurs every (days)_ | Specify the interval, in days, between each scheduled event. For example, set to `1` to trigger the event every day, `2` for every other day and so forth. | Yes |
|  | _At time (UTC + 00:00)_ | Enter the time for the event. | No |
| _Starting on after_ | Select the start day and month for the event. |  | No |
| _Ending on_ | Select the end day and month for the event. |  | No |

**Example with the _Every_ property:**

If you set "Every day every 2 hours" between 08:00 and 18:00, the event will trigger at 08:00, 10:00, 12:00, 14:00, 16:00, and 18:00.

**Example with the _Once at_ property:**

If you set "Once at 09:30," the event will trigger only at 09:30 each day.

#### Basic configuration: Weekly

| **Field** | **Description** |  | **Required** |
| --- | --- | --- | --- |
| _Recurs every (Weeks)_ | Specify the interval, in weeks, between each scheduled event. For example, set to `1` to trigger the event every week, `2` for every other week and so forth. |  | Yes |
| _Daily checkboxes_ | Select one or more checkboxes for the days of the week on which the event should occur. |  | No |
| _Occurs_ | Select _Every_ or _Once at_ from the drop-down. |  | Yes |
| _Every_ | Select to schedule multiple events on selected days of the week at a regular interval. |  |  |
|  | _Recurrence unit_ | Specify the unit in hours or minutes. | Yes |
|  | _Recurrence amount_ | Enter the amount for the specified unit. | Yes |
|  | _Starting at time (UTC + 00:00)_ | Enter the starting time for the event. | No |
|  | _Ending at time (UTC + 00:00)_ | Enter the ending time for the event. | No |
| _Once at_ | Select to schedule a single event at a specific time of day on the selected days of the week. |  | Yes |
|  | _At time (UTC + 00:00)_ | Enter the time for the event. | No |
| _Starting on after_ | Select the start day and month for the event. |  | No |
| _Ending on_ | Select the end day and month for the event. |  | No |

**Example with the _Every_ property:**

If you select _Monday, Wednesday,_ and _Friday_, and set "Every 2 hours" between 08:00 and 18:00, the event will trigger at 08:00, 10:00, 12:00, 14:00, 16:00, and 18:00 on each of those days.

**Example with the _Once at_ property:**

If you select _Tuesday_ and _Thursday_ and set "Once at 09:30," the event will trigger only at 09:30 on each Tuesday and Thursday.

#### Basic configuration: Monthly

| **Field** | **Description** |  | **Required** |
| --- | --- | --- | --- |
| _Frequency_ | Select _Day_ or _The_ from the drop-down. |  | Yes |
| _Day_ | Select to schedule events on a specific numbered day of the month |  |  |
|  | _Day_ | Enter the exact day number. For example, set to `27` to trigger the event on the 27th day of the month. | Yes |
| _The_ | Select to schedule events using pattern-based day selection. For example, First Monday, Last Friday, or Third Wednesday of the month. |  |  |
|  | _The_ | Select the pattern from the drop-down. | Yes |
|  | _Day name_ | Select the name of the day for the pattern. | Yes |
| _Recurs every (Months)_ | Specify the interval, in months, between each scheduled event. For example, set to `1` to trigger the event every month, `2` for every other month and so forth. |  | Yes |
| _Occurs_ | Select _Every_ or _Once at_ from the drop-down. |  | Yes |
| _Every_ | Select to schedule multiple events on selected days of the week at a regular interval. |  |  |
|  | _Recurrence unit_ | Specify the unit in hours or minutes. | Yes |
|  | _Recurrence amount_ | Enter the amount for the specified unit. | Yes |
|  | _Starting at time (UTC + 00:00)_ | Enter the starting time for the event. | No |
|  | _Ending at time (UTC + 00:00)_ | Enter the ending time for the event. | No |
| _Once at_ | Select to schedule a single event at a specific time of day on the selected days of the week. |  | Yes |
|  | _At time (UTC + 00:00)_ | Enter the time for the event. | No |
| _Starting on after_ | Select the start day and month for the event. |  | No |
| _Ending on_ | Select the end day and month for the event. |  | No |

**Example with _Day_ and _Every_ properties:**

If you set "Every 2 hours" on the 15th of each month between 08:00 and 18:00, the event will trigger at 08:00, 10:00, 12:00, 14:00, 16:00, and 18:00 on the 15th of every month.

**Example with _The_ and _Once at_ properties:**

If you set "Once at 09:30" on the last Friday of every other month, the event will trigger only at 09:30 on the last Friday of every two months.

## Trigger output

| **Property** | **Description** |
| --- | --- |
| _TriggerDateTime_ | The date and time the event was triggered. |

![Image 5: Scheduled event trigger config](https://docs-external.u4pp.com/extensions-kit/images/built-in-triggers/scheduled-event-trigger-output.png)
