# Download Steam Leaderboard Entries (Users)

![Blueprint node screenshot](../resources/getentryuser.png)

<span style="font-size:17px">Asynchronously fetches leaderboard rows for a <b>specific list of Steam users</b> (by SteamID64). Returns a compact <code>Entries Data</code> handle and an <code>Entry Count</code>. Use <b>Get Downloaded Leaderboard Entry</b> to read individual rows.</span>

#### Inputs
| `Pin` | `Type` | `Description` |
| --- | --- | --- |
| `Leaderboard Handle` | `FSAL_LeaderboardHandle` | Handle from **Find** or **Create** (must be valid). |
| `SteamIDs` | `String[]` | Array of SteamID64 strings (e.g., `7656119...`). Invalid IDs are skipped. Internally clamped to a maximum number of users per call. |

#### Outputs
| `Pin` | `Type` | `Description` |
| --- | --- | --- |
| `On Success` | `Exec` | Fired when rows are downloaded successfully. |
| `On Failure` | `Exec` | Fired on I/O failure, invalid handle, empty/invalid user list, or other errors. |
| `Entries Data` *(On Success)* | `FSAL_LeaderboardEntriesData` | Container holding all downloaded rows and request metadata. Pass this into **Get Downloaded Leaderboard Entry**. |
| `Entry Count` *(On Success)* | `int32` | Number of rows that were actually downloaded. Use as the max index when iterating. |

<h3><b>Usage</b></h3>
<ul style="font-size:0.72rem; line-height:1.75">
  <li>Prepare a list of SteamID64 strings for the users you care about (party members, friends, rivals, etc.).</li>
  <li>Call <b>Download Steam Leaderboard Entries (Users)</b> with a valid <code>Leaderboard Handle</code> and your <code>SteamIDs</code> array.</li>
  <li>On <b>Success</b>, store the returned <code>Entries Data</code> and <code>Entry Count</code>.</li>
  <li>Loop from <code>Index = 0 .. EntryCount - 1</code> and call <b>Get Downloaded Leaderboard Entry</b> to retrieve each row struct (SteamID, PlayerName, GlobalRank, Score, Details[], UGC data, etc.).</li>
</ul>

<h3><b>Notes</b></h3>
<ul style="font-size:0.72rem; line-height:1.75">
  <li>Only users <b>with an existing score</b> on the leaderboard will return a row.</li>
  <li>Large lists are clamped internally (roughly up to <b>100</b> users per request). For larger sets, batch multiple calls.</li>
  <li>Provide SteamID64 <b>as strings</b>; malformed or invalid IDs are ignored.</li>
  <li>If <b>no valid IDs</b> remain after parsing, the node will fire <b>On Failure</b> with a clear error message.</li>
</ul>
