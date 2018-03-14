---
UID: NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_INPUT
title: D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_INPUT
author: windows-driver-content
description: Contains the response to a QueryAuthenticatedChannel(D3D11_1) query with a D3D11_1DDI_AUTHENTICATED_QUERY_INPUT.QueryType value of D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS.
old-location: display\d3d11_1ddi_authenticated_query_restricted_shared_resource_process_input.htm
old-project: display
ms.assetid: a4b18099-aff8-4709-a040-838e1391cedc
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_INPUT, D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_INPUT structure [Display Devices], d3d10umddi/D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_INPUT, display.d3d11_1ddi_authenticated_query_restricted_shared_resource_process_input
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
-	D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_INPUT
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_INPUT
---

# D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_INPUT structure


## -description


Contains the response to a <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_queryauthenticatedchannel.md">QueryAuthenticatedChannel(D3D11_1)</a> query with a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_query_input.md">D3D11_1DDI_AUTHENTICATED_QUERY_INPUT</a>.<b>QueryType</b> value of <b>D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS</b>.


## -syntax


````
typedef struct D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_INPUT {
  D3D11_1DDI_AUTHENTICATED_QUERY_INPUT Input;
  UINT                                 ProcessIndex;
} D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_INPUT;
````


## -struct-fields




### -field Input

A <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_query_input.md">D3D11_1DDI_AUTHENTICATED_QUERY_INPUT</a> structure that contains the GUID for the query and other data.




### -field ProcessIndex

The index of the process.


## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_queryauthenticatedchannel.md">QueryAuthenticatedChannel(D3D11_1)</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_query_input.md">D3D11_1DDI_AUTHENTICATED_QUERY_INPUT</a>



 

 


