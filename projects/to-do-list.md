# To-Do List Application

## Synopsis

Allows the user to manage their individual to-do list and see what
they've accomplished.

## Functional Requirements

### Tasks

The basic unit of data in a to-do list is a _task_, which we define
as a one-line text description. A given _task_ may have additional
information associated with it via one or more unordered _properties_.
We will define _properties_ more fully in the next section.

Operations on tasks include:

  * Add task
  * Delete task
  * Change description of task
  * Add property to task
  * Remove property from task

### Properties

Task properties are used for on-screen task ordering and filtering. A
_task_ may only possess one _property_ of a given type: conversely,
therefore, a _task_ may have at most N _properties_ where N is the
number of property types.

Types of properties (data type):

  * Priority (integer, range 1-3)
  * Due date (date)
  * Tag (string)
  * Created (datetime)
  * Completed (datetime)

Operations on properties:

  * Add property to task
  * Remove property from task
  * Alter property value

## Interface Requirements

### Medium

May be web-based or native GUI, but not a command-line interface. If
web-based, must accomodate multiple users; this can be done via
`localStorage` or similar if desired.

### Task List

This is the only screen in the application, and it should be displayed
as soon as the application is opened. All non-completed tasks appear in
a vertical list. The list entry for each task should contain a
representation of its properties.

An unchecked check box must appear to the left of each task in the list.
When the user checks the box to the left of a given task, that task must
be marked as completed at the time of the user's click and it should
disappear from the list. (Optional touch controls: a swipe gesture from
left to right across the task entry should behave as if the user checked
the task's check box.)

A small 'no passage' icon must appear to the right of each task in the
list. When the user clicks on the icon, a 'delete' button or icon should
slide into view from the right side of the task entry. If the user then
clicks on the 'delete' icon, then the task should be deleted. If the
user clicks somewhere else instead, then the 'delete' icon should slide
out of view again. (Optional touch controls: a swipe gesture from right
to left across the task entry should behave as if the user clicked on
the 'no passage' icon.)

By default, tasks are ordered on-screen according to this hierarchy:

  1. Due date (descending)
  2. Priority (descending)
  3. Created (descending)

The user can select an alternative sort order from a drop-down located
above the task list. The list should consist of ascending and descending
sort orders for each property type except 'Completed', plus a dummy
entry of '(default)'. Selecting an option from this list overrides the
default sort order hierarchy and remains in effect until another
selection is made.

The user can view completed tasks using a toggle control located above
the task list. This action will change the task list contents to all
completed tasks, each of which should have their check box checked. If
the user unchecks the check box for a completed task, that task must
be marked as incomplete and it should disappear from the list.

While viewing completed tasks, the user may also purge the entire list
of completed tasks by clicking on a button labeled 'Remove completed
tasks' that is located below the task list. After clicking the button
but before any action is carried out, the application must display a
yes/no confirmation dialog. If the user's response is 'yes', then all
completed tasks should be deleted.

## Data Storage Requirements

Any data entered by the user must be saved immediately. If the user
closes the application at any time and subsequently re-opens it, the
application must display the same data that were present last time
the application was closed.
