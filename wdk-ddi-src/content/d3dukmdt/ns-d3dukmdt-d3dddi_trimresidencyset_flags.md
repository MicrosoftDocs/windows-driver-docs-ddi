---
UID: NS:d3dukmdt.D3DDDI_TRIMRESIDENCYSET_FLAGS
title: D3DDDI_TRIMRESIDENCYSET_FLAGS (d3dukmdt.h)
description: D3DDDI_TRIMRESIDENCYSET_FLAGS is used with pfnTrimResidencySet to trim the residency list for a given device.
old-location: display\d3dddi_trimresidencyset_flags.htm
tech.root: display
ms.assetid: B063561B-FA79-44B4-A058-71DB9CBF4804
ms.date: 05/10/2018
ms.keywords: D3DDDI_TRIMRESIDENCYSET_FLAGS, D3DDDI_TRIMRESIDENCYSET_FLAGS structure [Display Devices], d3dukmdt/D3DDDI_TRIMRESIDENCYSET_FLAGS, display.d3dddi_trimresidencyset_flags
ms.topic: struct
f1_keywords:
 - "d3dukmdt/D3DDDI_TRIMRESIDENCYSET_FLAGS"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dukmdt.h
api_name:
- D3DDDI_TRIMRESIDENCYSET_FLAGS
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_TRIMRESIDENCYSET_FLAGS
---

# D3DDDI_TRIMRESIDENCYSET_FLAGS structure


## -description


<b>D3DDDI_TRIMRESIDENCYSET_FLAGS</b> is used with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_trimresidencyset">pfnTrimResidencySet</a> to trim the residency list for a given device.


## -struct-fields




### -field PeriodicTrim

When <b>PeriodicTrim</b> flag is set, the driver is required to performed the following operations:
                                                

<ul>
<li>Trim all allocations that were not referenced since the previous periodic trim request
                                                by comparing the allocation last referenced fence with the last periodic trim context fence.</li>
<li>Refresh the last periodic trim context fence with the last completed context fence.</li>
</ul>

### -field RestartPeriodicTrim

May not be set together with <b>PeriodicTrim</b> flag.
                                                Reset the last periodic trim context fence to the last completed context fence.


### -field TrimToBudget

Indicates that the application usage is over the memory budget
                                                and that <b>NumBytesToTrim</b> bytes should be trimmed to fit in the new memory budget.


### -field Reserved

This member is reserved and should be set to zero.


### -field Value

The consolidated value of the bit-fields in the structure.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_trimresidencyset">pfnTrimResidencySet</a>
 

 

