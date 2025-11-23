## BigQuery API

A data platform for customers to create, manage, and share query data.

## Base URL

[<code>bigquery.googleapis.com/bigquery/v1</code>](https://bigquery.googleapis.com/bigquery/v2)

## Authorization

Authorization: Bearer {{access_token}}

Content-Type: application/json

### OAuth scopes (examples):

- `https://www.googleapis.com/auth/bigquery`
    
- `https://www.googleapis.com/auth/cloud-platform`

## Get a list of datasets

## **HTTP Request**

GET

### **Endpoint Path**

GET /v1/projects/{projectId}/datasets

**URL**: `/[https://bigquery.googleapis.com/bigquery/v2/projects/{{projectId}}/datasets]`  
Replace `{{projectId}}` with your project ID (example: `bigquery-api-docs-001`).

## Description

Lists all datasets in the specified project to which you have been granted the READER dataset role.

## Authentication

Authorization: Bearer {{access_token}}

Content-Type: application/json

Requires the following OAuth scopes:

- `https://www.googleapis.com/auth/bigquery`
    
- `https://www.googleapis.com/auth/cloud-platform`
    

## Path Parameters

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| ProjectId | string | Yes | Google Cloud Project ID (example: `bigquery-api-docs-001`). |

## HTTP Status Codes

**200 OK** - Request succeeded

Returns a list of datasets.

``` json
{
  "datasets": [
    {
      "datasetReference": {
        "datasetId": "string",
        "projectId": "string"
      },
      "friendlyName": "string",
      "id": "string",
      "kind": "bigquery#dataset",
      "labels": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
      },
      "location": "string"
    }
  ],
  "etag": "string",
  "kind": "bigquery#datasetList",
  "nextPageToken": "string"
}

 ```

## Error Responses

| Code | Meaning | Fix |
| --- | --- | --- |
| 401 Unauthorized | Missing/expired/invalid token | Pass a valid Bearer token |
| 403 Forbidden | Token lacks BigQuery permissions | Give SA/Account `/roles/bigquery.user` |
| 404 Not Found | Invalid projectId or access denied | Check projectId or permissions |

## Create a dataset

## **HTTP Request**

POST

### **Endpoint Path**

POST /v1/projects/{projectId}/datasets

**URL**: `/[https://bigquery.googleapis.com/bigquery/v2/projects/{{projectId}}/datasets]`  
Replace `{{projectId}}` with your project ID (example: `bigquery-api-docs-001`).

## Description

Create a new empty dataset.

## Authentication

Authorization: Bearer {{access_token}}

Content-Type: application/json

Requires the following OAuth scopes:

- `https://www.googleapis.com/auth/bigquery`
    
- `https://www.googleapis.com/auth/cloud-platform`
    

## Path Parameters

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| ProjectId | string | Yes | Google Cloud Project ID related to the dataset you want to create. |

## Request Body

``` json
{
  "access": [
    {
      "dataset": {
        "dataset": {
          "datasetId": "string",
          "projectId": "string"
        },
        "targetTypes": [
          "TARGET_TYPE_UNSPECIFIED"
        ]
      },
      "domain": "string",
      "groupByEmail": "string",
      "iamMember": "string",
      "role": "string",
      "routine": {
        "datasetId": "string",
        "projectId": "string",
        "routineId": "string"
      },
      "specialGroup": "string",
      "userByEmail": "string",
      "view": {
        "datasetId": "string",
        "projectId": "string",
        "tableId": "string"
      }
    }
  ],
  "creationTime": "string",
  "datasetReference": {
    "datasetId": "string",
    "projectId": "string"
  },
  "defaultCollation": "string",
  "defaultEncryptionConfiguration": {
    "kmsKeyName": "string"
  },
  "defaultPartitionExpirationMs": "string",
  "defaultRoundingMode": "string",
  "defaultTableExpirationMs": "string",
  "description": "string",
  "etag": "string",
  "friendlyName": "string",
  "id": "string",
  "isCaseInsensitive": true,
  "kind": "bigquery#dataset",
  "labels": {
    "additionalProp1": "string",
    "additionalProp2": "string",
    "additionalProp3": "string"
  },
  "lastModifiedTime": "string",
  "location": "string",
  "maxTimeTravelHours": "string",
  "satisfiesPzs": true,
  "selfLink": "string",
  "storageBillingModel": "string",
  "tags": [
    {
      "tagKey": "string",
      "tagValue": "string"
    }
  ]
}

 ```

### Fields

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| datasetReference.datasetId | string | Yes | Unique dataset name. |
| datasetReference.projectId | string | Yes | Google Cloud Project ID. |

### Example Request Body

``` json
{
  "datasetReference": {
    "datasetId": "{{datasetId}}",
    "projectId": "{{projectId}}"
  },
  "location": "{{location}}"
}

 ```

## HTTP Status Code

**200 OK** - Request succeeded

Returns a list of datasets.

``` json
{
  "access": [
    {
      "dataset": {
        "dataset": {
          "datasetId": "string",
          "projectId": "string"
        },
        "targetTypes": [
          "TARGET_TYPE_UNSPECIFIED"
        ]
      },
      "domain": "string",
      "groupByEmail": "string",
      "iamMember": "string",
      "role": "string",
      "routine": {
        "datasetId": "string",
        "projectId": "string",
        "routineId": "string"
      },
      "specialGroup": "string",
      "userByEmail": "string",
      "view": {
        "datasetId": "string",
        "projectId": "string",
        "tableId": "string"
      }
    }
  ],
  "creationTime": "string",
  "datasetReference": {
    "datasetId": "string",
    "projectId": "string"
  },
  "defaultCollation": "string",
  "defaultEncryptionConfiguration": {
    "kmsKeyName": "string"
  },
  "defaultPartitionExpirationMs": "string",
  "defaultRoundingMode": "string",
  "defaultTableExpirationMs": "string",
  "description": "string",
  "etag": "string",
  "friendlyName": "string",
  "id": "string",
  "isCaseInsensitive": true,
  "kind": "bigquery#dataset",
  "labels": {
    "additionalProp1": "string",
    "additionalProp2": "string",
    "additionalProp3": "string"
  },
  "lastModifiedTime": "string",
  "location": "string",
  "maxTimeTravelHours": "string",
  "satisfiesPzs": true,
  "selfLink": "string",
  "storageBillingModel": "string",
  "tags": [
    {
      "tagKey": "string",
      "tagValue": "string"
    }
  ]
}

 ```

## Error Responses

| Code | Meaning | Fix |
| --- | --- | --- |
| 400 Bad Request | Missing datasetId or invalid name | Use valid characters; length ≤ 1024 |
| 401 Unauthorized | Missing/expired/invalid token | Use a valid Bearer token |
| 403 Forbidden | Token lacks BigQuery permissions | Grant `roles/bigquery.admin` or `/roles/bigquery.user` |
| 409 Conflict | Dataset already exists | Use a different datasetId |

## Delete a dataset

## **HTTP Request**

DELETE

### **Endpoint Path**

DELETE /v1/projects/{projectId}/datasets/{datasetId}

**URL**: `/[https://bigquery.googleapis.com/bigquery/v2/projects/{{projectId}}/datasets/{{datasetId}}]`  
Replace `{{projectId}}` with your project ID (example: `bigquery-api-docs-001`).

Replace `{{datasetId}}` with your dataset ID.

## Description

Delete a dataset specified in the datasetId value.

## Authentication

Authorization: Bearer {{access_token}}

Content-Type: application/json

Requires the following OAuth scopes:

- `https://www.googleapis.com/auth/bigquery`
    
- `https://www.googleapis.com/auth/cloud-platform`
    

## Path Parameters

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| `projectId` | string | Yes | ID of the Google Cloud Project related to the dataset you want to delete. |
| `datasetId` | string | Yes | The name of the dataset you want to delete. |

## Query Parameters

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| `deleteContents` | string | Optional | If 'true', deletes all tables inside the dataset before deleting the dataset. |

## HTTP Status Code

**204 OK** - Dataset deleted successfully

## Update the fields of a dataset

## **HTTP Request**

PATCH

### **Endpoint Path**

PATCH /v1/projects/{projectId}/datasets/{datasetId}

**URL**: `/[https://bigquery.googleapis.com/bigquery/v2/projects/{{projectId}}/datasets{datasetId}}]`  
Replace `{{projectId}}` with your project ID (example: `bigquery-api-docs-001`).

Replace `{{datasetId}}` with your dataset ID.

## Description

Update the fields of an exisitng dataset using patch semantics.

## Authentication

Authorization: Bearer {{access_token}}

Content-Type: application/json

Requires the following OAuth scopes:

- `https://www.googleapis.com/auth/bigquery`
    
- `https://www.googleapis.com/auth/cloud-platform`
    

## Path Parameters

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| projectId | string | Yes | Google Cloud Project ID related to the dataset you want to create. |
| datasetId | string | Yes | The dataset you want to update. |

## Request Body

Include the fields you want to update.

``` json
{
  "access": [
    {
      "dataset": {
        "dataset": {
          "datasetId": "string",
          "projectId": "string"
        },
        "targetTypes": [
          "TARGET_TYPE_UNSPECIFIED"
        ]
      },
      "domain": "string",
      "groupByEmail": "string",
      "iamMember": "string",
      "role": "string",
      "routine": {
        "datasetId": "string",
        "projectId": "string",
        "routineId": "string"
      },
      "specialGroup": "string",
      "userByEmail": "string",
      "view": {
        "datasetId": "string",
        "projectId": "string",
        "tableId": "string"
      }
    }
  ],
  "creationTime": "string",
  "datasetReference": {
    "datasetId": "string",
    "projectId": "string"
  },
  "defaultCollation": "string",
  "defaultEncryptionConfiguration": {
    "kmsKeyName": "string"
  },
  "defaultPartitionExpirationMs": "string",
  "defaultRoundingMode": "string",
  "defaultTableExpirationMs": "string",
  "description": "string",
  "etag": "string",
  "friendlyName": "string",
  "id": "string",
  "isCaseInsensitive": true,
  "kind": "bigquery#dataset",
  "labels": {
    "additionalProp1": "string",
    "additionalProp2": "string",
    "additionalProp3": "string"
  },
  "lastModifiedTime": "string",
  "location": "string",
  "maxTimeTravelHours": "string",
  "satisfiesPzs": true,
  "selfLink": "string",
  "storageBillingModel": "string",
  "tags": [
    {
      "tagKey": "string",
      "tagValue": "string"
    }
  ]
}

 ```

## HTTP Status Code

**200 OK** - Request succeeded

Returns the updated dataset metadata.

## Error Responses

| Code | Meaning | Fix |
| --- | --- | --- |
| 400 Bad Request | Invalid field or value | Check request body fields |
| 401 Unauthorized | Missing/expired/invalid token | Use a valid Bearer token |
| 403 Forbidden | Token lacks BigQuery permissions | Grant `roles/bigquery.admin` or `/roles/bigquery.user` |
| 409 Conflict | Dataset doesn't exist | Verify datasetId |

## Replace all fields of a dataset

## **HTTP Request**

PUT

### **Endpoint Path**

PUT /v1/projects/{projectId}/datasets/{datasetId}

**URL**: `/[https://bigquery.googleapis.com/bigquery/v2/projects/{{projectId}}/datasets/{{datasetId}}]`  
Replace `{{projectId}}` with your project ID (example: `bigquery-api-docs-001`).

Replace `{{datasetId}}` with your dataset ID.

## Description

Complelely replace all the fields of an exisiting dataset.

## Authentication

Authorization: Bearer {{access_token}}

Content-Type: application/json

Requires the following OAuth scopes:

- `https://www.googleapis.com/auth/bigquery`
    
- `https://www.googleapis.com/auth/cloud-platform`
    

## Path Parameters

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| projectId | string | Yes | Google Cloud Project ID related to the dataset you want to create. |
| datasetId | string | Yes | The dataset you want to update. |

## Request Body

Include all the fields you want to include in the dataset. If a field is omitted, it is removed.

``` json
{
  "access": [
    {
      "dataset": {
        "dataset": {
          "datasetId": "string",
          "projectId": "string"
        },
        "targetTypes": [
          "TARGET_TYPE_UNSPECIFIED"
        ]
      },
      "domain": "string",
      "groupByEmail": "string",
      "iamMember": "string",
      "role": "string",
      "routine": {
        "datasetId": "string",
        "projectId": "string",
        "routineId": "string"
      },
      "specialGroup": "string",
      "userByEmail": "string",
      "view": {
        "datasetId": "string",
        "projectId": "string",
        "tableId": "string"
      }
    }
  ],
  "creationTime": "string",
  "datasetReference": {
    "datasetId": "string",
    "projectId": "string"
  },
  "defaultCollation": "string",
  "defaultEncryptionConfiguration": {
    "kmsKeyName": "string"
  },
  "defaultPartitionExpirationMs": "string",
  "defaultRoundingMode": "string",
  "defaultTableExpirationMs": "string",
  "description": "string",
  "etag": "string",
  "friendlyName": "string",
  "id": "string",
  "isCaseInsensitive": true,
  "kind": "bigquery#dataset",
  "labels": {
    "additionalProp1": "string",
    "additionalProp2": "string",
    "additionalProp3": "string"
  },
  "lastModifiedTime": "string",
  "location": "string",
  "maxTimeTravelHours": "string",
  "satisfiesPzs": true,
  "selfLink": "string",
  "storageBillingModel": "string",
  "tags": [
    {
      "tagKey": "string",
      "tagValue": "string"
    }
  ]
}

 ```

## HTTP Status Code

**200 OK** - Request succeeded

Returns the updated dataset metadata.

## Error Responses

| Code | Meaning | Fix |
| --- | --- | --- |
| 400 Bad Request | Invalid field or value | Check request body fields |
| 401 Unauthorized | Missing/expired/invalid token | Use a valid Bearer token |
| 403 Forbidden | Token lacks BigQuery permissions | Grant `roles/bigquery.admin` or `/roles/bigquery.user` |
| 409 Conflict | Dataset doesn't exist | Verify `datasetId` |
