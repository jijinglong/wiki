## Apple Search


### 使用pkcs12
```
openssl pkcs12 -export -in <PEM_file>.pem -inkey <PRIVATE_KEY>.key -out <FILENAME>.p12
```

```
curl \
   --cert ./<FILENAME>.p12 \
   --pass <PASSWORD> \
   -H "Authorization: orgId=<ORG_ID>" \
   "https://api.searchads.apple.com/api/v1/campaigns/<CAMPAIGN_ID>"
```

### 使用pem
```
curl \
- E <FILE_NAME>.pem
-- key <PRIVATE_KEY>.key
- H "Authorization: orgId=<ORG_ID>" \
"https://api.searchads.apple.com/api/v1/campaigns/<CAMPAIGN_ID>"
```

### example

```
curl -E Midas.pem --key Midas.key -H "Authorization: orgId=460020" -d "@TestCampaignReport.json" -H "Content-Type: application/json" -X POST "https://api.searchads.apple.com/api/v1/reports/campaigns"
```

```
TestCampaignReport.json
{
	"startTime": "2018-02-01",
    "endTime": "2018-02-01",
    "selector": {
        "orderBy": [{"field":"campaignId","sortOrder":"DESCENDING"}]
    },
    "returnRowTotals":true
}
```
