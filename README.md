# s3_hash_join
Hash join of fact and dimension files on one column.

It appends one column to a large partitioned impressions file from smaller campaign dimension file.

## Fact was
    50000,campaign_00,video_0,0.5
    50080,campaign_00,video_0,0.1

## Fact now
    50000,campaign_00,video_0,0.5,metadata 1
    50080,campaign_00,video_0,0.1,metadata 1

## Dimension
    campaign_00,video campaign "xvbcjfz",metadata 1
    campaign_01,video campaign "cjzfybq",metadata 1

## Exec log
```
['campaign_00', 'video campaign "xvbcjfzln"', 'metadata 1']
{'campaign_00': ['campaign_00',
                 'video campaign '
                 '"xvbcjfzln"',
                 'metadata 1']}
tables/FACT_IMPRESSIONS/B_0/FACT_IMPRESSIONS.B_0.campaign_00.campaign.csv.gz
Fact file: tables/FACT_IMPRESSIONS_APPENDED/B_0/FACT_IMPRESSIONS_APPENDED.B_0.campaign_00.campaign.csv.gz
Fact file: tables/FACT_IMPRESSIONS_APPENDED/B_1/FACT_IMPRESSIONS_APPENDED.B_1.campaign_00.campaign.csv.gz
Fact file: tables/FACT_IMPRESSIONS_APPENDED/B_2/FACT_IMPRESSIONS_APPENDED.B_2.campaign_00.campaign.csv.gz
Fact file: tables/FACT_IMPRESSIONS_APPENDED/B_3/FACT_IMPRESSIONS_APPENDED.B_3.campaign_00.campaign.csv.gz
Fact file: tables/FACT_IMPRESSIONS_APPENDED/B_4/FACT_IMPRESSIONS_APPENDED.B_4.campaign_00.campaign.csv.gz
Fact file: tables/FACT_IMPRESSIONS_APPENDED/B_5/FACT_IMPRESSIONS_APPENDED.B_5.campaign_00.campaign.csv.gz
Fact file: tables/FACT_IMPRESSIONS_APPENDED/B_6/FACT_IMPRESSIONS_APPENDED.B_6.campaign_00.campaign.csv.gz
Fact file: tables/FACT_IMPRESSIONS_APPENDED/B_7/FACT_IMPRESSIONS_APPENDED.B_7.campaign_00.campaign.csv.gz
Total uploaded, bytes: 83
Total uploaded, bytes: 78
Total uploaded, bytes: 83
Total uploaded, bytes: 81
Total uploaded, bytes: 75
Total uploaded, bytes: 76
Total uploaded, bytes: 92
Total uploaded, bytes: 67
s3update.py executed in 1.73 seconds.
