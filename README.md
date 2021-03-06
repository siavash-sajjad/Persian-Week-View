Android Week View
=================

**Android Week View for iranian** is an android library to display calendars (week view or day view) within the app. It supports custom styling.

![](images/screen-shot1.png)

Features
------------

* Week view calendar
* Day view calendar
* Custom styling
* Horizontal and vertical scrolling
* Infinite horizontal scrolling
* Live preview of custom styling in xml preview window

Who uses it
---------------

* [Series Addict](https://play.google.com/store/apps/details?id=com.alamkanak.seriesaddict)
* Using the library? Just [tweet me](https://twitter.com/alamkanak) or [send me an email](mailto:alam.kanak@gmail.com).

Usage
---------
Write the following code in your java file.

    ```java
    // Get a reference for the week view in the layout.
    mWeekView = (WeekView) findViewById(R.id.weekView);

    // Set an action when any event is clicked.
    mWeekView.setOnEventClickListener(mEventClickListener);

    // The week view has infinite scrolling horizontally. We have to provide the events of a
    // month every time the month changes on the week view.
    mWeekView.setMonthChangeListener(mMonthChangeListener);

    // Set long press listener for events.
    mWeekView.setEventLongPressListener(mEventLongPressListener);
    ```
Implement `WeekView.MonthChangeListener`, `WeekView.EventClickListener`, `WeekView.EventLongPressListener` according to your need.

Provide the events for the `WeekView` in `WeekView.MonthChangeListener.onMonthChange()` callback. Please remember that the calendar pre-loads events of three consecutive months to enable lag-free scrolling.

    ```java
    WeekView.MonthChangeListener mMonthChangeListener = new WeekView.MonthChangeListener() {
        @Override
        public List<WeekViewEvent> onMonthChange(int newYear, int newMonth) {
            // Populate the week view with some events.
            List<WeekViewEvent> events = getEvents(newYear, newMonth);
            return events;
        }
    };
    ```

Customization
-------------------

You can customize the look of the `WeekView` in xml. Use the following attributes in xml. All these attributes also have getters and setters to enable you to change the style dynamically.

- `columnGap`
- `dayBackgroundColor`
- `dayNameLength`
- `eventMarginVertical`
- `eventPadding`
- `eventTextColor`
- `eventTextSize`
- `firstDayOfWeek`
- `headerColumnBackground`
- `headerColumnPadding`
- `headerColumnTextColor`
- `headerRowBackgroundColor`
- `headerRowPadding`
- `hourHeight`
- `hourSeparatorColor`
- `hourSeparatorHeight`
- `noOfVisibleDays`
- `overlappingEventGap`
- `textSize`
- `todayBackgroundColor`
- `todayHeaderTextColor`

Interfaces
----------

Use the following interfaces according to your need.

- `mWeekView.setMonthChangeListener()` to provide events to the calendar
- `mWeekView.setOnEventClickListener()` to get a callback when an event is clicked
- `mWeekView.setEventLongPressListener()` to get a callback when an event is long pressed
- `mWeekView.setEmptyViewClickListener()` to get a callback when any empty space is clicked
- `mWeekView.setEmptyViewLongPressListener()` to get a callback when any empty space is long pressed
- `mWeekView.setDateTimeInterpreter()` to set your own labels for the calendar header row and header column
- `mWeekView.setScrollListener()` to get an event every time the first visible day has changed

To do
-------

* Add event touch feedback selector
* Show events that expand multiple days properly

Changelog
---------

**Version 1.2.3**

* Get callbacks when scrolling horizontally
* `goToHour` and `goToDate` methods has been fixed
* Use `getFirstVisibleHour` method to get the first visible hour in the week view

**Version 1.2.1**

* Better scrolling added
* Get callbacks when empty view is tapped/long pressed
* Control the speed of scrolling
* Support for multiple language added
* Ability to set your own interpreter for header row and column added

**Version 1.1.7**

* You can now dynamically scroll to an hour of your preference.

**Version 1.1.6**

* Added support for events that expands to multiple days

**Version 1.1.5**

* A bug related to overlapping events fixed
* You can now programmatically get first and last visible day in the week view

**Version 1.1.4**

* Small bug fixed

**Version 1.1.3**

* Margins support added for overlapping events

**Version 1.1.2**

* Small bugs fixed
* Hour separator inconsistency fixed

**Version 1.1.1**

* Overlapping event bug fixed

**Version 1.1.0**

* Added support for overlapping events

License
----------

    Copyright 2014 Raquib-ul-Alam

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
