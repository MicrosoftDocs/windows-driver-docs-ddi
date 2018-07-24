---
UID: NS:d3dkmthk._D3DKMT_DESTROYALLOCATION
title: "_D3DKMT_DESTROYALLOCATION"
author: windows-driver-content
description: The D3DKMT_DESTROYALLOCATION structure describes parameters for releasing allocations.
old-location: display\d3dkmt_destroyallocation.htm
tech.root: display
ms.assetid: ba85b333-9a43-421a-8687-9630e792cadf
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DKMT_DESTROYALLOCATION, D3DKMT_DESTROYALLOCATION structure [Display Devices], OpenGL_Structs_46425135-17f7-4b12-8e01-1247e3e1ab63.xml, _D3DKMT_DESTROYALLOCATION, d3dkmthk/D3DKMT_DESTROYALLOCATION, display.d3dkmt_destroyallocation
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
-	D3DKMT_DESTROYALLOCATION
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_DESTROYALLOCATION
---

# _D3DKMT_DESTROYALLOCATION structure


## -description


The D3DKMT_DESTROYALLOCATION structure describes parameters for releasing allocations.


## -struct-fields




### -field hDevice

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the device that the resource, allocations, or both are associated with.


### -field hResource

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the resource that is associated with the allocations when releasing a resource. If a resource handle is specified, all of the allocations that are associated with it are automatically released.


### -field phAllocationList

[in] An array of D3DKMT_HANDLE data types that represent kernel-mode handles to the allocations. If any allocation in the list is associated with a resource, all of the allocations in the list must also be associated with the same resource. If the OpenGL ICD sets the handle in the <b>hResource</b> member to a non-<b>NULL</b> value, the ICD must set <b>phAllocationList</b> to <b>NULL</b>.


### -field AllocationCount

[in] The number of allocations in the array that <b>phAllocationList</b> specifies. If the OpenGL ICD sets the handle in the <b>hResource</b> member to a non-<b>NULL</b> value, the <b>AllocationCount</b> member is ignored by the OpenGL runtime.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546891">D3DKMTDestroyAllocation</a>
 

 

