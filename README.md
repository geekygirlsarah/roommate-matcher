# Roommate Matcher

A simple, client-side web application to match students into hotel rooms based on their preferences and avoidance constraints.

## Features

- **Spreadsheet Integration**: Copy and paste data directly from Excel or Google Sheets (Tab-separated values).
- **Preference Matching**: Uses a greedy heuristic algorithm to optimize room assignments.
- **Mutual Preference Priority**: Optionally give higher weight to students who both want to room with each other.
- **Hard Constraints**: "Avoid" lists are strictly enforced; the algorithm will not place students in the same room if either student lists the other as someone to avoid.
- **Customizable Room Size**: Set the maximum number of students per room.
- **Local Only**: All processing happens in your browser. No data is sent to a server.

## How to Use

1. Open `index.html` in any modern web browser.
2. Prepare your student data in a spreadsheet with the following columns:
   - **Column 1 (Name)**: The student's full name.
   - **Column 2 (Preferred Roommates)**: Comma-separated names of preferred roommates.
   - **Column 3 (Avoid)**: Comma-separated names of students to avoid.
3. Copy the rows (including those columns) and paste them into the "Student List" text area.
4. Adjust the **Room Size** and the **Prefer Mutual Roommates** toggle as needed.
5. Click **Match Students**.

## Technical Details

The application uses a greedy matching algorithm:
- It seeds rooms with the most "constrained" students first (those with the most preferences or avoidance requirements).
- It evaluates potential roommates using a scoring system that rewards mutual preferences and one-way preferences while applying a massive penalty for avoidance constraints.
- Built with HTML, JavaScript, and Bootstrap 5.

## License

This project is licensed under the CC0 1.0 Universal - see the [LICENSE](LICENSE) file for details.
