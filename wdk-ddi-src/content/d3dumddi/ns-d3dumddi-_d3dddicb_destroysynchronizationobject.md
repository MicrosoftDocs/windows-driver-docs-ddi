---
UID: NS:d3dumddi._D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT
title: "_D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT"
author: windows-driver-content
description: The D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT structure contains the handle to a synchronization object to destroy.
old-location: display\d3dddicb_destroysynchronizationobject.htm
old-project: display
ms.assetid: d950e290-3acb-4a89-86a4-ae5117781998
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT, display.d3dddicb_destroysynchronizationobject, D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT, d3dumddi/D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT, D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT structure [Display Devices], D3D_param_Structs_34603e42-8f8b-42cb-9191-988be4a8932d.xml"
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
-	D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT
product: Windows
targetos: Windows
req.typenames: D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT
---

# _D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT structure


## -description


The D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT structure contains the handle to a synchronization object to destroy.


## -syntax


````
typedef struct _D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT {
  D3DKMT_HANDLE hSyncObject;
} D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT;
````


## -struct-fields




### -field hSyncObject

[in] A D3DKMT_HANDLE value that represents the kernel-mode handle that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createsynchronizationobjectcb.md">pfnCreateSynchronizationObjectCb</a> function returns and that identifies the kernel-mode synchronization object to destroy. 


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createsynchronizationobjectcb.md">pfnCreateSynchronizationObjectCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroysynchronizationobjectcb.md">pfnDestroySynchronizationObjectCb</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

