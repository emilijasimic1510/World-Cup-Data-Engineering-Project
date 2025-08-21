# Pipeline & Workflow

## Steps
1. **Load raw data (Matches.csv)**  
   - Encoding: `latin-1`
   - Load with `pandas.read_csv(...)`

2. **Type conversion & normalization**  
   - `Datetime` → `datetime64[ns]`
   - Numeric fields: `Year`, goals fields, `Attendance`, `RoundID`, `MatchID`

3. **De-duplication & NaNs**  
   - Drop fully empty rows
   - Keep first occurrence per `MatchID`
   - Remove rows with missing `MatchID`

4. **Data validation rules**
   - No negative goals
   - Half-time goals ≤ full-time goals (per team and total)
   - `Datetime` ≤ today (ignore `NaT`)
   - Unique `MatchID`
   - `Home Team Name` ≠ `Away Team Name`
   - `Year` in [1930, 2026]

5. **Attendance imputation**
   - Median by `Year`, then global median as fallback
   - Round to integer (nullable `Int64`)

6. **Feature engineering**
   - `Winner` / `Loser` / `ResultType` (FT / WinConditions / Draw)
   - `Goals` = `Home Team Goals + Away Team Goals`
   - Placings (Champion, Runners-up, Third, Fourth) per World Cup year
   - Special handling for **1950** (final group) and **1930** ordering

7. **Aggregations per year**
   - Total goals, attendance, matches
   - Number of qualified teams (unique teams per year)

8. **Export**
   - `outputs/WorldCup.csv` (analytics-ready table)
