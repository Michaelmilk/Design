## Split db statistic table

* view state update
  * view state timestamp
  * view version latency 



* view metrics daily update
  * view daily error and triage count
  * view daily missla detail(==daily miss sla version detail==)
  * view daily triage detail(==daily triage version detail==)



## Changes

1. delete [ViewVersionDuration], [TriageCommitDuration] cols, these metrics can be fetched from verionslatency
2. split DbTriageStatistic to DbTriageStatistic and DbTriageMetric