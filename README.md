############################### SEEDSTARS DEVELOPER CASE STUDY ###############################
### PROBLEM: ###
Jenkins (http://jenkins-ci.org/) is an open source continuous integration server.

Create a script, in Python, that uses Jenkins' API to get a list of jobs and their status from a given Jenkins instance. The status for each job should be stored in a sqlite database along with the time for when it was checked.

### HOW TO RUN APP ###
Run: "python seedstars.py"


#################################################### REPORT ################################################

The "seedstars" script uses "SQLAlchemy", which is the Python SQL toolkit and Object Relational Mapper (ORM) that gives application developers the full power and flexibility of SQL.

It provides a full suite of well known enterprise-level persistence patterns, designed for efficient and high-performing database access, adapted into a simple and Pythonic domain language. (From official documentation)

I used the declarative_base (sqlalchemy.ext.declarative) to Construct a base class for declarative class definitions. The new base class will be given a metaclass that produces appropriate Table objects and makes the appropriate mapper() calls based on the information provided declaratively in the class and any subclasses of the class. (Official Docs)

The Jenkins app is downloaded and hosted locally on my PC (localhost:8080) using the username and password to connect to the Jenkins Application. 

My Jenkins Application consists of three (3) Jobs: seedstars_job_one, seedstars_job_two and seedstars_job_three from a Jenkins instance and returning:
id: Serial
jen_id: Job build id
name: Name of the Job
timeStamp: Time it was checked
result: Job Status 

seedstars_job_one is a job that executes periodically every minute from a build trigger, hence the multiple time stamps and SUCCESS status.

seedstars_job_three was built to be triggered remotely using URL JENKINS_URL/job/kjhkjj/build?token=TOKEN_NAME and an Authentication Token.

seedstars_job_two has same features with seedstars_job_one but was truncated to account for FAILURE status.


On line 16, the initializeDb function is called to initialize and create an SQLITE database using the create_engine() method. SQLite connects to file-based databases, using the Python built-in module sqlite3 by default.

As SQLite connects to local files, the URL format is slightly different. The “file” portion of the URL is the filename of the database. For a relative file path, this requires three slashes.

Thank You

### ISHAYA SUNDAY ### ### ishayasunday@gmail.com ### 
###  ###