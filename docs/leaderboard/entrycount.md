# Get Leaderboard Entry Count

![Blueprint node screenshot](../resources/entrycount.png)

<span style="font-size:17px">Returns the total number of entries currently stored on the specified Steam leaderboard.</span>

#### Inputs
| `Pin` | `Type` | `Description` |
| --- | --- | --- |
| `Leaderboard Handle` | `FSAL_LeaderboardHandle` | Handle obtained from **Find** or **Create** (must be valid). |

#### Outputs
| `Pin` | `Type` | `Description` |
| --- | --- | --- |
| `Entry Count` | `int32` | Number of rows on this leaderboard. |

<h3><b>Notes</b></h3>
<ul style="font-size:0.72rem; line-height:1.75">
  <li>This is a <b>pure</b> node (no async work).</li>
  <li>Useful for paging and UI (“N entries total”).</li>
</ul>

