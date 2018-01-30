---
UID: NS:d3dumddi._D3DDDICB_DEALLOCATE
title: "_D3DDDICB_DEALLOCATE"
author: windows-driver-content
description: The D3DDDICB_DEALLOCATE structure describes allocations to release.
old-location: display\d3dddicb_deallocate.htm
old-project: display
ms.assetid: b1d92adf-6efc-4a30-bd5c-cbfe53a7c648
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dumddi/D3DDDICB_DEALLOCATE, display.d3dddicb_deallocate, D3DDDICB_DEALLOCATE, D3D_param_Structs_4182b764-2e99-4146-a8ae-15620524f408.xml, D3DDDICB_DEALLOCATE structure [Display Devices], _D3DDDICB_DEALLOCATE
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDICB_DEALLOCATE
product: Windows
targetos: Windows
req.typenames: D3DDDICB_DEALLOCATE
---

# _D3DDDICB_DEALLOCATE structure


## -description


The D3DDDICB_DEALLOCATE structure describes allocations to release. 


## -syntax


````
typedef struct _D3DDDICB_DEALLOCATE {
  HANDLE              hResource;
  UINT                NumAllocations;
  const D3DKMT_HANDLE *HandleList;
} D3DDDICB_DEALLOCATE;
````


## -struct-fields




### -field hResource

[in] A handle to a resource whose associated allocations must be released. If the user-mode display driver uses the array that is specified by <b>HandleList</b> to specify the allocations to release, it sets <b>hResource</b> to <b>NULL</b>.


### -field NumAllocations

[in] The number of allocations in the <b>HandleList</b> array. If the user-mode display driver sets the handle in the <b>hResource</b> member to non-<b>NULL</b>, <b>NumAllocations</b> is ignored by the Microsoft Direct3D runtime.


### -field HandleList

[in] An array of D3DKMT_HANDLE data types that represent kernel-mode handles to the allocations. The Direct3D runtime's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_allocatecb.md">pfnAllocateCb</a> function returns these handles. Therefore, the user-mode display driver uses these handles to release the allocations.

If the user-mode display driver sets the handle in the <b>hResource</b> member to non-<b>NULL</b>, <b>HandleList</b> is ignored by the Direct3D runtime. 


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_deallocatecb.md">pfnDeallocateCb</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_DEALLOCATE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

