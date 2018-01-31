---
UID: NC:d3d10umddi.PFND3D11_1DDI_FINISHSESSIONKEYREFRESH
title: PFND3D11_1DDI_FINISHSESSIONKEYREFRESH
author: windows-driver-content
description: Completes the switch to a new session key.
old-location: display\finishsessionkeyrefresh1.htm
old-project: display
ms.assetid: 95c0433f-e4da-4566-b128-34cb758b8001
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.finishsessionkeyrefresh1, pfnFinishSessionKeyRefresh callback function [Display Devices], pfnFinishSessionKeyRefresh, PFND3D11_1DDI_FINISHSESSIONKEYREFRESH, PFND3D11_1DDI_FINISHSESSIONKEYREFRESH, d3d10umddi/pfnFinishSessionKeyRefresh
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
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
-	UserDefined
apilocation:
-	D3d10umddi.h
apiname:
-	pfnFinishSessionKeyRefresh
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3D11_1DDI_FINISHSESSIONKEYREFRESH callback


## -description


Completes the switch to a new session key.


## -prototype


````
PFND3D11_1DDI_FINISHSESSIONKEYREFRESH pfnFinishSessionKeyRefresh;

VOID APIENTRY* pfnFinishSessionKeyRefresh(
  _In_ D3D10DDI_HDEVICE          hDevice,
  _In_ D3D11_1DDI_HCRYPTOSESSION hCryptoSession
)
{ ... }
````


## -parameters




#### - hDevice [in]

A handle to the display device (graphics context).




#### - hCryptoSession [in]

A handle to the driver's private data for the cryptographic session. This handle was created by the Direct3D runtime and passed to the driver in the call to <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession.md">CreateCryptoSession</a>.


## -returns


This callback function does not return a value.



## -remarks


<b>FinishSessionKeyRefresh</b> indicates that all buffers from that point in time will use the updated session key value.



## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession.md">CreateCryptoSession</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_FINISHSESSIONKEYREFRESH callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

