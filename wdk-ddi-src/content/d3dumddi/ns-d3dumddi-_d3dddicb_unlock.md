---
UID: NS:d3dumddi._D3DDDICB_UNLOCK
title: "_D3DDDICB_UNLOCK"
author: windows-driver-content
description: The D3DDDICB_UNLOCK structure describes allocations to unlock.
old-location: display\d3dddicb_unlock.htm
old-project: display
ms.assetid: 1e0e6313-1dfa-4b68-8f58-bfa79f3124d6
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: D3DDDICB_UNLOCK, d3dumddi/D3DDDICB_UNLOCK, display.d3dddicb_unlock, _D3DDDICB_UNLOCK, D3D_param_Structs_91515cd5-00b4-4ad6-a8a5-ff216ddec171.xml, D3DDDICB_UNLOCK structure [Display Devices]
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
-	D3DDDICB_UNLOCK
product: Windows
targetos: Windows
req.typenames: D3DDDICB_UNLOCK
---

# _D3DDDICB_UNLOCK structure


## -description


The D3DDDICB_UNLOCK structure describes allocations to unlock. 


## -syntax


````
typedef struct _D3DDDICB_UNLOCK {
  UINT                NumAllocations;
  const D3DKMT_HANDLE *phAllocations;
} D3DDDICB_UNLOCK;
````


## -struct-fields




### -field NumAllocations

[in] The number of allocations in the array that is specified by <b>phAllocations</b>. 


### -field phAllocations

[in] An array of D3DKMT_HANDLE data types that represent kernel-mode handles to the allocations. The Microsoft Direct3D runtime's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_allocatecb.md">pfnAllocateCb</a> function returns these handles. Therefore, the user-mode display driver uses these handles to unlock the allocations.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_unlockcb.md">pfnUnlockCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_allocatecb.md">pfnAllocateCb</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_UNLOCK structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

