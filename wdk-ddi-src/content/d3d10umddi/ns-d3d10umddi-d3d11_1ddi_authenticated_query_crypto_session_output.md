---
UID: NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_OUTPUT
title: D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_OUTPUT
author: windows-driver-content
description: Contains the response to a QueryAuthenticatedChannel(D3D11_1) query with a D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT.QueryType value of D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION.
old-location: display\d3d11_1ddi_authenticated_query_crypto_session_output.htm
old-project: display
ms.assetid: 3ea5c3e9-44cd-4cf6-be01-4a8c0ce481b0
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 1, 3, A, C, D, D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_OUTPUT, D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_OUTPUT structure [Display Devices], E, H, I, N, O, P, Q, R, S, T, U, Y, _, d3d10umddi/D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_OUTPUT, display.d3d11_1ddi_authenticated_query_crypto_session_output"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d10umddi.h
apiname:
-	D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_OUTPUT
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_OUTPUT
---

# D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_OUTPUT structure


## -description


Contains the response to a <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_queryauthenticatedchannel.md">QueryAuthenticatedChannel(D3D11_1)</a> query with a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_query_output.md">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT</a>.<b>QueryType</b> value of <b>D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION</b>.


## -syntax


````
typedef struct D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_OUTPUT {
  D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT Output;
  HANDLE                                DecodeHandle;
  HANDLE                                CryptoSessionHandle;
  HANDLE                                DeviceHandle;
} D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_OUTPUT;
````


## -struct-fields




### -field Output

A <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_query_output.md">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT</a> structure that contains a Message Authentication Code (MAC) and other data.


### -field DecodeHandle

A handle to a decode device.


### -field CryptoSessionHandle

A handle to the cryptographic session that is associated with the decode device.


### -field DeviceHandle

A handle to the Direct3D device that is associated with the decode device.


## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_query_output.md">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_queryauthenticatedchannel.md">QueryAuthenticatedChannel(D3D11_1)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_OUTPUT structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

