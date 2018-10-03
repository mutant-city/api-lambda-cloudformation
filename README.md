## api-lambda-cloudformation

- A simple cloudformation template to create an api endpint that echos the lambda event object
- This event object contains everything the api gateway passes to the lambda and is useful for further development

- A current DEMO can be located here:

(https://6kh5hy0j6h.execute-api.us-west-1.amazonaws.com/v1/test)[https://6kh5hy0j6h.execute-api.us-west-1.amazonaws.com/v1/test]

## To use

- Note: AWS-cli must be installed and configured

1. Pull the repo and navigate inside
1. Run this command

```
aws cloudformation create-stack --stack-name lambda-repeater-cf --capabilities CAPABILITY_IAM  --template-body file://api-lambda-cloudformation.json
```

3. To view the status run:

```
watch -n 5 aws cloudformation describe-stacks --stack-name "lambda-repeater-test-cf"
```

4. When you see the `"StackStatus": "CREATE_COMPLETE"` then you should also see an output that contains the URL
   - `"OutputKey": "endpointUrl"`
5. You can navigate to this url and see the output of the event object passed from api gateway to lambda
