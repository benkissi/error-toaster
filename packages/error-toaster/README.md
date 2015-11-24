##Description
Error-Toaster presents a nice way to display error prompts to users.
It shows user caused errors such as omissions.

##Installation
meteor add benkissi:error-toaster

##Usage
The package provides a function throw(), which catches errors and
displays them. Here is an example:

```
meteor
    Meteor.call('accountsInsert', account, function(error, result) {
		// display the error to the user and abort
		if (error)
			return Error.throw(error.reason);

		if (result.accountExists)
			Error.throw('This account number has already been created');

		Router.go('accountPage', {_id: result._id});
	});

```

