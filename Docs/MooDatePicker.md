Class: MooDatePicker {#MooDatePicker}
=========================================

MooDatePicker is a simple date picker for MooTools.

### Implements:

[Options][options], [Events][events]

MooDatePicker Method: constructor {#MooDatePicker:constructor}
-------------------------------------------------------------------

### Syntax:

	var myMooDatePicker = new MooDatePicker(elements, options);

### Arguments:

1. elements - (mixed) An Element reference or an [Elements](http://mootools.net/docs/core/Element/Element#Elements) array.
2. options - (object) Options for the class.

### Options:

* prefix: (string: defaults to `moodatepicker-`) The prefix for your CSS classnames.
* offset: (object: defaults to {x: 5, y: -3}) The picker position, relative to the top right corner of the associated element (or top left if there is not enougth space on the right).
* templates: (object) The picker's templates. You can redefine one or more parts of the templates to customize the picker.
	* global: (string) Container template. Available variables: {prefix}, {header}, {calendar}
	* header: (string) Header template. Available variables: {prefix}, {month}
	* calendar: (string) Calendar template. Available variables: {prefix}, {dayHeader}, {week}
	* dayHeader: (string) Day labels template. Available variables: {prefix}, {dayLabel}
	* week: (string) Week template. Available variables: {prefix}, {day}
	* day: (string) Day template. Available variables: {prefix}, {today}, {selected}, {number}
	* dayEmpty: (string) Empty day template. Available variables: {prefix}
* labelLength: (integer: defaults to 1) The length of the day labels. Example: 1 to get M T W etc. , 3 to get Mon Tue Wed etc. or 0 to get the full labels.

### Events:

* onShow (function) Callback to execute when the calendar is displayed
* onHide (function) Callback to execute when the calendar is hidden
* onPick (function) Callback to execute when the user pick a date; passed the picked date as a [Date](https://developer.mozilla.org/en/JavaScript/Reference/Global_Objects/Date) object

### Example:

#### HTML:

    <input name="date" type="text" data-moodatepicker />

#### JavaScript:

	new MooDatePicker(document.getElements('input[data-moodatepicker]'), {
		onPick: function(e, date){
			this.element.set('value', date.format('%e %B %Y'));
		}
	});

MooDatePicker Method: show {#MooDatePicker:show}
-------------------------------------------------------------------

Display the date picker for a given element.

### Syntax:

	myMooDatePicker.show(element);

### Arguments:

1. element - (Element) An Element reference.

### Returns:

* (object) This MooDatePicker instance.

### Example:

#### HTML:

	<input id="date" name="date" type="text" data-moodatepicker />

#### JavaScript:

    var myMooDatePicker = new MooDatePicker(document.getElements('input[data-moodatepicker]'), {
		onPick: function(e, date){
			this.element.set('value', date.format('%e %B %Y'));
		}
	});

    myMooDatePicker.show(document.id('date'));

MooDatePicker Method: hide {#MooDatePicker:hide}
-------------------------------------------------------------------

Hide the currently displayed date picker.

### Syntax:

	myMooDatePicker.hide(element);

### Arguments:

1. element - (Element) An Element reference.

### Returns:

* (object) This MooDatePicker instance.

### Example:

#### HTML:

	<input id="date" name="date" type="text" data-moodatepicker />

#### JavaScript:

    var myMooDatePicker = new MooDatePicker(document.getElements('input[data-moodatepicker]'), {
		onPick: function(e, date){
			this.element.set('value', date.format('%e %B %Y'));
		}
	});

    myMooDatePicker.hide();

MooDatePicker Method: updateCalendar {#MooDatePicker:updateCalendar}
-------------------------------------------------------------------

Change the month to display in the calendar.

### Syntax:

	myMooDatePicker.updateCalendar(date);

### Arguments:

1. date - (Date) A Date instance.

### Returns:

* (object) This MooDatePicker instance.

### Example:

#### HTML:

	<input id="date" name="date" type="text" data-moodatepicker />

#### JavaScript:

    var myMooDatePicker = new MooDatePicker(document.getElements('input[data-moodatepicker]'), {
		onPick: function(e, date){
			this.element.set('value', date.format('%e %B %Y'));
		}
	});

    myMooDatePicker.show(document.id('date'));

    myMooDatePicker.updateCalendar(new Date(2011, 4, 12));

[options]:http://mootools.net/docs/core/Class/Class.Extras#Options
[events]:http://mootools.net/docs/core/Class/Class.Extras#Events