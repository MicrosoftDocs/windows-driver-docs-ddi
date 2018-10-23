---
UID: NS:d3dumddi._D3DDDICB_FREEGPUVIRTUALADDRESS
title: "_D3DDDICB_FREEGPUVIRTUALADDRESS"
author: windows-driver-content
description: D3DDDICB_FREEGPUVIRTUALADDRESS is used with pfnFreeGpuVirtualAddressCb to release a range of graphics processing unit (GPU) virtual addresses that were previously reserved or mapped.
old-location: display\d3dddicb_freegpuvirtualaddress.htm
tech.root: display
ms.assetid: 5E11C1BB-7E9E-4D9C-A15A-B9CCB29622C3
ms.date: 05/10/2018
ms.keywords: D3DDDICB_FREEGPUVIRTUALADDRESS, D3DDDICB_FREEGPUVIRTUALADDRESS structure [Display Devices], _D3DDDICB_FREEGPUVIRTUALADDRESS, d3dumddi/D3DDDICB_FREEGPUVIRTUALADDRESS, display.d3dddicb_freegpuvirtualaddress
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDICB_FREEGPUVIRTUALADDRESS
product:
- Windows
targetos: Windows
req.typenames: D3DDDICB_FREEGPUVIRTUALADDRESS
---

# _D3DDDICB_FREEGPUVIRTUALADDRESS structure


## -description


<b>D3DDDICB_FREEGPUVIRTUALADDRESS</b> is used with <a href="https://msdn.microsoft.com/92F2A43C-699B-4580-8A56-472D837A76E2">pfnFreeGpuVirtualAddressCb</a> to release a range of graphics processing unit (GPU) virtual addresses that were previously reserved or mapped.


## -struct-fields




### -field BaseAddress

Specifies the base virtual address, in bytes, of the range to free. Must be aligned to 4 KB.


### -field Size

Specifies the size, in bytes, of the range to free. Must be aligned to 4 KB.


## -see-also




<a href="https://msdn.microsoft.com/92F2A43C-699B-4580-8A56-472D837A76E2">pfnFreeGpuVirtualAddressCb</a>
 

 

