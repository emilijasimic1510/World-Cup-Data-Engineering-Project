# Data Quality Checks

This document lists the validation rules applied during the transformation.

## Structural
- Drop fully empty rows
- Keep first record per `MatchID`
- `MatchID` must be present and unique

## Type & Range
- Convert numeric fields with `errors='coerce'`
- `Year` must be between 1930 and 2026
- `Datetime` must not be in the future (ignoring `NaT`)

## Consistency
- No negative values in goals-related columns
- Half-time goals ≤ full-time goals (per team and in total)
- `Home Team Name` must differ from `Away Team Name`

## Attendance Imputation
- Fill with median by `Year`, fallback to global median
- Round and store as nullable `Int64`
