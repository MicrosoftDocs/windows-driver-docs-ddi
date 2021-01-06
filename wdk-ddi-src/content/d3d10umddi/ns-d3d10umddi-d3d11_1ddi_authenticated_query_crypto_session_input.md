---
UID: NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_INPUT
title: D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_INPUT (d3d10umddi.h)
description: Contains the response to a QueryAuthenticatedChannel(D3D11_1) query with a D3D11_1DDI_AUTHENTICATED_QUERY_INPUT.QueryType value of D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION.
old-location: display\d3d11_1ddi_authenticated_query_crypto_session_input.htm
ms.date: 05/10/2018
keywords: ["D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_INPUT structure"]
ms.keywords: D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_INPUT, D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_INPUT structure [Display Devices], d3d10umddi/D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_INPUT, display.d3d11_1ddi_authenticated_query_crypto_session_input
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
req.typenames: D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_INPUT
f1_keywords:
 - D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_INPUT
 - d3d10umddi/D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_INPUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d10umddi.h
api_name:
 - D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_INPUT
---

# D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_INPUT structure


## -description

Contains the response to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_queryauthenticatedchannel">QueryAuthenticatedChannel(D3D11_1)</a> query with a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_input">D3D11_1DDI_AUTHENTICATED_QUERY_INPUT</a>.<b>QueryType</b> value of <b>D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION</b>.

## -struct-fields

### -field Input

A <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_input">D3D11_1DDI_AUTHENTICATED_QUERY_INPUT</a> structure that contains the GUID for the query and other data.

### -field DecodeHandle

A handle to a decode device.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_authenticated_query_input">D3D11_1DDI_AUTHENTICATED_QUERY_INPUT</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_queryauthenticatedchannel">QueryAuthenticatedChannel(D3D11_1)</a>
