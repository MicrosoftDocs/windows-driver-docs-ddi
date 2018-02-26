---
UID: NS:d3dkmthk._D3DKMT_UNLOCK
title: "_D3DKMT_UNLOCK"
author: windows-driver-content
description: The D3DKMT_UNLOCK structure describes allocations to unlock.
old-location: display\d3dkmt_unlock.htm
old-project: display
ms.assetid: 397d2ab0-89a0-42a8-a665-ca7e1ed5d8f3
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, 3, C, D, D3DKMT_UNLOCK, D3DKMT_UNLOCK structure [Display Devices], K, L, M, N, O, OpenGL_Structs_d4f3b3e8-fddd-41d2-8a7e-ee43f25a1f2d.xml, T, U, _, _D3DKMT_UNLOCK, d3dkmthk/D3DKMT_UNLOCK, display.d3dkmt_unlock"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_UNLOCK
product: Windows
targetos: Windows
req.typenames: D3DKMT_UNLOCK
---

# _D3DKMT_UNLOCK structure


## -description


The D3DKMT_UNLOCK structure describes allocations to unlock. 


## -syntax


````
typedef struct _D3DKMT_UNLOCK {
  D3DKMT_HANDLE       hDevice;
  UINT                NumAllocations;
  const D3DKMT_HANDLE *phAllocations;
} D3DKMT_UNLOCK;
````


## -struct-fields




### -field hDevice

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the device that the allocation is associated with.


### -field NumAllocations

[in] The number of allocations in the array that <b>phAllocations</b> specifies. 


### -field phAllocations

[in] An array of D3DKMT_HANDLE data types that represent kernel-mode handles to the allocations to unlock.


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtunlock.md">D3DKMTUnlock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_UNLOCK structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

