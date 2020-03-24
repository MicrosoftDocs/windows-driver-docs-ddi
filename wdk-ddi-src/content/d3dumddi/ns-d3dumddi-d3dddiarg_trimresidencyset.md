---
UID: NS:d3dumddi.D3DDDIARG_TRIMRESIDENCYSET
title: D3DDDIARG_TRIMRESIDENCYSET (d3dumddi.h)
description: D3DDDIARG_TRIMRESIDENCYSET is used with pfnTrimResidencySet by a user mode driver to trim the residency list for a given device.
old-location: display\d3dddiarg_trimresidencyset.htm
tech.root: display
ms.assetid: DEF219B9-115A-4B61-8014-266730CEBD30
ms.date: 05/10/2018
keywords: ["D3DDDIARG_TRIMRESIDENCYSET structure"]
ms.keywords: D3DDDIARG_TRIMRESIDENCYSET, D3DDDIARG_TRIMRESIDENCYSET structure [Display Devices], d3dumddi/D3DDDIARG_TRIMRESIDENCYSET, display.d3dddiarg_trimresidencyset
f1_keywords:
 - "d3dumddi/D3DDDIARG_TRIMRESIDENCYSET"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
- d3dumddi.h
api_name:
- D3DDDIARG_TRIMRESIDENCYSET
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_TRIMRESIDENCYSET
---

# D3DDDIARG_TRIMRESIDENCYSET structure


## -description


<b>D3DDDIARG_TRIMRESIDENCYSET</b> is used with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_trimresidencyset">pfnTrimResidencySet</a> by a user mode driver to trim the residency list for a given device.


## -struct-fields




### -field TrimFlags

The trimming behavior flags.


### -field NumBytesToTrim

When <b>TrimToBudget</b> is set, this value specifies how much the application should evict in order to meet its current memory budget.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_trimresidencyset">pfnTrimResidencySet</a>
 

 

