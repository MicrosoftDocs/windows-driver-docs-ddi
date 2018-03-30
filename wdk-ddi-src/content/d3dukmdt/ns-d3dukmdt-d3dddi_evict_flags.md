---
UID: NS:d3dukmdt.D3DDDI_EVICT_FLAGS
title: D3DDDI_EVICT_FLAGS
author: windows-driver-content
description: D3DDDI_EVICT_FLAGS specifies the eviction behavior.
old-location: display\d3dddi_evict_flags.htm
old-project: display
ms.assetid: 443671F1-98F5-4F9F-900B-37E3E50770CE
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDI_EVICT_FLAGS, D3DDDI_EVICT_FLAGS structure [Display Devices], d3dukmdt/D3DDDI_EVICT_FLAGS, display.d3dddi_evict_flags
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dukmdt.h
api_name:
-	D3DDDI_EVICT_FLAGS
product: Windows
targetos: Windows
req.typenames: D3DDDI_EVICT_FLAGS
---

# D3DDDI_EVICT_FLAGS structure


## -description


<b>D3DDDI_EVICT_FLAGS</b> specifies the eviction behavior.


## -struct-fields




### -field EvictOnlyIfNecessary

When set, this indicates that the resource may be used again in the near future and instructs the OS to try to defer actual resource eviction from the GPU until low memory conditions. When not set, this instructs the OS that the resource will no longer be used and that the eviction should be performed at the earliest opportunity. 

<div class="alert"><b>Note</b>  This flag is ignored if the residency reference count does not hit zero because the allocation will not be evicted until that time.</div>
<div> </div>

### -field NotWrittenTo

When set, this indicates that the resource has not been written to by the GPU since the time it was made resident. This allows the OS to optimize the eviction process by discarding the allocation contents instead of paging it out to the system memory. The driver must opt-in to use this flag. By default, the value is zero and the allocation is considered dirty during eviction. Unlike <b>EvictOnlyIfNecessary</b>, the driver does not need to defer setting this flag until the last call to <b>Evict</b> (<a href="https://msdn.microsoft.com/5E66A522-BC1C-4E7C-8732-87D40F99BBDA">pfnEvictCb</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/dn906774">D3DKMTEvict</a>), and the effects of specifying this flag take place immediately. In other words, if the driver calls <b>MakeResident</b> multiple times, it is valid for any one of the subsequent <b>Evict</b> operations to specify this flag. The driver is not expected to track this flag until the last call.


### -field Reserved

This member is reserved and should be set to zero.


#### - Value

The consolidated value of the flags in the structure.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906774">D3DKMTEvict</a>



<a href="https://msdn.microsoft.com/5E66A522-BC1C-4E7C-8732-87D40F99BBDA">pfnEvictCb</a>
 

 

