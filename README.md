How To Create
===========


Step 1: Create the Project

Open UiPath Studio.

Click Process → Blank Process.

Name it DataCapturingBot → Choose location → Click Create.

Step 2: Add a New Workflow

In the Project panel, right-click the project → Add → New Sequence.

Name it WebDataCapturingBot.xaml.

Open it — this will be your main automation workflow.

Step 3: Read Data from Excel

Search for Read Range activity (Excel or Workbook version depending on if Excel App is installed).

Specify the file path of your Excel sheet (where data is stored).

In the Output property, create a variable (e.g. dtInputData of type DataTable).

This stores all your Excel rows & columns for looping.

Step 4: Open Web Application

Use Use Application/Browser activity.

Enter or paste the URL of the webpage where you want to enter data.

Example: https://example.com/form

Step 5: Loop Through Data Rows

Drag a For Each Row in DataTable activity below the browser activity.

Select dtInputData as the DataTable.

This lets you access each cell’s value with row("ColumnName").ToString.

Step 6: Type Data into Web Form

Inside the For Each Row loop:

Use Type Into activities for text fields.
Example:

For Name field → row("Name").ToString

For Email field → row("Email").ToString

Make sure to indicate each field on screen using indicate on screen option.

Step 7: Handle Radio Buttons (Gender)

Use an If activity:

Condition: row("Gender").ToString.ToLower = "male"

In Then → use Click activity to click the Male radio button.

In Else → use Click activity to click the Female radio button.

Step 8: Handle Drop-down Selection

Use the Select Item activity.

Indicate the drop-down element on the screen.

Pass value from DataTable like:
row("City").ToString

Step 9: Submit the Form

Use a Click activity on the Submit button.

Add a Delay (1–2 seconds) after it if the page refreshes.

Step 10: Debug and Run

Click Debug File or Run File.

Watch UiPath fill in each row of data automatically!

Check for any selector errors or delays — adjust accordingly.
