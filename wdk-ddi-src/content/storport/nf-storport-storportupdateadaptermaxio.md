---
UID: NF:storport.StorPortUpdateAdapterMaxIO
title: StorPortUpdateAdapterMaxIO function
author: windows-driver-content
description: This function can be called by a miniport to update the maximum IO's supported by an adapter. This function is valid during HwInitialize/HwPassiveInitRoutine callback and has effect only during adapter initialization.
old-location: storage\storportupdateadaptermaxio.htm
old-project: storage
ms.assetid: BB18925D-ACFA-426D-ADD3-33C1D8A99396
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , A, I, M, O, P, S, StorPortUpdateAdapterMaxIO, StorPortUpdateAdapterMaxIO function [Storage Devices], U, a, d, e, o, p, r, storage.storportupdateadaptermaxio, storport/StorPortUpdateAdapterMaxIO, t, x"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10, version 1709.
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Storport.h
apiname:
-	StorPortUpdateAdapterMaxIO
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortUpdateAdapterMaxIO function


## -description


This function can be called by a miniport to update the maximum IO's supported by
    an adapter. This function is valid during HwInitialize/HwPassiveInitRoutine
    callback and has effect only during adapter initialization.


## -syntax


````
ULONG StorPortUpdateAdapterMaxIO(
   PVOID HwDeviceExtension,
   ULONG MaxIoCount
);
````


## -parameters




### -param HwDeviceExtension

A pointer to miniport's device extension.


### -param MaxIoCount

Maximum IO's supported by the adapter.


## -returns



This function returns of the following values.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>STOR_STATUS_SUCCESS</td>
<td>The telemetry event was successfully logged.</td>
</tr>
<tr>
<td>STOR_STATUS_NOT_IMPLEMENTED</td>
<td>The function is called on the OS that does not support it.</td>
</tr>
<tr>
<td>STOR_STATUS_INVALID_PARAMETER</td>
<td>There is an invalid parameter.</td>
</tr>
<tr>
<td>STOR_STATUS_INVALID_DEVICE_REQUEST</td>
<td>The function was called outside of <b>HwInitialize</b>/<b>HwPassiveInitRoutine</b>. </td>
</tr>
</table>
 




## -see-also

<a href="..\storport\ns-storport-_hw_initialization_data.md">HwInitialize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortUpdateAdapterMaxIO function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

