---
UID: NS:d3dumddi._D3DDDICB_DEALLOCATE2
title: "_D3DDDICB_DEALLOCATE2"
author: windows-driver-content
description: The D3DDDICB_DEALLOCATE2 structure describes parameters for releasing allocations with pfnDeallocate2Cb.
old-location: display\d3dddicb_deallocate2.htm
old-project: display
ms.assetid: C859CB06-3F71-4F6D-9949-0E9AE75CEC20
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DDDICB_DEALLOCATE2, D3DDDICB_DEALLOCATE2 structure [Display Devices], _D3DDDICB_DEALLOCATE2, d3dumddi/D3DDDICB_DEALLOCATE2, display.d3dddicb_deallocate2
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	D3DDDICB_DEALLOCATE2
product:
- Windows
targetos: Windows
req.typenames: D3DDDICB_DEALLOCATE2
---

# _D3DDDICB_DEALLOCATE2 structure


## -description


The <b>D3DDDICB_DEALLOCATE2</b> structure describes parameters for releasing allocations with <a href="https://msdn.microsoft.com/68C7EC44-D744-4C69-86D9-35B3B089875A">pfnDeallocate2Cb</a>



## -struct-fields




### -field hResource

[in] A handle to a resource whose associated allocations must be released. If the user-mode display driver uses the array that is specified by <b>HandleList</b> to specify the allocations to release, it sets <b>hResource</b> to <b>NULL</b>.


### -field NumAllocations

[in] The number of allocations in the <b>HandleList</b> array. If the user-mode display driver sets the handle in the <b>hResource</b> member to non-<b>NULL</b>, <b>NumAllocations</b> is ignored by the Direct3D runtime.


### -field HandleList

[in] An array of <b>D3DKMT_HANDLE</b> data types that represent kernel-mode handles to the allocations. The Direct3D runtime's <a href="https://msdn.microsoft.com/a61e6c6a-3992-429c-ad8c-5f1a61dc7b8b">pfnAllocateCb</a> function returns these handles. Therefore, the user-mode display driver uses these handles to release the allocations.

If the user-mode display driver sets the handle in the <b>hResource</b> member to non-<b>NULL</b>, <b>HandleList</b> is ignored by the Direct3D runtime. 


### -field Flags

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/dn906318">D3DDDICB_DESTROYALLOCATION2FLAGS</a> structure that contains additional details about the operation.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906318">D3DDDICB_DESTROYALLOCATION2FLAGS</a>



<a href="https://msdn.microsoft.com/68C7EC44-D744-4C69-86D9-35B3B089875A">pfnDeallocate2Cb</a>
 

 

