---
title: "Get cloudPCs"
description: "View the properties and relationships of a cloudPC object."
author: "jiajyang"
localization_priority: Normal
ms.prod: "microsoft_cloudpc"
doc_type: apiPageType
---

# Get cloudPCs

Namespace: microsoft.graph

View the properties and relationships of a specific [cloudPC](../resources/cloudpc.md) object.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from most to least privileged)|
|:---|:---|
|Delegated (work or school account)|CloudPC.ReadWrite.All,CloudPC.Read.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|Not supported.|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->

``` http
GET /deviceManagement/virtualEndpoint/cloudPCs/{id}
```

## Optional query parameters

This method supports some of the OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body

Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a [cloudPC](../resources/cloudpc.md) object in the response body.

## Examples

### Request

<!-- {
  "blockType": "request",
  "name": "get_cloudpc"
}
-->

``` http
GET https://graph.microsoft.com/beta/deviceManagement/virtualEndpoint/cloudPCs/{id}
```

### Response

**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "name": "get_cloudpc",
  "@odata.type": "microsoft.graph.cloudPC"
}
-->

``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": {
    "@odata.type": "#microsoft.graph.cloudPC",
    "id": "ac74ae8b-85f7-4272-88cc-5419267403ed",
    "displayName": "Demo-1",
    "imageDisplayName": "Custom image name",
    "managedDeviceId": "e87f50c7-fa7f-4687-aade-dd45f3d65970",  
    "managedDeviceName": "A00001D3000",
    "provisioningPolicyId": "13fa0778-ba00-438a-96d3-488c86029dff",
    "servicePlanId": "da5615b4-a484-4742-a019-2d52c91cbfd0",
    "servicePlanName": "standard",
    "status": "failed",
    "statusDetails": {
    "code": "internalServerError",
    "message": "There was an internal server error. Please contact support xxx.",
    "additionalInformation": [
        {
          "@odata.type": "microsoft.graph.keyValuePair",
          "name": "correlationId",
          "value": "52367774-cfb7-4e9c-ab51-1b864c31f2d1"
        }
      ]
    },
    "userPrincipalName": "mrichard@cpccustomer001.onmicrosoft.com",
    "lastModifiedDateTime": "2020-07-28T18:14:34Z"
  }
}
```