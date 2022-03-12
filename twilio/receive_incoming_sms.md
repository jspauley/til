# Receive An Incoming SMS From Twilio

Twilio expects a reponse when an SMS is sent via an HTTP POST request. Using Flask to create our API, 
you can receive an SMS, extract the sender phone number, the contents of the text, and return a `200`
status with the following:

```python
@api.post('/twilio/sms')
def twilio_sms():
    response = MessagingResponse()

    sender = request.form['From']
    message = request.form['Body']

    return Response(mimetype="text/xml"), 200
```

The `response` variable here isn't actually used in this example, but is kept in this example as it's 
commonly returned along with the `200` status and may be needed. 
