---
UID: NF:d3dkmthk.D3DKMTPollDisplayChildren
title: D3DKMTPollDisplayChildren function
author: windows-driver-content
description: The D3DKMTPollDisplayChildren function queries for connectivity status of all child devices of the given adapter.
old-location: display\d3dkmtpolldisplaychildren.htm
tech.root: display
ms.assetid: 463831c1-d9b2-404d-91f3-78f495668fdf
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DKMTPollDisplayChildren, D3DKMTPollDisplayChildren function [Display Devices], OpenGL_Functions_dc39afab-758a-423a-9058-9d9ec091d4b2.xml, d3dkmthk/D3DKMTPollDisplayChildren, display.d3dkmtpolldisplaychildren
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
-	D3DKMTPollDisplayChildren
product:
- Windows
targetos: Windows
req.typenames: 
---

# D3DKMTPollDisplayChildren function


## -description


The <b>D3DKMTPollDisplayChildren</b> function queries for connectivity status of all child devices of the given adapter.


## -parameters




### -param D3DKMT_POLLDISPLAYCHILDREN






#### - pData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548161">D3DKMT_POLLDISPLAYCHILDREN</a> structure that describes the parameters for querying for connectivity status of the adapter's child devices.


## -returns



<b>D3DKMTPollDisplayChildren</b> returns one of the following values:

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
Connectivity status was successfully retrieved.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was stopped.

</td>
</tr>
</table>
 

This function might also return other NTSTATUS values.




## -remarks



The OpenGL installable client driver (ICD) calls <b>D3DKMTPollDisplayChildren</b> to query for connectivity status of all of the adapter's child devices. The ICD sets the <b>NonDestructiveOnly</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff548161">D3DKMT_POLLDISPLAYCHILDREN</a> to indicate whether <b>D3DKMTPollDisplayChildren</b> should be destructive (that is, cause visual artifacts). For typical polling, the ICD should set <b>NonDestructiveOnly</b> to <b>TRUE</b> to prevent the screen from flickering.

New child devices are enumerated to the Plug and Play (PnP) manager when PnP detects them. The devices are then listed in the device manager. If PnP determines that a child device was removed, the device is reported as a surprise removal. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548161">D3DKMT_POLLDISPLAYCHILDREN</a>
 

 

