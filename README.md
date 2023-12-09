# Admin.html
# Hospital Triage Administration Webpage

## Overview
This HTML document structures a web-based interface for hospital triage administration. It is designed to manage and display patient data in a hospital setting, focusing on triage and priority handling.

## Features

### Patient Data Table
- **Structure**: The core of the page is a table that lists patient details.
- **Columns**: Includes columns for patient name, injury type, pain level, additional information, and necessary attention level.
- **Interaction**: Each row has a 'Select' button, presumably for further actions on individual patient records.

### Data Management
- **Load Data Button**: A button (`id="loadData"`) is provided to presumably load patient data into the table.
- **File Input**: An input field (`id="fileInput"`) allows for uploading data, possibly for batch processing or data import.

### Action Section
- **Buttons for Priority Management**: Includes buttons for removing a patient from the list or adjusting their priority level (increase or decrease).

### External Resources
- **CSS Styles**: The page is styled with an external CSS file (`stylesAdmin.css`), which is not included in this document.
- **JavaScript Interactions**: Functionalities like data loading, patient record management, and interaction handling are likely managed by an external JavaScript file (`scripts.js`).

## Usage
This webpage serves as an administrative interface for hospital staff to manage patient triage efficiently. The interactive table format allows for easy viewing and updating of patient statuses and priorities.

**Note**: The actual functionality for data manipulation, event handling, and dynamic interaction requires the associated CSS and JavaScript files, which are referenced but not included in this HTML structure.
                                                              # User.html
# Hospital Triage App

## Overview
The Hospital Triage App is an HTML-based web application designed to facilitate the triage process in a hospital setting. It allows users to enter information about a patient's injury, pain level, and additional relevant details.

## Features

### User Name Entry
- **Section**: A dedicated section for entering the user's name.
- **Form**: Includes a form (`id="infoForm"`) with an input field for the user's name.

### Injury Type Selection
- **Headings**: Clear headings guide the user through the process.
- **Interactive Buttons**: Buttons for selecting the type of injury (Head, Heart, Lung, Neck, Hand or Leg, Any Type of Bones, Stomach, Burn or Cut).
- **Event Handling**: Each button has an `onclick` event linked to the `selectInjury` function, presumably defined in the external `scripts.js` file.

### Pain Level Selection
- **Pain Scale**: A dropdown (`id="painLevel"`) allows users to select a pain level from 0 to 10.

### Additional Information
- **Information Form**: Another form for additional patient information with a text input field.

### Submission
- **Submit Button**: A button to submit the form data, triggering the `submitForm` function on click.

### External Resources
- **Styling**: The page is styled with an external CSS file (`styles.css`).
- **JavaScript**: Functionalities and form handling are managed by an external JavaScript file (`scripts.js`).

## Usage
This web application is intended for hospital staff or patients to quickly and efficiently input triage information. The structured format with clear sections for different types of information ensures ease of use and facilitates the triage process.

**Note**: The actual functionality for data processing and event handling is managed by the linked JavaScript file, which is not included in this HTML structure.

                                                                              # admin.js
# Hospital Triage App - JavaScript Functionality

## Overview
The `scripts.js` file contains the JavaScript code that adds interactivity and data handling to the Hospital Triage App. It is responsible for loading user data, handling form submissions, and managing the triage table.

## Key Functionalities

### DOM Content Loaded Event Listener
- **Initialization**: Sets up event listeners and initializes variables once the DOM content is fully loaded.

### Global Variables
- **User Data**: Stores user data as an array, which can be populated from a file or other sources.

### Load User Data Function
- **Table Update**: Clears and populates the table with user data.
- **Row Creation**: Dynamically creates table rows and cells based on the user data.
- **Button Creation**: Adds a 'Select' button to each row with an event listener for selection actions.

### Handle Select Function
- **Selection Logging**: Logs information about the selected user (currently a placeholder for further implementation).

### File Input Change Event Listener
- **File Reading**: Reads a user data file and populates the `userData` array.
- **Data Parsing**: Splits file content into key-value pairs and stores them in `userData`.

### Load Data Button Event Listener
- **Data Loading**: Calls the `loadUserData` function to update the table with the loaded data.

### Remove, Increase, and Decrease Priority Buttons
- **Event Listeners**: Placeholder event listeners for future implementation of removing a user and adjusting their priority in the triage list.

## Usage
This script is designed to enhance the Hospital Triage App by providing dynamic data handling and user interaction capabilities. It facilitates the triage process by allowing efficient loading, viewing, and managing of patient data.

**Note**: The functionalities for removing and adjusting priority levels are placeholders and require further implementation to be fully functional.

                                                                              # user.js
# Hospital Triage App - User Interaction Script

## Overview
This script (`scripts.js`) is part of the Hospital Triage App, handling user input and form submission. It captures user-selected injury type, pain level, additional information, and user name, and then compiles this data into a downloadable text file.

## Key Functionalities

### Global Variables
- **Selected Information**: Variables (`selectedInjury`, `selectedPainLevel`, `additionalInfo`, `userName`) store the user's selections and inputs.

### Select Injury Function
- **Purpose**: Captures the type of injury selected by the user.
- **Parameter**: `injuryType` (String) - the type of injury selected.
- **Implementation**: Assigns the selected injury type to `selectedInjury`.

### Submit Form Function
- **Data Collection**: Retrieves user input from the DOM elements (`painLevel`, `info`, `name`).
- **Validation**: Checks if all required fields are fil# Hospital Triage System (HTS) - MySQL Database Structure

## Overview
The provided MySQL dump outlines the database structure for the Hospital Triage System. It includes definitions for tables `emergency_severity` and `users`, essential for managing triage operations.

## Database Structure

### Table: `emergency_severity`
- **Purpose**: Stores the severity levels of emergencies.
- **Fields**:
  - `severity_index`: Tinyint (unsigned) - A unique identifier for the severity level.
  - `severity_desc`: Text - Describes the emergency severity.
  - `default_wait_time`: Smallint (unsigned) - Indicates the default wait time (in minutes) associated with each severity level.
- **Primary Key**: `severity_index`.
- **Character Set**: UTF8MB4 with collation `utf8mb4_0900_ai_ci`.

### Sample Data for `emergency_severity`
- Inserts predefined values ranging from 'Immediate life-saving intervention required' to 'Non-urgent/stable, not requiring resources' with associated default wait times.

### Table: `users`
- **Purpose**: Manages user information for system access.
- **Fields**:
  - `user_id`: Smallint - A unique identifier for each user.
  - `user_code`: Varchar(8) - A unique code assigned to each user.
  - `user_pin`: Char(3) - A PIN for user authentication.
  - `full_privs`: Char(1) - Indicates whether the user has full privileges ('Y' or 'N').
- **Primary Key**: `user_id`.
- **Unique Key**: `user_code_UNIQUE` on `user_code`.
- **Character Set**: UTF8MB4 with collation `utf8mb4_0900_ai_ci`.

### Sample Data for `users`
- Inserts predefined user records, each with a unique user code, pin, and privileges indicator.

## Usage
The database structure is integral to the HTS, enabling efficient management of emergency cases based on severity and handling user authentication and authorization for system access.

**Note**: This MySQL dump is a snapshot of the database structure and sample data as of a specific date. It might require updates or modifications to align with the latest system requirements or operational practices.
led out.
- **Data Compilation**: If valid, compiles the user information into a formatted string.
- **File Creation and Download**:
  - Creates a Blob from the compiled string.
  - Generates a downloadable text file (`user_information.txt`) containing the user's information.
  - Triggers a download action for the user to save the file.
- **Alerts**: If any field is missing, alerts the user to select all information before submitting.

## Usage
This script enhances the Hospital Triage App by providing an interactive and user-friendly way to capture and download patient information. It ensures that all necessary data is selected and allows for easy exportation of this information, potentially for record-keeping or further processing.

**Note**: The script includes client-side data validation but does not include server-side handling, which would be necessary for a complete, production-ready application.

                                                                         # HTS_DB.sql

                                                                         
