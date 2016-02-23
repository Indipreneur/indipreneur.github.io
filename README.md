Indipreneur Website
======

#The Official Website for Indipreneur, a subsidiary of CampusBiz

##Static Site Validation

I was faced with an interesting problem. Since JavaScript is only Client Side Handling, I couldn't really send an email, parse a form, or validate anything properly without `PHP` or `AJAX`. Since the client didn't have a server and everything was hosted on GitHub pages statically, I had to bypass this issue in an interesting manner.

Below is the inline JavaScript I used to check to see if the Terms and Conditions checkbox was checked.

```javascript
<script type="text/javascript">
function validate() {
	if (document.getElementById('squaredOne').checked){
		exit(0);
	}
	else {window.open('terms.html');
	alert("Please read the terms and conditions before submission.");
	}
  }
</script>
```

I ran the function through the checkbox and the submit button. On the event that the user didn't check the box (because I know no one actually reads the T&C), the program alerts the user, opens a new tab with the T&C, and still opens up the email.

```html
	<div class="modal fade" id="modal1" tabindex="-1" role="dialog" aria-labelledby="myModalLabel" aria-hidden="true">
		<div class="modal-dialog">
			<div class="modal-content modal-popup">
				<a href="#" class="close-link"><i class="icon_close_alt2"></i></a>
				<h3 class="white">Sign Up</h3>
				<form action="" class="popup-form">
					<div class="checkbox-holder text-center">
						<div class="checkbox text-center">
							<input type="checkbox" value="None" id="squaredOne" name="check" required="required" onclick="validate()" />
							<label for="squaredOne"><span>I Agree to the <strong><a href="terms">Terms &amp; Conditions</a></strong></span></label>
						</div>
					</div>
					<a href="mailto:example@gmail.com" class="btn btn-submit" onclick="validate()">Submit</a>
				</form>
			</div>
		</div>
	</div>
```

##Contribution
I'm sure there is a better way to implement this, but this is the most hacked up solution I could think of at 2 in the morning.

If you know of a better way, please fork this code, and submit a pull request.


Thanks for reading!

___
Written by Viren Mohindra &copy; 2016