---
UID: NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE_OUTPUT
title: D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE_OUTPUT (d3d10umddi.h)
description: Contains the response to a QueryAuthenticatedChannel(D3D11_1) query with a D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT.QueryType value of D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE.
old-location: display\d3d11_1ddi_authenticated_query_channel_type_output.htm
ms.assetid: 2bdcc511-c176-4f8f-83fe-7a3715b60330
ms.date: 05/10/2018
keywords: ["D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE_OUTPUT structure"]
ms.keywords: D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE_OUTPUT, D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE_OUTPUT structure [Display Devices], d3d10umddi/D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE_OUTPUT, display.d3d11_1ddi_authenticated_query_channel_type_output
f1_keywords:
 - "d3d10umddi/D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE_OUTPUT"
 - "D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE_OUTPUT"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d10umddi.h
api_name:
- D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE_OUTPUT
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE_OUTPUT
---

# D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE_OUTPUT structure


## -description


Contains the response to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_queryauthenticatedchannel">QueryAuthenticatedChannel(D3D11_1)</a> query with a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_output">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT</a>.<b>QueryType</b> value of <b>D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE</b>.


## -struct-fields




### -field Output

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_output">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT</a> structure that contains a Message Authentication Code (MAC) and other data.


### -field ChannelType

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_authenticated_channel_type">D3D11_1DDI_AUTHENTICATED_CHANNEL_TYPE</a> value that specifies the channel type.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_authenticated_channel_type">D3D11_1DDI_AUTHENTICATED_CHANNEL_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_output">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_queryauthenticatedchannel">QueryAuthenticatedChannel(D3D11_1)</a>
 

 

