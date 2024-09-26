# Panther Training Club

## Introduction
The development team for Panther Training Club comprises:
- **Shusrita Venugopal** (Pitt ID: SHV73)
- **Bhavana Devulapally** (Pitt ID: BHD30)
- **Shri Harsha Vaidhyam** (Pitt ID: SAV127)

Panther Training Club is a comprehensive fitness web application built using **Node.js**, **Express.js**, **MongoDB**, **JavaScript**, and the **EJS** templating framework. It caters to gym enthusiasts by providing a platform to register, log in, and book trainers for health and training purposes. The application offers distinct user roles for gym members, trainers, and administrators.

## Objective
The primary objective of the project was to create a user-friendly and secure platform for gym enthusiasts to connect with trainers and access personalized fitness services. We aimed to implement features such as user authentication, profile management, booking functionalities, and admin privileges. Beyond the basic requirements, our goal was to ensure efficient data management, robust security measures, and a seamless user experience.

## Team Member Contributions
- **Bhavana Devulapally**: Led the front-end development, including user interface design and implementation. Also contributed to backend development and API integration.
- **Shusrita Venugopal**: Took charge of backend development, including server setup, database management, and API development. Implemented authentication and authorization features.
- **Harsha Vaidhyam**: Managed project planning, documentation, and testing. Contributed to both front-end and backend development tasks.

## Technical Architecture
The application follows the **MVC (Model-View-Controller)** architecture:
- **Models**: Define data structures and interact with MongoDB collections. Includes schemas for administrators, members, trainers, and bookings.
- **Views**: Render dynamic HTML pages using the EJS templating engine. Includes pages for user authentication, profile management, booking forms, and admin dashboard.
- **Controllers**: Handle user requests, process data, and invoke appropriate models. Responsible for implementing business logic and interacting with views to render responses.

## Functionality
- Gym members can register and log in to the web app.
- Both gym members and trainers have an exclusive profile page where they can view and update their details, except for email.
- Gym members can book a trainer by specifying their fitness goals, preferred workout, dietary restrictions, health issues, and additional comments.
- Bookings made by gym members are stored in the database.
- Trainers can view bookings on their homepage based on their specialization. For example, a Zumba instructor can see all bookings for Zumba sessions.
- Admin login functionality allows administrators to view all accounts of trainers and members and delete them if necessary.

## Implementation Details
- The project follows the **MVC (Model-View-Controller)** architecture using **Node.js**, **Express.js**, and EJS templating system.
- Log-in and sign-up functionalities are implemented using **JWT (JSON Web Tokens)** for authentication.
- Admin capabilities are included to perform advanced functions accessible only to specific admin users.
- Session management is implemented using JWT with an expiration feature.
- **RESTful Web service API** with CRUD operations is used, following proper structure and documented with Postman.
- The web app handles login and updating profile capabilities efficiently.
- Customized interfaces are provided for different user types, such as admin view, trainer view, and member view.
- Web forms for signup, login, profile page, and profile editing are implemented with form validation.

## Challenges
- Connecting to MongoDB.
- Ensuring proper error handling and validation for user inputs demanded attention to detail to maintain data integrity and security.
- Fine-tuning the frontend design for responsiveness across different devices and browsers was a continuous challenge throughout the development process.

## Future Work
- Interaction between trainers and members.
- Introduce a rating and feedback system to gather user reviews and improve service quality.
- Enhance data analytics capabilities to provide personalized recommendations based on user preferences and progress.

## Conclusion
The Panther Training Club project provided valuable insights into web development technologies and standards. By successfully implementing a feature-rich fitness application with robust security measures and a user-friendly interface, we achieved our objectives. The project enabled us to deepen our understanding of web technologies and prepare for future endeavors in software development.

## Resources and References
- [MongoDB documentation](https://docs.mongodb.com/)
- [JWT](https://jwt.io/)
- Project reference for JWT, EJS, and organizing file structure
- [Express API](https://expressjs.com/)
- [npm](https://www.npmjs.com/)
- [Express with MongoDB](https://www.freecodecamp.org/news/connect-mongodb-with-nodejs-express/)
- [JWT authentication](https://jwt.io/introduction/)
- Delete functions
- Method overriding
- RESTful API testing with Postman
- Web application references
- Web application reference images
- Express.js with MongoDB activity

## Testing Instructions
1. Register as a gym member or trainer using valid credentials.
2. Log in to access exclusive features such as profile management and booking.
3. Update profile details, including age and weight, from the profile page.
4. Book a trainer by specifying goals, preferred workout, dietary restrictions, and health issues.
5. Ensure proper functionality of admin capabilities, including account deletion and user management.

## API Documentation

### 1. Get All Members
- **Method**: GET
- **Endpoint**: `/api/admin/members`
- **Description**: Retrieves a list of all gym members.

**Output Format**:
```json
{
    "members": [
        {
            "_id": "66315e263b74fcb47fa107d6",
            "name": "Shusrita Venugopal",
            "email": "shv73@pitt.edu",
            "phoneNo": "4126264706",
            "age": 24,
            "gender": "female",
            "height": 154,
            "weight": 50
        },
        {
            "_id": "663168c7b3ecaa58c73ab38a",
            "name": "Bhavana Devulapally",
            "email": "bhd30@pitt.edu",
            "phoneNo": "4125435612",
            "age": 22,
            "gender": "female",
            "height": 182,
            "weight": 55
        }
    ]
}
```

### 2. Get All Trainers
- **Method**: GET
- **Endpoint**: `/api/admin/trainers`
- **Description**: Retrieves a list of all gym trainers.

**Output Format**:
```json
{
    "trainers": [
        {
            "_id": "663070601dd800a383bd1118",
            "name": "Bhavana Devulapally",
            "email": "bhd30@pitt.edu",
            "phoneNo": "4125468486",
            "age": 22,
            "gender": "female",
            "specializations": "Zumba"
        },
        {
            "_id": "66310ff6e0629b418d2c85c2",
            "name": "Shusrita Venugopal",
            "email": "shv73@gmail.com",
            "phoneNo": "4122223333",
            "age": 24,
            "gender": "female",
            "specializations": "Yoga"
        }
    ]
}
```

### 3. Delete Member
- **Method**: DELETE
- **Endpoint**: `/api/admin/members/{memberId}`
- **Description**: Deletes a gym member with the specified ID.

### 4. Get Member Details
- **Method**: GET
- **Endpoint**: `/api/member/{memberId}`
- **Description**: Retrieves details of a gym member with the specified ID.

**Output Format**:
```json
{
    "_id": "66315e263b74fcb47fa107d6",
    "name": "Shusrita Venugopal",
    "email": "shv73@pitt.edu",
    "phoneNo": "4126264706",
    "age": 24,
    "gender": "female",
    "height": 154,
    "weight": 50
}
```

### 5. Get Trainer Details
- **Method**: GET
- **Endpoint**: `/api/trainer/{trainerId}`
- **Description**: Retrieves details of a gym trainer with the specified ID.

**Output Format**:
```json
{
    "_id": "663070601dd800a383bd1118",
    "name": "Bhavana Devulapally",
    "email": "bhd30@pitt.edu",
    "phoneNo": "4125468486",
    "age": 22,
    "gender": "female",
    "specializations": "Zumba"
}
```

### 6. Get Bookings for Trainers
- **Method**: GET
- **Endpoint**: `/api/booktrainer/`
- **Description**: Retrieves all bookings for trainers.

**Output Format**:
```json
[
    {
        "_id": "66315e4c3b74fcb47fa107da",
        "memberId": "66315e263b74fcb47fa107d6",
        "goal": "Training",
        "preferredWorkout": "Yoga",
        "foodPreferences": "vegan",
        "medicalHistory": "",
        "additionalMessage": ""
    },
    {
        "_id": "6631690eb3ecaa58c73ab38d",
        "memberId": "663168c7b3ecaa58

c73ab38a",
        "goal": "Fitness",
        "preferredWorkout": "Weight Training",
        "foodPreferences": "vegetarian",
        "medicalHistory": "",
        "additionalMessage": "Need a trainer for weight loss."
    }
]
```

### 7. Book Trainer
- **Method**: POST
- **Endpoint**: `/api/booktrainer/`
- **Description**: Allows members to book trainers by providing their preferences.

**Input Format**:
```json
{
    "memberId": "66315e263b74fcb47fa107d6",
    "goal": "Training",
    "preferredWorkout": "Yoga",
    "foodPreferences": "vegan",
    "medicalHistory": "",
    "additionalMessage": ""
}
```

### 8. Update Member Profile
- **Method**: PUT
- **Endpoint**: `/api/member/update/{memberId}`
- **Description**: Updates member details.

**Input Format**:
```json
{
    "name": "Shusrita Venugopal",
    "phoneNo": "4126264706",
    "age": 25,
    "gender": "female",
    "height": 160,
    "weight": 52
}
```


