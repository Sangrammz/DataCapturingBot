Data Capturing Bot – UiPath Automation Project

This project automates data entry from Excel into both Web and Desktop applications using UiPath Studio.
It demonstrates reading data, filling forms, handling dropdowns & radio buttons, and running multiple workflows in parallel.

Project Overview
---------------------------------


Name: DataCapturingBot

Tools: UiPath Studio, Excel, Web/Windows Forms

Workflows:

WebDataCapturingBot.xaml

DesktopDataCapturingBot.xaml

Main.xaml (runs both in parallel)


How to Create & Run the Bot
----------------------------------------------------------------

1️⃣ Create the Project

Open UiPath Studio → New Process → Blank Process → Name it DataCapturingBot.

2️⃣ WebDataCapturingBot.xaml

Purpose: Automates data entry on a website.
Steps:

Add a new Sequence → name it WebDataCapturingBot.xaml.

Use Read Range to load Excel data → store in dtInputData.

Add Use Application/Browser → open target webpage (e.g., form URL).

Add For Each Row in DataTable → use dtInputData.

Use Type Into to enter text fields (row("Name").ToString, etc.).

Use If for gender radio buttons → click Male or Female.

Use Select Item for dropdowns (row("City").ToString).

Click Submit → add small delay if page reloads.

Debug & Run → data should fill automatically.

3️⃣ DesktopDataCapturingBot.xaml

Purpose: Automates data entry on a desktop application.
Steps:

Add another Sequence → name it DesktopDataCapturingBot.xaml.

Use Read Range to load Excel → store in dtDesktopData.

Use Use Application/Browser → indicate desktop window.

Add For Each Row in DataTable → use dtDesktopData.

Use Type Into for form fields (row("FullName").ToString, etc.).

Use If for gender radio buttons.

Use Select Item for dropdowns (row("Department").ToString).

Click Submit → optional delay for app response.

Debug & Run → confirm data entries are correct.

4️⃣ Main.xaml – Run Workflows in Parallel

Purpose: Execute both bots together.
Steps:

Open Main.xaml.

Drag a Parallel activity to the canvas.

In each branch, use Invoke Workflow File:

Branch 1 → WebDataCapturingBot.xaml

Branch 2 → DesktopDataCapturingBot.xaml

Debug or Run → both workflows execute simultaneously.

5️⃣ Connect Project to GitHub

Purpose: Version control & collaboration.
Steps:

Create a new GitHub repo → copy repo URL.

In UiPath Studio → Home → Team → GIT → Init Repository.

Manage Remotes → Add → paste GitHub repo URL.

Commit and Push → upload project files.

Verify on GitHub — all .xaml files should appear.

✅ Final Structure
DataCapturingBot/
├── Main.xaml
├── WebDataCapturingBot.xaml
├── DesktopDataCapturingBot.xaml
├── project.json
└── .gitignore

🧩 Key Features

Reads data from Excel and fills both web & desktop forms.

Handles text, dropdowns, and radio buttons.

Executes multiple workflows in parallel.

Integrated with GitHub for version control.

▶️ Run the Bot

Open DataCapturingBot in UiPath Studio.

Run Main.xaml → both workflows execute concurrently.

Monitor browser and desktop forms — data is captured automatically.
