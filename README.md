## api-lambda-cloudformation

* A simple cloudformation template to create an api endpint that echos the lambda event object
* This event object contains everything the api gateway passes to the lambda and is useful for further development



## To use
* Note: AWS-cli must be installed and configured
* Pull the repo and navigate inside
* Run this command
```
aws cloudformation create-stack --stack-name lambda-repeater-cf --capabilities CAPABILITY_IAM  --template-body file://api-lambda-cloudformation.json
```
* To view the status run:
```
watch -n 5 aws cloudformation describe-stacks --stack-name "lambda-repeater-test-cf"
```

* When you see the ```"StackStatus": "CREATE_COMPLETE"``` then you should also see an output that contains the URL
    *  ``` "OutputKey": "endpointUrl" ```
* You can navigate to this url and see the output of the event object passed from api gateway to lambda