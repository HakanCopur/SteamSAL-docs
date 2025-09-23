# Get Steam Leaderboard Entries

![Blueprint node screenshot](../resources/getentry.png)

<span style="font-size:17px">Asynchronously downloads leaderboard rows for the chosen **scope** (Global, Global Around User, or Friends). Returns an array of parsed entries you can use directly in UI.</span>

#### Inputs
| `Pin` | `Type` | `Description` |
| --- | --- | --- |
| `Leaderboard Handle` | `FSAL_LeaderboardHandle` | Handle from **Find** or **Create** (must be valid). |
| `Request Type` | `Enum (Global / Global Around User / Friends)` | Selects the scope of results. |
| `Range Start` | `int32` | For **Global**: 1-based start rank. For **Global Around User**: negative offset (e.g. `-5`). Ignored for **Friends**. |
| `Range End` | `int32` | For **Global**: 1-based end rank. For **Global Around User**: positive offset (e.g. `+5`). Ignored for **Friends**. |
| `Details Max` | `int32` | Max number of `Details[]` integers to fetch per row (0 to skip; up to 64 supported by Steam). |

#### Outputs
| `Pin` | `Type` | `Description` |
| --- | --- | --- |
| `On Success` | `Exec` | Fired when rows are downloaded successfully. |
| `On Failure` | `Exec` | Fired on I/O failure, invalid handle, or bad range. |
| `Entries` *(On Success)* | `TArray<FSAL_LeaderboardEntryRow>` | Array of parsed rows. |


<h3><b>Notes</b></h3>
<ul style="font-size:0.72rem; line-height:1.75">
  <li><b>Global</b> uses absolute ranks: <code>(Range Start .. Range End)</code> are <b>1-based</b>.</li>
  <li><b>Global Around User</b> centers on the local player: use a <b>negative</b> start and <b>positive</b> end (e.g., <code>-5 .. +5</code>).</li>
  <li><b>Friends</b> ignores ranges and returns only Steam friends who have entries.</li>
  <li>Set <code>Details Max = 0</code> if you don’t need extra data for faster requests.</li>
  <li>Reuse the same <code>Leaderboard Handle</code> across upload/download to avoid extra lookups.</li>
</ul>
