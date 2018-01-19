---
UID: NF:d3dkmthk.D3DKMTReleaseProcessVidPnSourceOwners
title: D3DKMTReleaseProcessVidPnSourceOwners function
author: windows-driver-content
description: The D3DKMTReleaseProcessVidPnSourceOwners function releases the video present network source owners for a process.
old-location: display\d3dkmtreleaseprocessvidpnsourceowners.htm
old-project: display
ms.assetid: 65fa0654-25b5-4ead-ac9e-0eb0f404259a
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTReleaseProcessVidPnSourceOwners
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
req.alt-api: D3DKMTReleaseProcessVidPnSourceOwners
req.alt-loc: Gdi32.dll,API-MS-Win-dx-d3dkmt-l1-1-0.dll,API-MS-Win-dx-d3dkmt-l1-1-1.dll,API-MS-Win-DX-D3DKMT-L1-1-2.dll
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
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTReleaseProcessVidPnSourceOwners function



## -description
The <b>D3DKMTReleaseProcessVidPnSourceOwners</b> function releases the video present network source owners for a process.



## -syntax

````
NTSTATUS APIENTRY D3DKMTReleaseProcessVidPnSourceOwners(
  _In_ HANDLE hProcess
);
````


## -parameters

### -param hProcess [in]

A handle to the process that video present network source owners are released from.


## -returns
<b>D3DKMTReleaseProcessVidPnSourceOwners</b> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The video present network source owners for a process were successfully released.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Parameters were validated and determined to be incorrect.

 

This function might also return other <b>NTSTATUS</b> values.


## -remarks
