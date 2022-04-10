# marketing dashboard
This is a simple demonstration of an interactive marketing dashboard on Tableau.
Purpose of the dashboard is to keep track of sales revenue and transactions that occured over a 12 months period.
https://public.tableau.com/views/GoogleAnalyticsDashboard_16495739305500/MarketingDashboard?:language=en-US&:display_count=n&:origin=viz_share_link

![Marketing Dashboard](https://user-images.githubusercontent.com/30048857/162609707-4e980030-3fd7-4313-b295-2ba587e06dc8.png)


## dataset
The dataset was obtained from Google BigQuery Public Dataset - "Google Analytics Sample Dataset"
The SQL query used to extract the data can be found below:

  SELECT
      fullVisitorId AS user_id,
      visitId AS visit_id,
      date,
      totals.transactions AS transactions,
      totals.transactionRevenue/1000000 AS revenue,
      trafficSource.source AS source,
      channelGrouping AS source_type
  FROM
      `bigquery-public-data.google_analytics_sample.ga_sessions_*`
  WHERE
  _TABLE_SUFFIX BETWEEN '20160801' AND '20170801'
  AND totals.transactionRevenue IS NOT NULL;
  
