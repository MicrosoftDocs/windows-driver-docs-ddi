---
UID: NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ENCRYPTION_GUID_COUNT_OUTPUT
title: D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ENCRYPTION_GUID_COUNT_OUTPUT (d3d10umddi.h)
description: Contains the response to a QueryAuthenticatedChannel(D3D11_1) query with a D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT.QueryType value of D3D11_1DDI_AUTHENTICATED_QUERY_ENCRYPTION_WHEN_ACCESSIBLE_GUID_COUNT.
old-location: display\d3d11_1ddi_authenticated_query_accessibility_encryption_guid_count_output.htm
ms.assetid: f7d385c6-a9c4-4160-82af-a87c0f60dcdf
ms.date: 05/10/2018
keywords: ["D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ENCRYPTION_GUID_COUNT_OUTPUT structure"]
ms.keywords: D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ENCRYPTION_GUID_COUNT_OUTPUT, D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ENCRYPTION_GUID_COUNT_OUTPUT structure [Display Devices], d3d10umddi/D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ENCRYPTION_GUID_COUNT_OUTPUT, display.d3d11_1ddi_authenticated_query_accessibility_encryption_guid_count_output
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
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ENCRYPTION_GUID_COUNT_OUTPUT
f1_keywords:
 - D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ENCRYPTION_GUID_COUNT_OUTPUT
 - d3d10umddi/D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ENCRYPTION_GUID_COUNT_OUTPUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d10umddi.h
api_name:
 - D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ENCRYPTION_GUID_COUNT_OUTPUT
---

# D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ENCRYPTION_GUID_COUNT_OUTPUT structure


## -description

Contains the response to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_queryauthenticatedchannel">QueryAuthenticatedChannel(D3D11_1)</a> query with a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_output">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT</a>.<b>QueryType</b> value of <b>D3D11_1DDI_AUTHENTICATED_QUERY_ENCRYPTION_WHEN_ACCESSIBLE_GUID_COUNT</b>.

## -struct-fields

### -field Output

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_output">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT</a> structure that contains a Message Authentication Code (MAC) and other data.

### -field EncryptionGuidCount

The number of encryption GUIDs.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_output">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_queryauthenticatedchannel">QueryAuthenticatedChannel(D3D11_1)</a>

