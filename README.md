# Unibuddy Engineering Exercise

This exercise is based on the deployed Unibuddy Chat service. The chat service is a core component in our product suite.

We've based our interview exercise on this code so you can get a feel of the code and products you'd been working on, and we can understand how you would adapt to working with our code base!

## Part 3 - Strech - Answers Below

We'd love to hear about

- How you would go about implementing the solution

  - Assuming adding tag to an existing message (code updated for this functionality)

    1. Create new handler to handle the add tag request (POST request).
    2. This will call a business logic function that will check if user is authorised to add a tag.
    3. Call a db function to add tag to the given message id.

  - Filtering messages - Follow a similar approach
    1. Create new handler to handle the filter by tags request (GET request)
    2. This will call a business logic function that will check if user is authorised to add a tag.
    3. Call a db function that should return an array of message that include the given tag as a property.
       <br>

- What problems you might encounter
  1.  User may add tag that has already been added to message (currently possible to do so)
  2.  User may filter by a tag that doesnt exist
      <br>
- How you would go about testing
  - Create a couple of tests to check if message is updated with correct tag and can successfully return filtered messages 1. For adding tag: Create mock message. Run function to add a tag to message. Expect tag to be included in message.tags array 2. For filtering: Create multiple mock messages. Add tags to each message. Run function to return an array of messages with given tag. Expect returned array to be of certain length.
    <br>
- What you might do differently
  1.  Do not allow user to add a tag that has already been added to message.
  2.  We could updated the messages tags real-time by sending the updates through a websocket connection.
  3.  Only allow certain tags. Give user available options. Update tag types accordingly. eg:
      ```javascript
      tag: 'Math' | 'Science' | 'Chemistry';
      ```
