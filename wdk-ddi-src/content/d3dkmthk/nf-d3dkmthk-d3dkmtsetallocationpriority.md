---
UID: NF:d3dkmthk.D3DKMTSetAllocationPriority
title: D3DKMTSetAllocationPriority function
author: windows-driver-content
description: The D3DKMTSetAllocationPriority function sets the priority level of a resource or list of allocations.
old-location: display\d3dkmtsetallocationpriority.htm
old-project: display
ms.assetid: d5ad6288-6123-4665-a48e-bbae856cc160
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTSetAllocationPriority
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
req.alt-api: D3DKMTSetAllocationPriority
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

# D3DKMTSetAllocationPriority function



## -description
The <b>D3DKMTSetAllocationPriority</b> function sets the priority level of a resource or list of allocations.



## -syntax

````
NTSTATUS APIENTRY D3DKMTSetAllocationPriority(
  _In_ const D3DKMT_SETALLOCATIONPRIORITY *pData
);
````


## -parameters

### -param pData [in]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_setallocationpriority.md">D3DKMT_SETALLOCATIONPRIORITY</a> structure that contains information for setting the priority level of a resource or list of allocations.


## -returns
<b>D3DKMTSetAllocationPriority</b> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>Priority level for allocations was successfully set.
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>The graphics adapter was stopped or the display device was reset.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Parameters were validated and determined to be incorrect.

 

This function might also return other NTSTATUS values.


## -remarks
The following code example demonstrates how an OpenGL ICD can use <b>D3DKMTSetAllocationPriority</b> to set the priority level of a resource (and therefore all of the allocations that are associated with the resource).


## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_setallocationpriority.md">D3DKMT_SETALLOCATIONPRIORITY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTSetAllocationPriority function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

