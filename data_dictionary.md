## Data dictionary

These are the tables with columns and descriptions:

* consumer

| Column | Type | Description |
| ----- | ----- | ----- |
| ConsumerID | bigint(20) | Unique Identifier for Consumer |
| MobileNo | varchar(20)| Customer Mobile Number |
| EmailID | varchar(150)| Customer Email ID |
| IsActive | tinyint(1) | Flag whether the customer is active |
| CreatedDate | datetime| Date when record was created |

* consumer_product

| Column | Type| Description |
| ----- | ----- | ----- |
| ConsumerProductID | bigint(20) | unique identifier for the owned product |
| ConsumerID| bigint(20) | Foreign Key from consumer table |
| BrandID | bigint(20) | Unique identifier for each brand |
| ProductID | bigint(20) | Unique identifier for a specific product from a brand |
| IMEI1| varchar(50) | Device IMEI |
| IMEI2| varchar(50) | Device IMEI for dual sims. NULL if it is a single SIM phone |
| SerialNo| varchar(50) | Device serial number |
| DateOfPurchase | date| Device purchase date  |
| WarrantyTill | date| Device warranty validity, will default to 1970-01-01 |
| IsActive| tinyint(1) | Flag whether the device is active |
| CreatedDate | datetime | Date when record was created |

* consumer_servicerequest

| Column | Type| Description |
| ----- | ----- | ----- |
| ConsumerServiceRequestID | bigint(20) | Unique identifier |
| Source | varchar(50)| Source where service request is raised from |
| ConsumerID| bigint(20) | Foreign Key from consumer table |
| ConsumerProductID| bigint(20) | Foreign Key from consumer_product table |
| SoldPlanID| bigint(19) | Foreign Key from sold_plan table |
| ServiceTypeID | bigint(20) | Unique identifier for service type availed |
| Lat | decimal(20,6) | Location of customer (Latitude) |
| Lng | decimal(20,6) | Location of customer (Longitude) |
| Zipcode| int(6)| Zipcode of customer location |
| Status | varchar(100) | Status of customer service request |
| ScheduledDateTime| datetime | Date & time when the customer request was scheduled |
| CreatedDate | datetime | Date when record was created |

* sold_plan

| Column | Type | Description |
| ----- | ----- | ----- |
| SoldPlanID| bigint(19)| Unique identifier for a plan sold |
| PlanID | bigint(19)| Unique idenfier for each plan |
| PlanAmount| int(19) | Amount paid for plan |
| FulfillerID | bigint(19)| Unique ID for Insurance fulfiller |
| ConsumerProductID | bigint(19)| Foreign Key from consumer_product table |
| ConsumerID| bigint(19)| Foreign Key from consumer table |
| DateOfPurchase | datetime| Date when plan was purchased |
| DateOfActivation | datetime| Date when plan was activated |
| ValidityDate | datetime| Date till which plan is valid |
| Status | tinyint(4)| Plan status |
| Source | varchar(255) | Source where plan was purchased from |
| CreatedDate | datetime| Date when record was created |
