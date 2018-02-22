---
UID: NC:d3dkmddi.DXGKDDI_GETROOTPAGETABLESIZE
title: DXGKDDI_GETROOTPAGETABLESIZE
author: windows-driver-content
description: DxgkDdiGetRootPageTableSize returns the minimum root page table size, in bytes, that is needed to hold the given number of page table entries.
old-location: display\dxgkddigetrootpagetablesize.htm
old-project: display
ms.assetid: 474F1772-0DF9-487B-AEB9-302392AE0B98
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.dxgkddigetrootpagetablesize, DxgkDdiGetRootPageTableSize callback function [Display Devices], DxgkDdiGetRootPageTableSize, DXGKDDI_GETROOTPAGETABLESIZE, DXGKDDI_GETROOTPAGETABLESIZE, d3dkmddi/DxgkDdiGetRootPageTableSize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dkmddi.h
apiname:
-	DxgkDdiGetRootPageTableSize
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_GETROOTPAGETABLESIZE callback


## -description


<b>DxgkDdiGetRootPageTableSize</b> returns the minimum root page table size,  in bytes, that is needed to hold the given number of page table entries. The actual number of entries in the page table could be greater than the given value. 

<b>DxgkDdiGetRootPageTableSize</b> is called only when <b>DXGK_GPUMMUCAPS</b>::<b>PageTableLevelCount</b> is two.

  


## -prototype


````
DXGKDDI_GETROOTPAGETABLESIZE DxgkDdiGetRootPageTableSize;

SIZE_T APIENTRY DxgkDdiGetRootPageTableSize(
  _In_    const HANDLE                       hAdapter,
  _Inout_       DXGKARG_GETROOTPAGETABLESIZE *pArgs
)
{ ... }
````


## -parameters




### -param hAdapter [in]

A handle to the display adapter.


### -param pArgs [in, out]

The <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_getrootpagetablesize.md">DXGKARG_GETROOTPAGETABLESIZE</a> structure that describes the operation.


## -returns



The page table size in bytes. The size must be a multiple of the page size of the GPU memory segment where page table is located.



