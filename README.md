# Tour Companion

JavaFX desktop app for booking tour guides, managing bookings, and leaving ratings after a trip. This is a 2-2 semester project.

Users can sign up, log in, browse guides with ratings and reviews, book a guide, cancel a booking, update their profile, and contact support.

## Features

- Sign up and login (with optional profile photo)
- User dashboard with session-based navigation
- Book a guide and view ratings/reviews
- Booking history
- Cancel a booking
- Rate and review after a completed service
- Profile and settings
- Contact admin/support

## Tech stack

- Java 21
- JavaFX 21 (Controls + FXML)
- Maven
- Scene Builder / FXML layouts
- MySQL (JDBC connector 8.0.33)
- FontAwesomeFX
- Thumbnailator (image handling)

## Requirements

- JDK 21 or later
- Maven 3.x (or the included `mvnw` / `mvnw.cmd` wrappers)
- A reachable MySQL instance matching the app's expected schema

## Project layout

Maven sources live in the inner `Tour_Companion/` folder.

```text
Tour_Companion/
|
|-- README.md
|
`-- Tour_Companion/                      Maven module
    |-- pom.xml
    |-- mvnw / mvnw.cmd
    |
    `-- src/main/
        |
        |-- java/
        |   |-- module-info.java
        |   `-- com/example/tour/
        |       |
        |       |-- HelloApplication.java    app entry (login)
        |       |-- RunMain.java
        |       |-- DatabaseConnector.java   MySQL
        |       |-- SessionManager.java
        |       |-- SceneManager.java
        |       |
        |       |-- LoginController.java
        |       |-- UserDashboardController.java
        |       |-- bookingController.java
        |       |-- BookingHistoryController.java
        |       |-- ProfileController.java
        |       |-- SettingsController.java
        |       |-- ContactController.java
        |       |
        |       |-- Guide.java
        |       `-- BookingDetails.java
        |
        `-- resources/com/example/tour/
            |-- login.fxml
            |-- signup.fxml
            |-- UserDashboard.fxml
            |-- booking.fxml
            |-- bookingHistory.fxml
            |-- profile.fxml
            |-- settings.fxml
            `-- contact.fxml
```

## Setup

1. Clone the repository and open it in your IDE.
2. Set the project SDK to **Java 21**.
3. Install dependencies and run from the Maven module directory:

```bash
cd Tour_Companion
mvn clean javafx:run
```

On Windows you can use the wrapper instead of a global Maven install:

```bash
cd Tour_Companion
.\mvnw.cmd clean javafx:run
```

The main class is `com.example.tour.HelloApplication`. The window opens on `login.fxml` at 1024x650 and is not resizable.

## Database

JDBC settings are hardcoded in `Tour_Companion/src/main/java/com/example/tour/DatabaseConnector.java` (`JDBC_URL`, `USERNAME`, `PASSWORD`).

Point those values at your own MySQL server before running. The app expects tables such as user records, `guideInfo`, and `bookingInfo` (bookings, ratings, and reviews).

Do not commit real production credentials.

## Notes

Intended for academic/demo use. Adjust JavaFX, Maven, and database settings for your local machine if the default run configuration does not match your environment.
