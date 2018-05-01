---
UID: NE:d3dkmthk._D3DKMT_OFFER_PRIORITY
title: "_D3DKMT_OFFER_PRIORITY"
author: windows-driver-content
description: Indicates the importance of video memory resources that the user-mode display driver offers for reuse.
old-location: display\d3dkmt_offer_priority.htm
old-project: display
ms.assetid: fec15098-3130-42d6-b889-579ecab6f162
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DKMT_OFFER_PRIORITY, D3DKMT_OFFER_PRIORITY enumeration [Display Devices], D3DKMT_OFFER_PRIORITY_AUTO, D3DKMT_OFFER_PRIORITY_HIGH, D3DKMT_OFFER_PRIORITY_LOW, D3DKMT_OFFER_PRIORITY_NORMAL, _D3DKMT_OFFER_PRIORITY, d3dkmthk/D3DKMT_OFFER_PRIORITY, d3dkmthk/D3DKMT_OFFER_PRIORITY_AUTO, d3dkmthk/D3DKMT_OFFER_PRIORITY_HIGH, d3dkmthk/D3DKMT_OFFER_PRIORITY_LOW, d3dkmthk/D3DKMT_OFFER_PRIORITY_NORMAL, display.d3dkmt_offer_priority
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmthk.h
api_name:
-	D3DKMT_OFFER_PRIORITY
product: Windows
targetos: Windows
req.typenames: D3DKMT_OFFER_PRIORITY
---

# _D3DKMT_OFFER_PRIORITY enumeration


## -description


Indicates the importance of video memory resources  that the user-mode display driver offers for reuse.


## -enum-fields




### -field D3DKMT_OFFER_PRIORITY_LOW

The allocation has low value and should be discarded before other offered allocations. Specify this type for allocations that have no useful content.


### -field D3DKMT_OFFER_PRIORITY_NORMAL

The allocation has useful content but can easily be regenerated.


### -field D3DKMT_OFFER_PRIORITY_HIGH

The allocation has useful content and cannot easily be regenerated. The video memory manager (which is part of Dxgkrnl.sys) should therefore avoid discarding this allocation before other offered allocations.


### -field D3DKMT_OFFER_PRIORITY_AUTO

The video memory manager should make a policy decision on the allocation's value based on its  priority for eviction.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406482">D3DKMT_OFFERALLOCATIONS</a>
 

 

