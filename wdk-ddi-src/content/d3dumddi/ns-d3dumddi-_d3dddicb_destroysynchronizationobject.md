---
UID: NS:d3dumddi._D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT
title: _D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT (d3dumddi.h)
description: The D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT structure contains the handle to a synchronization object to destroy.
old-location: display\d3dddicb_destroysynchronizationobject.htm
tech.root: display
ms.assetid: d950e290-3acb-4a89-86a4-ae5117781998
ms.date: 05/10/2018
keywords: ["_D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT structure"]
ms.keywords: D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT, D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT structure [Display Devices], D3D_param_Structs_34603e42-8f8b-42cb-9191-988be4a8932d.xml, _D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT, d3dumddi/D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT, display.d3dddicb_destroysynchronizationobject
f1_keywords:
 - "d3dumddi/D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT
product:
- Windows
targetos: Windows
req.typenames: D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT
---

# _D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT structure


## -description


The D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT structure contains the handle to a synchronization object to destroy.


## -struct-fields




### -field hSyncObject

[in] A D3DKMT_HANDLE value that represents the kernel-mode handle that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createsynchronizationobjectcb">pfnCreateSynchronizationObjectCb</a> function returns and that identifies the kernel-mode synchronization object to destroy. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createsynchronizationobjectcb">pfnCreateSynchronizationObjectCb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_destroysynchronizationobjectcb">pfnDestroySynchronizationObjectCb</a>
 

 

