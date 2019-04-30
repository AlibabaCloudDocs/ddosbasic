# DescribeOpEntities {#reference1760 .reference}

You can call this operation to perform queries on operation logs.

## Request parameters { .section}

|Name|Type|Required|Description|
|----|----|--------|-----------|
|StartTime|Long|Yes|The start timestamp of the query. Unit: milliseconds.|
|EndTime|Long |Yes|The end timestamp of the query. Unit: milliseconds.|
|PageNo|Integer|Yes|The number of the starting page returned in the query result.|
|PageSize|Integer|Yes|The number of log records on each page. Maximum value: 50.|

## Response parameters { .section}

|Name|Type|Description|
|----|----|-----------|
|Total|Integer|The total number of log records.|
|OpEntities|OpEntity|The operation log records. For more information, see [OpEntity](#).|

|Name|Type|Description|
|----|----|-----------|
|GmtCreate|Long|The time when the log record was generated. Unit: milliseconds.|
|EntityType|Integer|The type of the operation object. Valid value: 1. A value of 1 indicates that the operation object is an IP address.|
|EntityObject|String|The value of the operation object.|
|OpAction|Integer|The operation type. Valid value: 1. A value of 1 indicates that the operation is to change the burstable bandwidth.|
|OpAccount|String|The user who performed the operation.|
|OpDesc|String|The details of the operation. For more information, see [OpDesc](#).|

|Parameter|Type|Description|
|---------|----|-----------|
|oldValue|EntityValue|The old value. For more information, see [EntityValue](#).|
|newValue|EntityValue|The new value. For more information, see [EntityValue](#).|

|Name|Type|Description|
|----|----|-----------|
|elasticBandwidth|Integer|The value of the burstable bandwidth.|

## Examples { .section}

**Sample requests**

```
{
  "StartTime": 123,
  "EndTime": 456,
  "PageNo": 1,
  "PageSize": 10
}

```

**Sample responses**

```
{
  "Total": 10,
  "OpEntities": [
    {
      "gmtCreate": 1120384，
      "entityObject": "1.1.1.1",
      "opAction": 2,
      "opDesc": {
	    "oldValue": {
		  "elasticBandwidth": 10
		},
		"newValue": {
		  "elasticBandwidth": 30
		}
	  },
      "opResult": 1
    }
  ]
}

```

