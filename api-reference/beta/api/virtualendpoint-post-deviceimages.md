---
title: "Create deviceImages"
description: "Upload a custom OS image that you can later provision on Cloud PCs."
author: "jiajyang"
localization_priority: Normal
ms.prod: "microsoft_cloudpc"
doc_type: apiPageType
---

# Create deviceImages

Namespace: microsoft.graph

Upload a custom OS image that you can later provision on Cloud PCs.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from most to least privileged)|
|:---|:---|
|Delegated (work or school account)|CloudPC.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|Not supported.|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->

``` http
POST /deviceManagement/virtualEndpoint/deviceImages
```

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body

In the request body, supply a JSON representation of the [cloudPcDeviceImage](../resources/cloudpcdeviceimage.md) object.

The following table shows the properties that are required when you create the [cloudPcDeviceImage](../resources/cloudpcdeviceimage.md).

|Property|Type|Description|
|:---|:---|:---|
|id|String|The ID of the image resource on Cloud PC.This property is read-only.|
|displayName|String|The image's display name.|
|sourceImageResourceId|String|The ID of the source image resource on Azure. Required format: "/subscriptions/{subscription-id}/resourceGroups/{resourceGroupName}/providers/Microsoft.Compute/images/{imageName}".|
|operatingSystem|String|The image's operating system. For example: Windows 10 Enterprise.|
|osBuildNumber|String|The image's OS build version. For example: 1909.|
|version|String|The image version. For example: 0.0.1, 1.5.13.|

## Response

If successful, this method returns a `201 Created` response code and a [cloudPcDeviceImage](../resources/cloudpcdeviceimage.md) object in the response body.

## Examples

### Request

<!-- {
  "blockType": "request",
  "name": "create_cloudpcdeviceimage_from_cloudpcdeviceimage"
}
-->

``` http
POST https://graph.microsoft.com/beta/deviceManagement/virtualEndpoint/deviceImages
Content-Type: application/json
Content-length: 235

{
  "@odata.type": "#microsoft.graph.cloudPcDeviceImage",
  "displayName": "graph",
  "osBuildNumber": "1902",
  "operatingSystem": "Windows 10 Enterprise",
  "version": "2.3.5",
  "sourceImageResourceId": "/subscriptions/0ac520ee-14c0-480f-b6c9-0a90c585ad47/resourceGroups/SIGTEST/providers/Microsoft.Compute/images/imagefordemo"
}
```

### Response

**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.cloudPcDeviceImage"
}
-->

``` http
HTTP/1.1 201 Created
Content-Type: application/json

{
  "@odata.type": "#microsoft.graph.cloudPcDeviceImage",
  "id": "eda7ed64-7705-4079-9d08-c2bd883f4cfc",
  "displayName": "graph",
  "osBuildNumber": "1902",
  "operatingSystem": "Windows 10 Enterprise",
  "version": "2.3.5",
  "sourceImageResourceId": "/subscriptions/0ac520ee-14c0-480f-b6c9-0a90c585ad47/resourceGroups/SIGTEST/providers/Microsoft.Compute/images/imagefordemo",
  "lastModifiedDateTime": "2020-07-21T07:03:44.97Z",
  "status": "pending",
  "statusDetails": null
}
```