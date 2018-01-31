---
UID: NS:d3dkmddi._DXGK_BUILDPAGINGBUFFER_FLUSHTLB
title: "_DXGK_BUILDPAGINGBUFFER_FLUSHTLB"
author: windows-driver-content
description: DXGK_BUILDPAGINGBUFFER_FLUSHTLB is used as part of a flush translation look-aside buffer (TLB) operation.
old-location: display\dxgk_buildpagingbuffer_flushtlb.htm
old-project: display
ms.assetid: 9FDE47A4-1784-41EB-9F60-76368D6DFEED
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_DXGK_BUILDPAGINGBUFFER_FLUSHTLB, d3dkmddi/DXGK_BUILDPAGINGBUFFER_FLUSHTLB, DXGK_BUILDPAGINGBUFFER_FLUSHTLB, DXGK_BUILDPAGINGBUFFER_FLUSHTLB structure [Display Devices], display.dxgk_buildpagingbuffer_flushtlb"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_BUILDPAGINGBUFFER_FLUSHTLB
product: Windows
targetos: Windows
req.typenames: DXGK_BUILDPAGINGBUFFER_FLUSHTLB
---

# _DXGK_BUILDPAGINGBUFFER_FLUSHTLB structure


## -description


<b>DXGK_BUILDPAGINGBUFFER_FLUSHTLB</b> is used as part of a flush translation look-aside buffer (TLB) operation.


## -syntax


````
typedef struct _DXGK_BUILDPAGINGBUFFER_FLUSHTLB {
  D3DGPU_PHYSICAL_ADDRESS RootPageTableAddress;
  HANDLE                  hProcess;
  D3DGPU_PHYSICAL_ADDRESS StartVirtualAddress;
  D3DGPU_PHYSICAL_ADDRESS EndVirtualAddress;
} DXGK_BUILDPAGINGBUFFER_FLUSHTLB;
````


## -struct-fields




#### - RootPageTableAddress

Physical address of the root page table being invalidated.


#### - hProcess

KMD process handle,  returned from <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createprocess.md">DxgkDdiCreateProcess</a>, that the page table belongs to. 


#### - StartVirtualAddress

The start of the affected GPU virtual address range.


#### - EndVirtualAddress

The end of the affected GPU virtual address range. When both <b>StartVirtualAddress</b> and <b>EndVirtualAddress</b> are zero, the entire GPU virtual address range is affected.

