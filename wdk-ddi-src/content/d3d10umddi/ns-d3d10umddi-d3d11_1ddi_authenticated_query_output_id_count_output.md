---
UID: NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID_COUNT_OUTPUT
title: D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID_COUNT_OUTPUT (d3d10umddi.h)
description: Contains the response to a QueryAuthenticatedChannel(D3D11_1) query with a D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT.QueryType value of D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID_COUNT.
old-location: display\d3d11_1ddi_authenticated_query_output_id_count_output.htm
ms.assetid: 21225f0e-5ab4-48fb-90d2-cb9cbd81b7c2
ms.date: 05/10/2018
ms.keywords: D3D11_1DDI_AUTHENTICATED_CHANNEL_QUERY_OUTPUT_ID_COUNT_OUTPUT, D3D11_1DDI_AUTHENTICATED_CHANNEL_QUERY_OUTPUT_ID_COUNT_OUTPUT structure [Display Devices], D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID_COUNT_OUTPUT, D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID_COUNT_OUTPUT structure [Display Devices], d3d10umddi/D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID_COUNT_OUTPUT, display.d3d11_1ddi_authenticated_query_output_id_count_output
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d10umddi.h
api_name:
- D3D11_1DDI_AUTHENTICATED_CHANNEL_QUERY_OUTPUT_ID_COUNT_OUTPUT
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_AUTHENTICATED_CHANNEL_QUERY_OUTPUT_ID_COUNT_OUTPUT
---

# D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID_COUNT_OUTPUT structure


## -description


Contains the response to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_queryauthenticatedchannel">QueryAuthenticatedChannel(D3D11_1)</a> query with a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_output">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT</a>.<b>QueryType</b> value of <b>D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID_COUNT</b>.TBDD3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID_COUNT


## -struct-fields




### -field Output

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_output">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT</a> structure that contains a Message Authentication Code (MAC) and other data.


### -field DeviceHandle

A handle to the device.




### -field CryptoSessionHandle

A handle to the cryptographic session.


### -field OutputIDCount

The number of output IDs associated with the specified device and cryptographic session.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_output">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_queryauthenticatedchannel">QueryAuthenticatedChannel(D3D11_1)</a>
 

 

