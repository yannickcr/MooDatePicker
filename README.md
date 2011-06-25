MooDatePicker
====

MooDatePicker is a simple date picker for MooTools.

How to use
----------

To use MooDatePicker, you need one or more elements to use as a datepicker, like a form input.
Just call the constructor with the element(s) as first parameter and the options object as second parameter.

### Example

HTML:

	<input name="date" type="text" data-moodatepicker />

JavaScript:

	new MooDatePicker(document.getElements('input[data-moodatepicker]'), {
		onPick: function(e, date){
			this.element.set('value', date.format('%e %B %Y'));
		}
	});