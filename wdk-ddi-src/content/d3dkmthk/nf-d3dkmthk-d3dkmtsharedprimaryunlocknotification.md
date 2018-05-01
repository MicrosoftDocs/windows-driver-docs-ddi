---
UID: NF:d3dkmthk.D3DKMTSharedPrimaryUnLockNotification
title: D3DKMTSharedPrimaryUnLockNotification function
author: windows-driver-content
description: The D3DKMTSharedPrimaryUnLockNotification function notifies the operating system that a shared primary surface was unlocked.
old-location: display\d3dkmtsharedprimaryunlocknotification.htm
old-project: display
ms.assetid: 1d602d09-cd80-4079-9132-1caced4d1eee
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DKMTSharedPrimaryUnLockNotification, D3DKMTSharedPrimaryUnLockNotification function [Display Devices], OpenGL_Functions_311a1879-e3f7-44e2-aa1a-0c070e45bf85.xml, d3dkmthk/D3DKMTSharedPrimaryUnLockNotification, display.d3dkmtsharedprimaryunlocknotification
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Gdi32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTSharedPrimaryUnLockNotification
product: Windows
targetos: Windows
req.typenames: 
---

# D3DKMTSharedPrimaryUnLockNotification function


## -description


The <b>D3DKMTSharedPrimaryUnLockNotification</b> function notifies the operating system that a shared primary surface was unlocked.


## -parameters




### -param D3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION

TBD




#### - pData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548344">D3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION</a> structure that describes the shared primary surface that was unlocked.


## -returns



<b>D3DKMTSharedPrimaryUnLockNotification</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
Notification about unlocking a shared primary surface was successfully performed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
</table>
 

This function might also return other NTSTATUS values.




## -remarks



The OpenGL ICD calls the <b>D3DKMTSharedPrimaryUnLockNotification</b> function to inform the operating system that an application just unlocked the GDI shared primary surface that exists on the graphics adapter and video present source that the <b>AdapterLuid</b> and <b>VidPnSourceId</b> members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548344">D3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION</a> structure specify. The OpenGL ICD should call <b>D3DKMTSharedPrimaryUnLockNotification</b> after it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547233">D3DKMTUnlock</a> function to unlock the GDI shared primary surface.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547233">D3DKMTUnlock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548344">D3DKMT_SHAREDPRIMARYUNLOCKNOTIFICATION</a>
 

 

