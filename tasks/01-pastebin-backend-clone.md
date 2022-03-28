# Pastebin Clone - Backend Only

Your task is to create the backend for a basic [Pastebin](https://pastebin.com) clone. Anonymous users (i.e. no authentiction needed) should be able to save arbitrary text, and then get back from the backend a URL which can be used to reference that text in the future.

The purpose of this task is to as closely as possible resemble the work that you would do in a production app. Please do not take any shortcuts, and use the tools/libraries you would use in a full-fledged production app.

This task is designed to take a couple of hours, but you may use up to 24 hours. When you are complete, please send the entirety

## Tech

You must use the following technology:

- TypeScript/Node.js
- SQL database (PostgreSQL)

If you have the experience, you may use GraphQL. Otherwise, a REST backend is also fine.

## Actions

The backend must be able to respond to the following actions (GraphQL _or_ REST):

### 1. Save text

Receive arbitrary text from the user, and save it to the DB. Also initialize the number of upvotes this text has to 0. Generate an ID for the text, by hashing the text with MD5. Return the ID.

Also, generate a "private" key, and return the key. Users of the API will be able to use this key in the future to demonstrate they created the text.

### 2. Get text

Receive the ID of some text, fetch it from the DB, and return it, along with the number of upvotes the text has.

### 3. Upvote text

Increase the number of upvotes of a text (referenced by ID) by 1

### 4. Downvote text

Same as upvoting, but _decrease_ upvotes by 1.

### 5. Delete text

Delete the text corresponding to the given ID. The request **must** include the key that was returned to the creating user in step 1. If the key is missing, or is not the correct key, return an error to the user.
