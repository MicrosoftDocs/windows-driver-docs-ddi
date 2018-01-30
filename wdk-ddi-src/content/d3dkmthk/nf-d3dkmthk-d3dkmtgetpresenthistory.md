---
UID: NF:d3dkmthk.D3DKMTGetPresentHistory
title: D3DKMTGetPresentHistory function
author: windows-driver-content
description: The D3DKMTGetPresentHistory function retrieves copying history.
old-location: display\d3dkmtgetpresenthistory.htm
old-project: display
ms.assetid: e00af04e-4770-4505-a06c-c44405dcaab5
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dkmtgetpresenthistory, D3DKMTGetPresentHistory function [Display Devices], d3dkmthk/D3DKMTGetPresentHistory, OpenGL_Functions_9070e169-207c-478d-8eab-b0bcfad65362.xml, D3DKMTGetPresentHistory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Gdi32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
apiname:
-	D3DKMTGetPresentHistory
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTGetPresentHistory function


## -description


The <b>D3DKMTGetPresentHistory</b> function retrieves copying history.


## -syntax


````
NTSTATUS D3DKMTGetPresentHistory(
  _Inout_ D3DKMT_GETPRESENTHISTORY *pData
);
````


## -parameters





#### - pData [in, out]

Supplies a pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_getpresenthistory.md">D3DKMT_GETPRESENTHISTORY</a> structure that describes the copying history.


## -returns


Returns <b>STATUS_SUCCESS</b> if copying history is successfully retrieved; otherwise an appropriate error code.



## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_getpresenthistory.md">D3DKMT_GETPRESENTHISTORY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTGetPresentHistory function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

