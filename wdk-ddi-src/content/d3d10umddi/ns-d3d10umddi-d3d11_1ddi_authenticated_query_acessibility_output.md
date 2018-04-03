---
UID: NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_QUERY_ACESSIBILITY_OUTPUT
title: D3D11_1DDI_AUTHENTICATED_QUERY_ACESSIBILITY_OUTPUT
author: windows-driver-content
description: Contains the response to a QueryAuthenticatedChannel(D3D11_1) query with a D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT.QueryType value of D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ATTRIBUTES.
old-location: display\d3d11_1ddi_authenticated_query_acessibility_output.htm
old-project: display
ms.assetid: 0b32d283-9a5f-4e37-9b03-3c0f5c33c11d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_OUTPUT, D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_OUTPUT structure [Display Devices], D3D11_1DDI_AUTHENTICATED_QUERY_ACESSIBILITY_OUTPUT, D3D11_1DDI_AUTHENTICATED_QUERY_ACESSIBILITY_OUTPUT structure [Display Devices], d3d10umddi/D3D11_1DDI_AUTHENTICATED_QUERY_ACESSIBILITY_OUTPUT, display.d3d11_1ddi_authenticated_query_acessibility_output
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
-	D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_OUTPUT
product:
- Windows
targetos: Windows
req.typenames: D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_OUTPUT
---

# D3D11_1DDI_AUTHENTICATED_QUERY_ACESSIBILITY_OUTPUT structure


## -description


Contains the response to a <a href="https://msdn.microsoft.com/bb152e3d-497f-4798-86cc-6f300e24a05c">QueryAuthenticatedChannel(D3D11_1)</a> query with a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406401">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT</a>.<b>QueryType</b> value of <b>D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ATTRIBUTES</b>.


## -struct-fields




### -field Output

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh406401">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT</a> structure that contains a Message Authentication Code (MAC) and other data.


### -field BusType

A bitwise <b>OR</b> of flags from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406433">D3D11_1DDI_BUS_TYPE</a> enumeration.


### -field AccessibleInContiguousBlocks

If <b>TRUE</b>, contiguous blocks of video memory may be accessible to the CPU or the bus.


### -field AccessibleInNonContiguousBlocks

If <b>TRUE</b>, non-contiguous blocks of video memory may be accessible to the CPU or the bus.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406401">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406433">D3D11_1DDI_BUS_TYPE</a>



<a href="https://msdn.microsoft.com/bb152e3d-497f-4798-86cc-6f300e24a05c">QueryAuthenticatedChannel(D3D11_1)</a>
 

 

