---
UID: NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID_INPUT
title: D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID_INPUT
author: windows-driver-content
description: Contains the response to a QueryAuthenticatedChannel(D3D11_1) query with a D3D11_1DDI_AUTHENTICATED_QUERY_INPUT.QueryType value of D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID.
old-location: display\d3d11_1ddi_authenticated_query_output_id_input.htm
ms.assetid: 7dd6da58-0105-4374-be01-58729f095d01
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID_INPUT, D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID_INPUT structure [Display Devices], d3d10umddi/D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID_INPUT, display.d3d11_1ddi_authenticated_query_output_id_input
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
-	D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID_INPUT
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID_INPUT
---

# D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID_INPUT structure


## -description


Contains the response to a <a href="https://msdn.microsoft.com/bb152e3d-497f-4798-86cc-6f300e24a05c">QueryAuthenticatedChannel(D3D11_1)</a> query with a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406399">D3D11_1DDI_AUTHENTICATED_QUERY_INPUT</a>.<b>QueryType</b> value of <b>D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID</b>.


## -struct-fields




### -field Input

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh406399">D3D11_1DDI_AUTHENTICATED_QUERY_INPUT</a> structure that contains the GUID for the query and other data.


### -field DeviceHandle

A handle to the device.




### -field CryptoSessionHandle

A handle to the cryptographic session.


### -field OutputIDIndex

The index of the output ID.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406399">D3D11_1DDI_AUTHENTICATED_QUERY_INPUT</a>



<a href="https://msdn.microsoft.com/bb152e3d-497f-4798-86cc-6f300e24a05c">QueryAuthenticatedChannel(D3D11_1)</a>
 

 

