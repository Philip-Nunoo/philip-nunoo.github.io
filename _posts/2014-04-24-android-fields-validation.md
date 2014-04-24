---
layout: post
title: Android Fields Validations
---
I've heard people talk about "Ok now let's make sure our fields are validated properly with no empty portions" - So we just have to go into our Activity and 
just check non of the fields are empty and so on and so fort.

That's good but have you ever wondered if there are libraries that could do that for you? Yes there are.
</p>
Here's the scenario. You've just spent the last couple hours busting out an awesome form for your new badass Android application. You've thought of everything. All the inputTypes and imeOptions are set. You even managed to set sensible hints and prompts for all your fields. But WAIT! What about validation?

So this tutorial talks about some of the android validation libraries out there
which you could add to your project to do those validation and save you lots of code which could have been writing by you.

Here are a few which I came across online:

* [Android Saripaar][saripaarUrl] from ragunathjawahar
* [Android Validator][validatorUrl] from throrin19
* [Android Validation library][androidValidationUrl] from tylerchesley

# Using Android Validator
I found android validator to be much simple and understanding among the list and so I'd talk about how to use [Android validor][validatorUrl].

First you would have to [download][androidValidorDownload] the validator from the github repository and import it into your android project. And add as a library to your project. 

## Form Class
This class manages the processing of each Validate, Validator and displays the error on the EditText automatically. The Form class stores a Validate stack and then you just have to run the validation with the validate() function. To instanciate Form and add Validates, you have to do this

{% highlight java %}
Form mForm = new Form();
{% endhighlight %}

## Validate Class
The pure Validate class is a FIFO validator. It's test a list of AbstractValidator for specific EditText. For some special cases, Validate is not enough. This is why there are specific validates. This is why there are two individuals with a Validate operation different from that base :

* ConfirmValidate : Can check whether a value is identical between the two fields. Can be used to confirm the entry of a password.

* OrTwoRequiredValidate : If one of the two target fields has a value, then it is valid. Can be used if a user must give his phone or fax.

* Validate : The base Validate. It creates his validators stack.

{% highlight java %}
Validate emailField = new Validate(emailEditTextField);
{% endhighlight %}

Then you add the Validator to it
{% highlight java %}
emailField.addValidator(new NotEmptyValidator(mContext));
emailField.addValidator(new EmailValidator(mContext));
{% endhighlight %}

## Validator Class
This class define the rules for your validation to take place.
The validator currently contains these basic validation rules:

* EmailValidator : Ensures that the field does contain an email address. You can also define a regex to check for a particular domain name with the function setDomainName(DomainRegexp). Example for gmail.com domain : setDomainName("gmail\\.com").

<table>
<tr>
<td>NotEmptyValidator</td>
<td>Ensures that the field is not empty.</td>
</tr>
<tr>
<td>UrlValidator</td>
<td>Ensures that the field is a valid url.</td>
</tr>
<tr>
<td>AlnumValidator</td>
<td>Ensure that the feld has Alnum characters.</td>
</tr>
<tr>
<td>HexValidator</td>
<td>Ensure that the field has Hex characters.</td>
</tr>
<tr>
<td>RegExpPattern</td>
<td>Ensure that the field does match setted Pattern.</td>
</tr>
<tr>
<td>PhoneValidator</td>
<td>Ensure that the field is a valid phone number.</td>
</tr>
<tr>
<td>Custom Validator</td>
<td>You can create your own Validator. To do this, you can just create class extends AbstractValidator.</td>
</tr>
</table>
{% highlight java %}
public class CustomValidator extends AbstractValidator
{
    private int mErrorMessage = R.string.validator_custom; // Your custom error message

    public CustomValidator(Context c) {
        super(c);
    }

    @Override
    public boolean isValid(Object value) {
        // Your validation Test is here.
        // Return true if it's correct, false if it's incorrect
        return true;
    }

    @Override
    public String getMessage() {
        return mContext.getString(mErrorMessage);
    }
}
{% endhighlight %}

## back to form class
Back to our form object we can now add the fields we would want to validate as shown here:

{% highlight java %}
mForm.addValidates(emailField);
mForm.addValidates(confirmFields);
mForm.addValidates(urlField);
{% endhighlight %}

Then you'd perform your validation check by:

{% highlight java %}
// Launch Validation
if(mForm.validate()){
    // success statement
}else{
    // error statement like toast, crouton, ...
}
{% endhighlight %}

Called to validate our form. If an error is found, it will be displayed in the corresponding field.

complete scenario:
{% highlight java %}
public void saveEvent(View view){
	Toast.makeText(context, "Save Data", Toast.LENGTH_LONG).show();
	EditText eventNameEditText = (EditText) findViewById(R.id.eventNameEditText);
	EditText placeEditText = (EditText) findViewById(R.id.placeEditText);
	EditText locationEditText = (EditText) findViewById(R.id.locationEditText);
	EditText descriptionEditText = (EditText) findViewById(R.id.descriptionEditText);
	EditText dateEditText = (EditText) findViewById(R.id.dateEditText);
	EditText timeEditText = (EditText) findViewById(R.id.timeEditText);
	
	// Check for name Field
	Validate nameValidate = new Validate(eventNameEditText);
	nameValidate.addValidator(new NotEmptyValidator(context));
	
	// Check for place field
	Validate placeValidate = new Validate(placeEditText);
	placeValidate.addValidator(new NotEmptyValidator(context));
	
	// Check for location field
	Validate locationValidate = new Validate(locationEditText);
	locationValidate.addValidator(new NotEmptyValidator(context));
	
	// Check for Description field
	Validate descriptionValidate = new Validate(descriptionEditText);
	descriptionValidate.addValidator(new NotEmptyValidator(context));
	
	// Check for time field
	Validate timeValidate = new Validate(timeEditText);
	timeValidate.addValidator(new NotEmptyValidator(context));
	
	// Check for date field
	Validate dateValidate = new Validate(dateEditText);
	dateValidate.addValidator(new NotEmptyValidator(context));
	
	Form mForm = new Form();
	mForm.addValidates(dateValidate);
	mForm.addValidates(timeValidate);
	mForm.addValidates(descriptionValidate);
	mForm.addValidates(locationValidate);
	mForm.addValidates(placeValidate);
	mForm.addValidates(nameValidate);
	
	if (mForm.validate()) {

		String eventName = eventNameEditText.getText().toString();
		String place = (placeEditText).getText().toString();
		String location = (locationEditText).getText().toString();
		String description = (descriptionEditText).getText().toString();
		String date = (dateEditText).getText().toString();
		String time = (timeEditText).getText().toString();
		
	} else {
		Toast.makeText(context, "Ensure you've entered correct inputs.", Toast.LENGTH_SHORT).show();
		return;
	}
}

{% endhighlight %}
[saripaarUrl]:           http://github.com/ragunathjawahar/android-saripaar
[validatorUrl]:          http://github.com/throrin19/Android-Validator
[androidValidationUrl]:  http://github.com/tylerchesley/android-validation
