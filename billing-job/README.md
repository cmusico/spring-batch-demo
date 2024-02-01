### Package the application

`./mvnw clean package -Dmaven.test.skip=true`

### Launch the job and pass the input file as a parameter with the following command

`java -jar target/billing-job-0.0.1-SNAPSHOT.jar input.file=input/billing-2023-01.csv output.file=staging/billing-report-2023-01.csv data.year=2023 data.month=1`

### Run the tests

In the terminal, run the following command:

`./mvnw clean test -Dspring.batch.job.enabled=false`

The property -Dspring.batch.job.enabled=false disables the automatic execution of the job by Spring Boot. Without this property, the job will be executed twice: a first time at the application's startup, and a second time during the test. This is obviously not desired when running tests, hence the use of that property.