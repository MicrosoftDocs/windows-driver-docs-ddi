---
UID: NF:ks.KsStreamPointerSetStatusCode
title: KsStreamPointerSetStatusCode function
author: windows-driver-content
description: The KsStreamPointerSetStatusCode function allows specification of a successful or unsuccessful error code with which to complete the given IRP.
old-location: stream\ksstreampointersetstatuscode.htm
old-project: stream
ms.assetid: 88d554d9-55b7-42d4-b799-f8cb2029b1ae
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsStreamPointerSetStatusCode, KsStreamPointerSetStatusCode function [Streaming Media Devices], avfunc_48c373d0-2d32-4ad3-b8de-3008e2e11f59.xml, ks/KsStreamPointerSetStatusCode, stream.ksstreampointersetstatuscode
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.lib: Ks.lib
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsStreamPointerSetStatusCode
product: Windows
targetos: Windows
req.typenames: 
---

# KsStreamPointerSetStatusCode function


## -description


The<b> KsStreamPointerSetStatusCode</b> function allows specification of a successful or unsuccessful error code with which to complete the given IRP.


## -parameters




### -param StreamPointer [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff567139">KSSTREAM_POINTER</a> structure. This pointer points to the frame contained in the IRP.


### -param Status [in]

The error code with which to complete the IRP.


## -returns



<b>KsStreamPointerSetStatusCode</b> returns STATUS_SUCCESS if the IRP is completed with the requested status code. Otherwise, it returns an appropriate error code.




## -remarks



Note that the IRP contains the frame to which <i>StreamPointer</i> points.

Also see <a href="https://msdn.microsoft.com/4bac68a0-34d2-431a-9ed9-8a42751a736f">Stream Pointers</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563535">KSPIN_DISPATCH</a>
 

 

