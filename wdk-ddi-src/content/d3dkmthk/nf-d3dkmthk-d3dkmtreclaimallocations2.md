---
UID: NF:d3dkmthk.D3DKMTReclaimAllocations2
title: D3DKMTReclaimAllocations2 function
author: windows-driver-content
description: D3DKMTReclaimAllocations2 reclaims video memory allocations.
old-location: display\d3dkmtreclaimallocations2.htm
old-project: display
ms.assetid: 0BC49546-ECDE-447D-8F7E-4235D96D293B
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTReclaimAllocations2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMTReclaimAllocations2
req.alt-loc: GDI32.dll,API-MS-Win-DX-D3DKMT-L1-1-1.dll,GDI32.dll,API-MS-Win-DX-D3DKMT-L1-1-2.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Gdi32.lib
req.dll: GDI32.dll
req.irql: 
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTReclaimAllocations2 function



## -description
<b>D3DKMTReclaimAllocations2</b> reclaims video memory allocations.



## -syntax

````
EXTERN_C _Check_return_ NTSTATUS APIENTRY D3DKMTReclaimAllocations2(
  _Inout_ D3DKMT_RECLAIMALLOCATIONS2 *pData
);
````


## -parameters

### -param pData [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_reclaimallocations2.md">D3DKMT_RECLAIMALLOCATIONS2</a> structure that defines memory allocations to reclaim.


## -returns
Returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The allocations were successfully reclaimed.

<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>The graphics adapter was stopped or the display device was reset.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Parameters were validated and determined to be incorrect.

 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_reclaimallocations2.md">D3DKMT_RECLAIMALLOCATIONS2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTReclaimAllocations2 function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

