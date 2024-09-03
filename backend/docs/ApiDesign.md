# MuscleMap — API Design

### Base URL
- **Base URL**: `/api/v1`

### 1. **User API**
- **Endpoint**: `/users`
- **Description**: Manage user accounts.

| Method | Endpoint         | Description              | Request Body |
|--------|------------------|--------------------------|--------------|
| GET    | `/users`          | Get all users            | N/A          |
| GET    | `/users/{id}`     | Get user by ID           | N/A          |
| POST   | `/users`          | Create a new user        | JSON (User)  |
| PUT    | `/users/{id}`     | Update a user            | JSON (User)  |
| DELETE | `/users/{id}`     | Delete a user            | N/A          |

### 2. **Muscle Group API**
- **Endpoint**: `/muscle-groups`
- **Description**: Manage muscle groups and related sub-groups.

| Method | Endpoint                                | Description                         | Request Body        |
|--------|-----------------------------------------|-------------------------------------|---------------------|
| GET    | `/muscle-groups`                        | Get all muscle groups               | N/A                 |
| GET    | `/muscle-groups/{id}`                   | Get muscle group by ID              | N/A                 |
| POST   | `/muscle-groups`                        | Create a new muscle group           | JSON (Muscle Group) |
| PUT    | `/muscle-groups/{id}`                   | Update a muscle group               | JSON (Muscle Group) |
| DELETE | `/muscle-groups/{id}`                   | Delete a muscle group               | N/A                 |
| POST   | `/muscle-groups/{id}/sub-groups`        | Add a sub-group to a muscle group   | JSON (Sub-Group)    |
| GET    | `/muscle-groups/{id}/sub-groups`        | Get all sub-groups for a muscle group | N/A              |

### 3. **Exercise API**
- **Endpoint**: `/exercises`
- **Description**: Manage exercises, linked to muscle sub-groups, difficulty levels, and machines.

| Method | Endpoint                    | Description                     | Request Body      |
|--------|-----------------------------|---------------------------------|-------------------|
| GET    | `/exercises`                | Get all exercises               | N/A               |
| GET    | `/exercises/{id}`           | Get exercise by ID              | N/A               |
| POST   | `/exercises`                | Create a new exercise           | JSON (Exercise)   |
| PUT    | `/exercises/{id}`           | Update an exercise              | JSON (Exercise)   |
| DELETE | `/exercises/{id}`           | Delete an exercise              | N/A               |

### 4. **Difficulty Level API**
- **Endpoint**: `/difficulty-levels`
- **Description**: Manage difficulty levels for exercises.

| Method | Endpoint                       | Description                         | Request Body          |
|--------|--------------------------------|-------------------------------------|-----------------------|
| GET    | `/difficulty-levels`           | Get all difficulty levels           | N/A                   |
| GET    | `/difficulty-levels/{id}`      | Get difficulty level by ID          | N/A                   |
| POST   | `/difficulty-levels`           | Create a new difficulty level       | JSON (DifficultyLevel) |
| PUT    | `/difficulty-levels/{id}`      | Update a difficulty level           | JSON (DifficultyLevel) |
| DELETE | `/difficulty-levels/{id}`      | Delete a difficulty level           | N/A                   |

### 5. **Machine API**
- **Endpoint**: `/machines`
- **Description**: Manage machines used for exercises.

| Method | Endpoint              | Description               | Request Body    |
|--------|-----------------------|---------------------------|-----------------|
| GET    | `/machines`           | Get all machines           | N/A             |
| GET    | `/machines/{id}`      | Get machine by ID          | N/A             |
| POST   | `/machines`           | Create a new machine       | JSON (Machine)  |
| PUT    | `/machines/{id}`      | Update a machine           | JSON (Machine)  |
| DELETE | `/machines/{id}`      | Delete a machine           | N/A             |

### 6. **Workout Plan API**
- **Endpoint**: `/workout-plans`
- **Description**: Manage workout plans, which consist of exercises.

| Method | Endpoint                             | Description                         | Request Body          |
|--------|--------------------------------------|-------------------------------------|-----------------------|
| GET    | `/workout-plans`                     | Get all workout plans               | N/A                   |
| GET    | `/workout-plans/{id}`                | Get workout plan by ID              | N/A                   |
| POST   | `/workout-plans`                     | Create a new workout plan           | JSON (WorkoutPlan)    |
| PUT    | `/workout-plans/{id}`                | Update a workout plan               | JSON (WorkoutPlan)    |
| DELETE | `/workout-plans/{id}`                | Delete a workout plan               | N/A                   |
| POST   | `/workout-plans/{id}/exercises`      | Add exercises to workout plan       | JSON (Exercise IDs)   |
| GET    | `/workout-plans/{id}/exercises`      | Get exercises in a workout plan     | N/A                   |

### Example JSON Structures:

1. **User**
   ```json
   {
     "username": "JohnDoe",
     "email": "john@example.com",
     "password": "hashed_password"
   }
   ```

2. **Muscle Group**
   ```json
   {
     "muscleGroupName": "Chest",
     "subGroups": [
       {
         "subGroupName": "Upper Chest"
       },
       {
         "subGroupName": "Lower Chest"
       }
     ]
   }
   ```

3. **Exercise**
   ```json
   {
     "exerciseName": "Bench Press",
     "description": "Classic chest exercise",
     "muscleSubGroupId": "6123abc456def789",
     "difficultyLevelId": "7123abc456def789",
     "machineId": "8123abc456def789"
   }
   ```

4. **Machine**
   ```json
   {
     "machineName": "Barbell",
     "description": "Weightlifting bar used for various exercises"
   }
   ```

5. **Workout Plan**
   ```json
   {
     "planName": "Full Body Workout",
     "userId": "9123abc456def789",
     "exercises": [
       {
         "exerciseId": "6123abc456def789"
       },
       {
         "exerciseId": "7123abc456def789"
       }
     ]
   }
   ```

### Pagination & Filtering:
- Implement pagination for endpoints returning lists (e.g., `/exercises`, `/workout-plans`) using query parameters like `page`, `size`, and `sort`.
- Add filtering options for searching exercises by muscle group, difficulty, etc.
