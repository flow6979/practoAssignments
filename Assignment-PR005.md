### Questions:

1. Create an application and integrate sentry with it. Push error messages to the sentry
	
### Steps - 
* Create sentry account
* Install sentry sdk and import it.
			
	pip install sentry-sdk

* Configure sentry using dsn string.
			
	# settings.py

	import sentry_sdk

	sentry_sdk.init(
		
	    dsn="https://00d278f2aaf1ad3d51d13be34ca48e60@o4507496686878720.ingest.us.sentry.io/4507496689303552",
		
	    # Set traces_sample_rate to 1.0 to capture 100%
		
	    # of transactions for performance monitoring.
		
	    traces_sample_rate=1.0,
		
	    # Set profiles_sample_rate to 1.0 to profile 100%
		
	    # of sampled transactions.
		
	    # We recommend adjusting this value in production.
		
	    profiles_sample_rate=1.0,
		
	)



* Send error or exception message to sentry ( with try and exception blocks in python.
	Try:
	
	    raise ValueError("This is a demo error.")

	except Exception as e:

	    sentry_sdk.capture_exception(e)
		
* Verification
	# urls.py

	from django.urls import path
	</br>

	def trigger_error(request):

	    division_by_zero = 1 / 0
	
	urlpatterns = [

	    path('sentry-debug/', trigger_error),

	    # ...

	]




2. Mention commands for updating a staging with a particular branch for a service

	practl update st <stage_name> -p <branch_name>

3. Command for starting a staging

	practl start staging <staging_name>


4. Create a staging with the services: Accounts, nav, Communicator, Ray-app, Ray-api, QMS, Store
The deployment of one product will fail, explain why the deployment has failed

	NOT ACCESSIBLE