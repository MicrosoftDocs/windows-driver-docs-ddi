---
UID: NS:d3dkmthk._D3DKMT_UNLOCK
title: "_D3DKMT_UNLOCK"
author: windows-driver-content
description: The D3DKMT_UNLOCK structure describes allocations to unlock.
old-location: display\d3dkmt_unlock.htm
old-project: display
ms.assetid: 397d2ab0-89a0-42a8-a665-ca7e1ed5d8f3
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DKMT_UNLOCK, D3DKMT_UNLOCK structure [Display Devices], OpenGL_Structs_d4f3b3e8-fddd-41d2-8a7e-ee43f25a1f2d.xml, _D3DKMT_UNLOCK, d3dkmthk/D3DKMT_UNLOCK, display.d3dkmt_unlock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_UNLOCK
product: Windows
targetos: Windows
req.typenames: D3DKMT_UNLOCK
---

# _D3DKMT_UNLOCK structure


## -description


The D3DKMT_UNLOCK structure describes allocations to unlock. 


## -struct-fields




### -field hDevice

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the device that the allocation is associated with.


### -field NumAllocations

[in] The number of allocations in the array that <b>phAllocations</b> specifies. 


### -field phAllocations

[in] An array of D3DKMT_HANDLE data types that represent kernel-mode handles to the allocations to unlock.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547233">D3DKMTUnlock</a>
 

 

