# Session 05 
# Modernization






## typical IT Enviornment by Migration Pattern 
- 20% replatform
- Refactor

- High Value & High Impact
- High Value & Medium Impact

### Application Selection Criteria
#### Business Indicator

- LOB, Critical to Business success 
- Customer Facing 
- Significant impact to revenue 
- Proprietary business logic 
- Market Differentiator 
- Value exceeds cost 

#### Technical Indicator 

- Old technology, no support 
- Performance & scalability issues 
- Difficult to extend capabilities 
- Lack of skilset, lost konwledge 
- Too many bugs, spaghetti code 
- Expensive to run, difficult to integrate 


## AWS Modernization
- Move to Cloud 
- Move to Container
- Move to Managed Database
- Move to OpenSource
- Move to Analytics
- Move to Modern DevOps


**Microservice**
- Re-usable modules of code 
- Independant SLA 
- Built and deployed Independantly
  
  









 ==========
Code :::

unique_id=$(date +%Y%m%d%H%M%S)
session_id=04
file_name=$(git diff --name-only)
git add . && git commit -m "Update: $file_name Session:04 - ID: $unique_id"