---
UID: NS:d3dkmddi._DXGKARG_SETROOTPAGETABLE
title: "_DXGKARG_SETROOTPAGETABLE"
author: windows-driver-content
description: DXGKARG_SETROOTPAGETABLE is used by the DxgkDdiSetRootPageTabledevice driver interface (DDI) to notify a context when its associated root page table is resized or moved in memory.
old-location: display\dxgkarg_setrootpagetable.htm
old-project: display
ms.assetid: D3863924-29EE-4886-B8DC-F9020A7C85A4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKARG_SETROOTPAGETABLE, DXGKARG_SETROOTPAGETABLE structure [Display Devices], _DXGKARG_SETROOTPAGETABLE, d3dkmddi/DXGKARG_SETROOTPAGETABLE, display.dxgkarg_setrootpagetable
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
-	DXGKARG_SETROOTPAGETABLE
product: Windows
targetos: Windows
req.typenames: DXGKARG_SETROOTPAGETABLE
---

# _DXGKARG_SETROOTPAGETABLE structure


## -description


<b>DXGKARG_SETROOTPAGETABLE</b> is used by the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setrootpagetable.md">DxgkDdiSetRootPageTable</a>device driver interface (DDI) to notify a context when its associated root page table is resized or moved in memory.


## -syntax


````
typedef struct _DXGKARG_SETROOTPAGETABLE {
  HANDLE                  hContext;
  D3DGPU_PHYSICAL_ADDRESS Address;
  UINT                    NumEntries;
} DXGKARG_SETROOTPAGETABLE;
````


## -struct-fields




### -field hContext

A context handle returned by <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createcontext.md">DxgkDdiCreateContext</a>.


### -field Address

The GPU physical address of the root page table.


### -field NumEntries

 The root page table size in entries. GPU should generate invalid fault when a virtual address has a top level page table entry index, which is greater or equal this value.


## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setrootpagetable.md">DxgkDdiSetRootPageTable</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createcontext.md">DxgkDdiCreateContext</a>



 

 


