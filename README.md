BFHL Data Processing API
This is a simple REST API built with Node.js and Express that processes an array of data and returns classified lists of numbers, alphabets, and special characters, along with a sum and a custom concatenated string.

Features
Classifies input data into even numbers, odd numbers, alphabets, and special characters.

Calculates the sum of all numbers in the input.

Returns a reversed, alternating-case string of all alphabets.

Simple and lightweight with no external dependencies besides Express.

Installation
Clone the repository:

git clone <your-repository-url>

Navigate to the project directory:

cd <your-project-directory>

Install the dependencies:

npm install

Running the Server
To start the local development server, run the following command:

node index.js

The server will start on http://localhost:3000 by default, or on the port specified in your PORT environment variable.

API Endpoint
POST /bfhl
This is the main endpoint for processing data.

Request Body:

The request must be a JSON object with a data key containing an array of strings.

{
    "data": ["a", "1", "334", "4", "R", "$"]
}

Success Response (200 OK):

If the request is successful, the API will return a JSON object with the processed data.

{
    "is_success": true,
    "user_id": "john_doe_17091999",
    "email": "john@xyz.com",
    "roll_number": "ABCD123",
    "odd_numbers": ["1"],
    "even_numbers": ["334", "4"],
    "alphabets": ["A", "R"],
    "special_characters": ["$"],
    "sum": "339",
    "concat_string": "Ra"
}

Error Response (400 Bad Request):

If the data field is missing or is not an array, the API will return an error.

{
    "is_success": false,
}
    "error": "Invalid input: 'data' must be an array."
}
