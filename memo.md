curl \
   -H ...\
   -d "@TestCampaignReport.json"
   -X POST "<ROOT_PATH>/v1/reports/campaigns"


=================================================================================

openssl pkcs12 -export -in <PEM_file>.pem -inkey <PRIVATE_KEY>.key -out <FILENAME>.p12

curl \
   --cert ./<FILENAME>.p12 \
   --pass <PASSWORD> \
   -H "Authorization: orgId=<ORG_ID>" \
   "https://api.searchads.apple.com/api/v1/campaigns/<CAMPAIGN_ID>"

==========================================================================================

curl \
- E <FILE_NAME>.pem
-- key <PRIVATE_KEY>.key
- H "Authorization: orgId=<ORG_ID>" \
"https://api.searchads.apple.com/api/v1/campaigns/<CAMPAIGN_ID>"
