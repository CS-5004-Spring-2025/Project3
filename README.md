# Project 3 - Fitness Tracker

### Due - Thursday, March 13, 2025

Assignment Link: [https://classroom.github.com/a/i5FMuAAJ](https://classroom.github.com/a/i5FMuAAJ)

This project requires you to **design** and **implement** a Fitness Tracker application. A large portion of your grade will depend on the design you choose for the program. Use of `static` fields or methods should be well justified!

**Description** Your fitness tracker will keep track of the workout history, nutrition history, and a profile for the user. The profile will track an exercise goal (minutes of exercise) and a nutrition goal (maximum calories). The workout history will track a list of workouts where each includes a date (month, day, and year), a workout type (e.g., Running), and a duration in minutes. A user may have multiple workouts on the same day. The nutrition history will keep a log of foods consumed including the date (month, day, and year), the list of foods, and their total calorie count. A user may have multiple records on the same day where each includes multiple foods. The calorie value will be the total calories of all foods in that record.

## Functionality Requirements

### Menu Operations: 
The application must use a menu to allow the user to select from one of the following operations:

1. **Log a workout** The workout must include the date (day, month, and year) of the workout, the workout type, and the duration. This operation will add a new workout to the workout history.
2. **Log a food item** The food item must include the date (day, month, and year) of consumption, the name of the food item, and the number of calories of the food item. This operation will add the new food either to an existing record or as a new record. When adding to an existing record, make sure to update the total calories consumed appropriately.
3. **View nutrition for a day** Given a day, month, and year, display the list of foods and total calories consumed on that day.
4. **View workouts for a day** Given a day, month, and year, display all the workouts and their durations for that day *sorted by duration*.
5. **View days fitness goal completed by month** Given a month and year, display all days that the user's dailyExerciseGoal was completed. 
6. **View days calorie goal met by month** Given a month and year, display all days that the user's calorie consumption was below their dailyCalorieGoal. *Note, this assumes that a user wishes to stay under their calorie goal; however, a valid alternative would be to set of goal of consuming more calories than the goal if the user wanted to gain weight rather than lose weight.*
7. **View monthly exercise summary** Given a month and year, view the total exercise minutes each day *sorted by day*.

### JSON Format
When the application loads, it will load data from the files *resources/profile.json*; *resources/fitness.json*; and *resources/nutrition.json*. The Log operations above will add new data to your data structure. The View operations will allow the user to query all data. 

The format of the *resources* files will be as follows:

User Profile data stored in *resources/profile.json*
```json
{
  "id": "12345",
  "dailyExerciseGoal": 30,
  "dailyCalorieGoal": 1700
}
```

Workout History data stored in *resources/fitness.json*
```json
{
  "workoutHistory": [
    {
      "date": "2024-01-29",
      "workoutType": "Running",
      "durationMinutes": 29
    },
    {
      "date": "2024-01-28",
      "workoutType": "Strength Training",
      "durationMinutes": 45
    },
    {
      "date": "2024-02-08",
      "workoutType": "Strength Training",
      "durationMinutes": 45
    }

  ]
}
```

Nutrition History stored in *resources/nutrition.json*
```json
{
  "nutritionHistory": [
    {
      "date": "2024-01-29",
      "foodsConsumed": [
        "Oatmeal", "Banana", "Ham Sandwich", "Apple", "Kind Bar"
      ],
      "totalCalories": 1523
    },
    {
      "date": "2024-01-29",
      "foodsConsumed": [
        "Fish and Chips", "Ice Cream"
      ],
      "totalCalories": 932
    },
    {
      "date": "2024-01-30",
      "foodsConsumed": [
        "Oatmeal", "Banana", "Hummus Crunch Salad", "Chocolate Chip Cookie", "Cauliflower Soup"
      ],
      "totalCalories": 1567
    }
  ]
}
```

## Execution Requirements

1. Your `main` method must be in a class called `FitnessTracker` in a package called `tracker`. We will run your solution as `java tracker.FitnessTracker`. You may assume that the data to be loaded on startup is in the *resources* directory in files named `profile.json`, `nutrition.json` and `fitness.json`.
2. `build.gradle.kts` has been updated to include the [Jackson](https://github.com/FasterXML/jackson) JSON parsing library as a dependency. You are responsible for updating `build.gradle.kts` if your solution depends on any other third-party libraries.

## Design Requirements

Your final design must use all of the following elements:

1. You must use inheritance in at least two places.
2. You must use at least one of the following: enum, switch statement, or record.
3. You must use the `Comparable` interface or a `Comparator` at least once.
4. You must use method overriding at least once.

## Testing Requirements

1. Your GitHub commit history must demonstrate that you have used test driven design.
2. Testing must be complete.

## Reflection

You are required to complete a thoughtful and thorough reflection on your solution, your experience implementing it, and what you learned. You will complete the questions outlined in [REFLECTION.md](REFLECTION.md).

## Grading Rubric

The assignment is worth 25 points in total. For criteria worth two points,
partial credit may be awarded. For criteria worth one point, the solution must
be completely correct to earn credit.

| Criterion                                 | Points | 
|-------------------------------------------|--------|
| Execution requirements met                | 1      |
| Data from resources/ is loaded correctly  | 1      |
| Log a workout                             | 1      | 
| Log a food item                           | 1      | 
| View nutrition for a day                  | 1      |
| View workouts for a day                   | 1      |
| View days fitness goal completed by month | 1      |
| View days calorie goal met by month       | 1      |
| View monthly exercise summary             | 1      |
| Error handling                            | 2      |
| Inheritance used in two places            | 1      |
| enum, switch, or record used              | 1      |
| Comparable or Comparator used             | 1      |
| Overriding used                           | 1      |
| Overall program design                    | 4      | 
| Uses TDD                                  | 2      |
| Testing is complete                       | 1      |
| Style check passes                        | 1      |
| Javadoc                                   | 1      | 
| Reflection                                | 1      | 
