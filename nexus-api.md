# Nexus API API documentation version v1

---

## /ajax-login

### /ajax-login

#### **POST**:
Authorization with client ID and secret

#### application/x-www-form-urlencoded (application/x-www-form-urlencoded) 

##### *application/x-www-form-urlencoded*:
| Name | Type | Description | Required | Pattern |
|:-----|:----:|:------------|:--------:|--------:|

### Response code: 200

#### application/json (application/json) 

```
{
  "access_token": "60qJ8mC4NUFxKjBXFJF0XOb5UKtpJT"
}
```

##### *application/json*:
| Name | Type | Description | Required | Pattern |
|:-----|:----:|:------------|:--------:|--------:|
| access_token |  string |  | true |  |

### Response code: 401

#### application/json (application/json) 

```
{
  "error_message": "Authentication credentials were not provided."
}
```

##### *application/json*:
| Name | Type | Description | Required | Pattern |
|:-----|:----:|:------------|:--------:|--------:|
| error_message |  string |  | true |  |

---

## /arb/ebi-model-types-recommendations/

### /arb/ebi-model-types-recommendations/

#### **GET**:
Get Ebi Model types with recommendations

### Response code: 200

#### application/json (application/json) 

```
[
  {
    "id": 1,
    "type": "Behavior",
    "recommendations": [
      {
        "rec_name": "ALL_FSIK"
      },
      {
        "rec_name": "SUB_AUTOPAY"
      },
      {
        "rec_name": "SUB_CALL_ANYQUEUE"
      },
      {
        "rec_name": "SUB_NUDGE_VALUE"
      },
      {
        "rec_name": "SUB_SELF_SERVICE"
      },
      {
        "rec_name": "SUB_TRUCKROLL"
      }
    ]
  },
  {
    "id": 2,
    "type": "Retention",
    "recommendations": [
      {
        "rec_name": "SUB_CHURN_NPD"
      },
      {
        "rec_name": "SUB_CHURN_TOTAL"
      },
      {
        "rec_name": "SUB_DNG_X1"
      }
    ]
  }
]
```

##### List of *items*:

| Name | Type | Description | Required | Pattern |
|:-----|:----:|:------------|:--------:|--------:|
| id |  integer |  | true |  |
| type |  string |  | true |  |
| recommendations | items array |  | true |  |

items:

| Name | Type | Description | Required | Pattern |
|:-----|:----:|:------------|:--------:|--------:|
| rec_name |  string |  | true |  |

### Response code: 401

#### application/json (application/json) 

```
{
  "error_message": "Authentication credentials were not provided."
}
```

##### *application/json*:
| Name | Type | Description | Required | Pattern |
|:-----|:----:|:------------|:--------:|--------:|
| error_message |  string |  | true |  |

---

## /iapi/get-ebi-recommendations/

### /iapi/get-ebi-recommendations/

#### **POST**:
Submit ebi arbitrate form and get recommendations

#### application/json (application/json) 

##### *application/json*:
| Name | Type | Description | Required | Pattern |
|:-----|:----:|:------------|:--------:|--------:|
| account_number |  string |  | true |  |
| house_key |  string |  | true |  |
| model_type_id | items array |  | true |  |
| recs_by_model_type |  boolean |  | true |  |
| recs_requested |  integer |  | true |  |
| timestamp |  number |  | true |  |

items:

| Name | Type | Description | Required | Pattern |
|:-----|:----:|:------------|:--------:|--------:|
| id |  integer |  | true |  |
| model_recommendations | items array |  | true |  |

items:

| Name | Type | Description | Required | Pattern |
|:-----|:----:|:------------|:--------:|--------:|
| rec_name |  string |  | true |  |

### Response code: 200

#### application/json (application/json) 

```
{
  "recs_by_model_type": true,
  "recs_requested": 2,
  "recs_available": 8,
  "account_number": 8220204141109707,
  "timestamp": "2018-02-13T18:32:43.178537",
  "recommendations": [
    {
      "rec_name": "SUB_DNG_X1",
      "model_type_id": 2,
      "rec_label": "Likelihood of a customer to drop X1 product within the next 90 days",
      "priority": 1,
      "probability": "9.83%",
      "rec_id": "EBI_N16_01_002"
    },
    {
      "rec_name": "SUB_CHURN_TOTAL",
      "model_type_id": 2,
      "rec_label": "Likelihood of a customer to disconnect all service within the next 90 days. HELLO MY NAME IS KEVIN. HELLO MY NAME IS KEVIN. HELLO MY NAME IS KEVIN. HELLO MY NAME IS KEVIN",
      "priority": 2,
      "probability": "8.95%",
      "rec_id": "EBI_N16_06_018"
    },
    {
      "rec_name": "SUB_AUTOPAY",
      "model_type_id": 1,
      "rec_label": "The likelihood of a Comcast subscriber to enroll in AutoPay withwithin the next 90 days.",
      "priority": 1,
      "probability": "7.27%",
      "rec_id": "EBI_N16_04_009"
    },
    {
      "rec_name": "SUB_UPG_DOUBLEPLAY",
      "model_type_id": 3,
      "rec_label": "Likelihood of an existing single product customer to subscribe to Doubleplay (VIDEO/HSD, HSD/VIDEO) within the next 90 days.",
      "priority": 1,
      "probability": "6.31%",
      "rec_id": "EBI_N16_01_019"
    },
    {
      "rec_name": "SUB_UPG_XHOME",
      "model_type_id": 3,
      "rec_label": "Likelihood of a customer to add XFINITY Home (XH) within the next 90 days. HELLO MY NAME IS KEVIN",
      "priority": 2,
      "probability": "5.83%",
      "rec_id": "EBI_N16_12_003"
    },
    {
      "rec_name": "SUB_DELQ_30DAYS",
      "model_type_id": 4,
      "rec_label": "The likelihood of a customer to become delinquent in the next 30 days",
      "priority": 1,
      "probability": "1.21%",
      "rec_id": "EBI_N16_09_007"
    },
    {
      "rec_name": "SUB_TRUCKROLL",
      "model_type_id": 1,
      "rec_label": "Likelihood of a customer to request a truckroll service within the next 90 days.",
      "priority": 1,
      "probability": "0.97%",
      "rec_id": "EBI_N16_06_007"
    }
  ],
  "house_key": " "
}
```

##### *application/json*:
| Name | Type | Description | Required | Pattern |
|:-----|:----:|:------------|:--------:|--------:|
| account_number |  number |  | true |  |
| house_key |  string |  | true |  |
| recs_by_model_type |  boolean |  | true |  |
| recs_available |  integer |  | true |  |
| recs_requested |  integer |  | true |  |
| timestamp |  string |  | true |  |
| recommendations | items array |  | true |  |

items:

| Name | Type | Description | Required | Pattern |
|:-----|:----:|:------------|:--------:|--------:|
| rec_name |  string |  | true |  |
| model_type_id |  integer |  | true |  |
| rec_label |  string |  | true |  |
| priority |  integer |  | true |  |
| probability |  string |  | true |  |
| rec_id |  string |  | true |  |

### Response code: 401

#### application/json (application/json) 

```
{
  "error_message": "Authentication credentials were not provided."
}
```

##### *application/json*:
| Name | Type | Description | Required | Pattern |
|:-----|:----:|:------------|:--------:|--------:|
| error_message |  string |  | true |  |

---

