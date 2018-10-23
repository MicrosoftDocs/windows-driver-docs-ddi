---
UID: NS:d3dumddi._D3DDDICB_DEALLOCATE
title: "_D3DDDICB_DEALLOCATE"
author: windows-driver-content
description: The D3DDDICB_DEALLOCATE structure describes allocations to release.
old-location: display\d3dddicb_deallocate.htm
tech.root: display
ms.assetid: b1d92adf-6efc-4a30-bd5c-cbfe53a7c648
ms.date: 05/10/2018
ms.keywords: D3DDDICB_DEALLOCATE, D3DDDICB_DEALLOCATE structure [Display Devices], D3D_param_Structs_4182b764-2e99-4146-a8ae-15620524f408.xml, _D3DDDICB_DEALLOCATE, d3dumddi/D3DDDICB_DEALLOCATE, display.d3dddicb_deallocate
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
api_name:
-	D3DDDICB_DEALLOCATE
product:
- Windows
targetos: Windows
req.typenames: D3DDDICB_DEALLOCATE
---

# _D3DDDICB_DEALLOCATE structure


## -description


The D3DDDICB_DEALLOCATE structure describes allocations to release. 


## -struct-fields




### -field hResource

[in] A handle to a resource whose associated allocations must be released. If the user-mode display driver uses the array that is specified by <b>HandleList</b> to specify the allocations to release, it sets <b>hResource</b> to <b>NULL</b>.


### -field NumAllocations

[in] The number of allocations in the <b>HandleList</b> array. If the user-mode display driver sets the handle in the <b>hResource</b> member to non-<b>NULL</b>, <b>NumAllocations</b> is ignored by the Microsoft Direct3D runtime.


### -field HandleList

[in] An array of D3DKMT_HANDLE data types that represent kernel-mode handles to the allocations. The Direct3D runtime's <a href="https://msdn.microsoft.com/a61e6c6a-3992-429c-ad8c-5f1a61dc7b8b">pfnAllocateCb</a> function returns these handles. Therefore, the user-mode display driver uses these handles to release the allocations.

If the user-mode display driver sets the handle in the <b>hResource</b> member to non-<b>NULL</b>, <b>HandleList</b> is ignored by the Direct3D runtime. 


## -see-also




<a href="https://msdn.microsoft.com/2ffa0367-0451-45d2-be05-e450c45be116">pfnDeallocateCb</a>
 

 

