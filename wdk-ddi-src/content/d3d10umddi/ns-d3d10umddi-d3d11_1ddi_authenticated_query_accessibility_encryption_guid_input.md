---
UID: NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ENCRYPTION_GUID_INPUT
title: D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ENCRYPTION_GUID_INPUT
author: windows-driver-content
description: Contains the response to a QueryAuthenticatedChannel(D3D11_1) query with a D3D11_1DDI_AUTHENTICATED_QUERY_INPUT.QueryType value of D3D11_1DDI_AUTHENTICATED_CONFIGURE_ENCRYPTION_WHEN_ACCESSIBLE_GUID.
old-location: display\d3d11_1ddi_authenticated_query_accessibility_encryption_guid_input.htm
old-project: display
ms.assetid: 919ca017-aa00-4a11-9847-37cb50abb412
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ENCRYPTION_GUID_INPUT, D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ENCRYPTION_GUID_INPUT structure [Display Devices], d3d10umddi/D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ENCRYPTION_GUID_INPUT, display.d3d11_1ddi_authenticated_query_accessibility_encryption_guid_input
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ENCRYPTION_GUID_INPUT
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ENCRYPTION_GUID_INPUT
---

# D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ENCRYPTION_GUID_INPUT structure


## -description


Contains the response to a <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_queryauthenticatedchannel.md">QueryAuthenticatedChannel(D3D11_1)</a> query with a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_query_input.md">D3D11_1DDI_AUTHENTICATED_QUERY_INPUT</a>.<b>QueryType</b> value of <b>D3D11_1DDI_AUTHENTICATED_CONFIGURE_ENCRYPTION_WHEN_ACCESSIBLE_GUID</b>.


## -syntax


````
typedef struct D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ENCRYPTION_GUID_INPUT {
  D3D11_1DDI_AUTHENTICATED_QUERY_INPUT Input;
  UINT                                 EncryptionGuidIndex;
} D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ENCRYPTION_GUID_INPUT;
````


## -struct-fields




### -field Input

A <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_query_input.md">D3D11_1DDI_AUTHENTICATED_QUERY_INPUT</a> structure that contains the GUID for the query and other data.


### -field EncryptionGuidIndex

The index of the encryption GUID. 




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_queryauthenticatedchannel.md">QueryAuthenticatedChannel(D3D11_1)</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_query_input.md">D3D11_1DDI_AUTHENTICATED_QUERY_INPUT</a>



 

 


