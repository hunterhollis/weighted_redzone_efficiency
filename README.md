# Weighted Red Zone Efficiency

## Overview

NFL offensive red zone efficiency is commonly measured by touchdown rate (percentage of red zone trips resulting in a touchdown) or scoring rate (percentage of red zone trips resulting in any score). While more advanced metrics like Expected Points Added (EPA) or Win Probability Added (WPA) on red zone opportunities may be more comprehensive measures of success, the rate statistics are commonly reported by broadcasts for simplicity and familiarity.

What may find a happy medium is a metric that is more precise than the existing scoring rates but is still simpler and more familiar to common fans than EPA or WPA. A weighted red zone scoring rate could represent that balance. The weighted red zone scoring rate proposed here would improve upon the overall scoring rate by penalizing teams for scoring field goals rather than touchdowns; it would improve upon the touchdown rate by rewarding teams for not turning the ball over and scoring any points.

## Methodology

The weighted scoring rate is the percentage of possible points scored across all red zone trips. Actual points on each red zone possession (3, 6, 7, or 8) are summed and then divided by the total possible points from those possessions (assumed to be 7 for each trip). The assumption of 7 possible points is imprecise but a reasonable starting point. The expected value of a touchdown is slightly less than 7 because: 1) PAT attempts are successful less than 100% of the time, and 2) 2-point conversion attempts are successful less than 50% of the time.

In the Jupyter Notebook [file](redzone_efficiencies.ipynb), play-by-play data from the 2024 NFL season was accessed using `nfl_data_py`. Red zone scoring rate, touchdown rate, weighted scoring rate, and respective rankings were calculated for each team. For additional comparison, total EPA, EPA per play, total WPA, and WPA per play in the red zone were also calculated and ranked for each team. A preview of the first ten teams is displayed in the table below.

![table of red zone efficiencies](visualizations/red_zone_efficiencies_preview.png)

Bar charts were also created for each of the 7 red zone efficiency metrics to compare teams visually. Team colors and logos were also accessed from `nfl_data_py` and used in these charts. The chart of weighted scoring rates is displayed below.

![chart of weighted scoring rate](visualizations/weighted_rz_eff.png)

## Conclusions

**End of season update**

I would argue that the weighted scoring rate is a more holistic red zone metric than either the overall scoring rate or the touchdown rate. The weighted metric improves on the overall rate by rewarding teams for scoring touchdowns over field goals, but it also improves on the touchdown rate by rewarding teams for not turning the ball over and converting field goals.

The biggest beneficiaries of a switch from overall rate to weighted rate would be teams with a below-average scoring rate and above-average touchdown rate. These teams may be more aggressive in attempting 4th-down conversions instead of field goals. They may also be more prone to turnovers. These teams are touchdown or bust.
- DET: 17th Overall -> 4th Weighted (+13)
- BAL: 9th Overall -> 1st Weighted (+8)
- CAR: 15th Overall -> 7th Weighted (+8)
- DEN: 19th Overall -> 12th Weighted (+7)

The biggest beneficiaries of a switch from touchdown rate to weighted rate would be teams with an above-average scoring rate and below-average touchdown rate. These teams may be more conservative about attempting fields rather than 4th-down conversions. They may also be less prone to turnovers. These teams are determined to come away with points.
- LAC: 18th TD Rate -> 8th Weighted (+10)
- IND: 23rd TD Rate -> 14th Weighted (+9)
- KC: 21st TD Rate -> 15th Weighted (+6)
- ARI: 17th TD Rate -> 13th Weighted (+4)

Just 2 teams would benefit from a change to weighted scoring rate regardless of the status quo metric. These teams have very similar rankings between overall scoring rate and touchdown rate. They may also benefit from success on PAT and 2-point conversion attempts, which are a factor in the weighted average.
- CAR: 15th Overall, 8th TD Rate -> 7th Weighted
- WAS: 6th Overall, 6th TD Rate -> 5th Weighted
Several other teams have a weighted rate tied with their scoring rate or touchdown rate.

Note: the statistics above are accurate through the end of the 2024 season.

The advanced metrics of Expected Points Added (EPA), Win Probability Added (WPA), and their respective per-play averages are still considered more comprehensive and precise metrics. However, scoring rate and touchdown rate are still preferred by broadcasts and major media outlets because of its familiarity to fans. If weighted scoring rate could be introduced as an alternative, it could be a happy middle ground between the basic rates and advanced metrics—more precise than the rates and more digestible than EPA or WPA.

## Attribution

A big thank you to nfl_data_py and nflfastR for making this data available. Y'all do amazing work to democratize sports analytics.
