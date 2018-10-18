---
UID: NS:d3dkmddi._DXGKARG_SETROOTPAGETABLE
title: "_DXGKARG_SETROOTPAGETABLE"
author: windows-driver-content
description: DXGKARG_SETROOTPAGETABLE is used by the DxgkDdiSetRootPageTabledevice driver interface (DDI) to notify a context when its associated root page table is resized or moved in memory.
old-location: display\dxgkarg_setrootpagetable.htm
ms.assetid: D3863924-29EE-4886-B8DC-F9020A7C85A4
ms.date: 5/10/2018
ms.keywords: DXGKARG_SETROOTPAGETABLE, DXGKARG_SETROOTPAGETABLE structure [Display Devices], _DXGKARG_SETROOTPAGETABLE, d3dkmddi/DXGKARG_SETROOTPAGETABLE, display.dxgkarg_setrootpagetable
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGKARG_SETROOTPAGETABLE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGKARG_SETROOTPAGETABLE
---

# _DXGKARG_SETROOTPAGETABLE structure


## -description


<b>DXGKARG_SETROOTPAGETABLE</b> is used by the <a href="https://msdn.microsoft.com/BC9E7A2D-690D-4EC2-8D16-22C5FEBA574A">DxgkDdiSetRootPageTable</a>device driver interface (DDI) to notify a context when its associated root page table is resized or moved in memory.


## -struct-fields




### -field hContext

A context handle returned by <a href="https://msdn.microsoft.com/aea21a36-f3d5-4541-bd2d-aa026668c562">DxgkDdiCreateContext</a>.


### -field Address

The GPU physical address of the root page table.


### -field NumEntries

 The root page table size in entries. GPU should generate invalid fault when a virtual address has a top level page table entry index, which is greater or equal this value.


## -see-also




<a href="https://msdn.microsoft.com/aea21a36-f3d5-4541-bd2d-aa026668c562">DxgkDdiCreateContext</a>



<a href="https://msdn.microsoft.com/BC9E7A2D-690D-4EC2-8D16-22C5FEBA574A">DxgkDdiSetRootPageTable</a>
 

 

