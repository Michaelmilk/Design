## Report implementation design

* basic view version statistic(==version latency==)
* summary
  * Sla 
    * version missSla
      * for misssla metric num
    * daily missSla
      * for misssla trend chart
  * triage
    * version triage
      * for triage metric num
    * daily triage
      * for triage trend chart
  * Rank(sort by missla times, triage times, segment, owner )
    * version misssla
    * version triage
* details(to generate view various charts)
  * related versionLatencies
  * related triageSupervisors



> code
>
> ```
> public class TriageReport
> {
>     public string ReportTimeSpan { get; set; }
>     public string Type { get; set; }
>     public string StartDate { get; set; }
>     public string EndDate { get; set; }
>     public TriageReportSummary TriageReportSummary { get; set; }
>     public TriageReportDetail TriageReportDetail { get; set; }
>     public string CreatedTime { get; set; }
> }
> ```
>
> 



## Summary

* Miss SLA 
  * missSla view ids group by diff cause
  * missSla times(all missSla versions' count of all ids)

* Triage 

  * triage view ids group by commit and uncommit
  * triage times(all triage versions' count of all ids)

  ```
  public class TriageReportSummary
  {
      public int AllViewCount { get; set; }
      public MissSlaSummary MissSlaSummary { get; set; }
      public TriageSummary TriageSummary { get; set; }
      public RankSummary RankSummary { get; set; }
  }
  
  
  ```

  

