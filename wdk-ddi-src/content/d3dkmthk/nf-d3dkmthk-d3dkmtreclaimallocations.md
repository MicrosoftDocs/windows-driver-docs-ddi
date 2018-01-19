---
UID: NF:d3dkmthk.D3DKMTReclaimAllocations
title: D3DKMTReclaimAllocations function
author: windows-driver-content
description: Reclaims video memory allocations.
old-location: display\d3dkmtreclaimallocations.htm
old-project: display
ms.assetid: 3bfb2a82-9451-4365-b113-6311c3f13fe6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTReclaimAllocations
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMTReclaimAllocations
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

# D3DKMTReclaimAllocations function



## -description
Reclaims video memory allocations.



## -syntax

````
EXTERN_C _Check_return_ NTSTATUS APIENTRY D3DKMTReclaimAllocations(
  _Inout_ const D3DKMT_RECLAIMALLOCATIONS *pData
);
````


## -parameters

### -param pData [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_reclaimallocations.md">D3DKMT_RECLAIMALLOCATIONS</a> structure that defines memory allocations to reclaim.


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
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_reclaimallocations.md">D3DKMT_RECLAIMALLOCATIONS</a>
</dt>
<dt>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtofferallocations.md">D3DKMTOfferAllocations</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTReclaimAllocations function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

