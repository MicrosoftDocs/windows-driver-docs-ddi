---
UID: NS:d3dkmddi._DXGKARG_CLOSEALLOCATION
title: "_DXGKARG_CLOSEALLOCATION"
author: windows-driver-content
description: The DXGKARG_CLOSEALLOCATION structure describes allocations that the display miniport driver should close.
old-location: display\dxgkarg_closeallocation.htm
old-project: display
ms.assetid: ccd65750-b4d0-4955-9fd4-9546709c2390
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKARG_CLOSEALLOCATION, DXGKARG_CLOSEALLOCATION structure [Display Devices], DmStructs_0d76b996-7ce8-4471-894f-585cc9f3f225.xml, _DXGKARG_CLOSEALLOCATION, d3dkmddi/DXGKARG_CLOSEALLOCATION, display.dxgkarg_closeallocation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
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
-	DXGKARG_CLOSEALLOCATION
product:
- Windows
targetos: Windows
req.typenames: DXGKARG_CLOSEALLOCATION
---

# _DXGKARG_CLOSEALLOCATION structure


## -description


The DXGKARG_CLOSEALLOCATION structure describes allocations that the display miniport driver should close.


## -struct-fields




### -field NumAllocations

[in] The number of elements in the array that <b>pOpenHandleList</b> specifies.


### -field pOpenHandleList

[in] An array of handles to device-specific allocations to close.


## -see-also




<a href="https://msdn.microsoft.com/f9c195d7-debe-495e-a355-e176d06884f8">DxgkDdiCloseAllocation</a>
 

 

