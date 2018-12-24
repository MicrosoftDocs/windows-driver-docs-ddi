---
UID: NS:d3dkmthk._D3DKMT_DESTROYSYNCHRONIZATIONOBJECT
title: "_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT"
description: The D3DKMT_DESTROYSYNCHRONIZATIONOBJECT structure contains the handle to a synchronization object to destroy.
old-location: display\d3dkmt_destroysynchronizationobject.htm
ms.assetid: d6be16da-7f92-4c10-af8b-7ecd05ef6856
ms.date: 05/10/2018
ms.keywords: D3DKMT_DESTROYSYNCHRONIZATIONOBJECT, D3DKMT_DESTROYSYNCHRONIZATIONOBJECT structure [Display Devices], OpenGL_Structs_ca88b27b-fcac-41f6-bf16-9f26507f4e3f.xml, _D3DKMT_DESTROYSYNCHRONIZATIONOBJECT, d3dkmthk/D3DKMT_DESTROYSYNCHRONIZATIONOBJECT, display.d3dkmt_destroysynchronizationobject
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
-	D3DKMT_DESTROYSYNCHRONIZATIONOBJECT
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_DESTROYSYNCHRONIZATIONOBJECT
---

# _D3DKMT_DESTROYSYNCHRONIZATIONOBJECT structure


## -description


The D3DKMT_DESTROYSYNCHRONIZATIONOBJECT structure contains the handle to a synchronization object to destroy.


## -struct-fields




### -field hSyncObject

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546869">D3DKMTCreateSynchronizationObject</a> function returns and that identifies the kernel-mode synchronization object to destroy. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546869">D3DKMTCreateSynchronizationObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546935">D3DKMTDestroySynchronizationObject</a>
 

 

