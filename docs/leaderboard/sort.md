# Get Leaderboard Sort Method

![Blueprint node screenshot](../resources/sort.png)

<span style="font-size:18px">Returns how scores are ranked on this leaderboard (Ascending or Descending).</span>

#### Inputs
| `Pin` | `Type` | `Description` |
| --- | --- | --- |
| `Leaderboard Handle` | `FSAL_LeaderboardHandle` | Handle obtained from **Find** or **Create** (must be valid). |

#### Outputs
| `Pin` | `Type` | `Description` |
| --- | --- | --- |
| `Sort Method` | `Enum (Ascending / Descending)` | Ranking order used to compare scores. |

<h3><b>Notes</b></h3>
<ul style="font-size:0.72rem; line-height:1.75">
  <li><b>Pure</b> node. Pair with <b>Display Type</b> to format and interpret scores correctly (e.g., timeboards often use <b>Ascending</b>).</li>
</ul>
