---
UID: NS:d3dkmddi._DXGKARG_GETROOTPAGETABLESIZE
title: "_DXGKARG_GETROOTPAGETABLESIZE"
author: windows-driver-content
description: DXGKARG_GETROOTPAGETABLESIZE is used with DxgkDdiGetRootPageTableSize.
old-location: display\dxgkarg_getrootpagetablesize.htm
old-project: display
ms.assetid: 31CB33F9-87E8-419D-AF35-E7F731661DD5
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*INOUT_PDXGKARG_GETROOTPAGETABLESIZE, DXGKARG_GETROOTPAGETABLESIZE, DXGKARG_GETROOTPAGETABLESIZE structure [Display Devices], _DXGKARG_GETROOTPAGETABLESIZE, d3dkmddi/DXGKARG_GETROOTPAGETABLESIZE, display.dxgkarg_getrootpagetablesize"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGKARG_GETROOTPAGETABLESIZE
product:
- Windows
targetos: Windows
req.typenames: DXGKARG_GETROOTPAGETABLESIZE
---

# _DXGKARG_GETROOTPAGETABLESIZE structure


## -description


<b>DXGKARG_GETROOTPAGETABLESIZE</b> is used with <a href="https://msdn.microsoft.com/474F1772-0DF9-487B-AEB9-302392AE0B98">DxgkDdiGetRootPageTableSize</a>.


## -struct-fields




### -field NumberOfPte

[in] A pointer to the number of page table entries which are required to be in the root page table.

[out] The actual number of page table entries in the page table with the returned size.


### -field PhysicalAdapterIndex

Physical adapter index (zero for non-linked display adapter configurations).


## -see-also




<a href="https://msdn.microsoft.com/474F1772-0DF9-487B-AEB9-302392AE0B98">DxgkDdiGetRootPageTableSize</a>
 

 

