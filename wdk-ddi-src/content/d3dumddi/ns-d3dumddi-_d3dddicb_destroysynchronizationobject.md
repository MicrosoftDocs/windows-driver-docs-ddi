---
UID: NS:d3dumddi._D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT
title: _D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT (d3dumddi.h)
description: The D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT structure contains the handle to a synchronization object to destroy.
old-location: display\d3dddicb_destroysynchronizationobject.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT structure"]
ms.keywords: D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT, D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT structure [Display Devices], D3D_param_Structs_34603e42-8f8b-42cb-9191-988be4a8932d.xml, _D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT, d3dumddi/D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT, display.d3dddicb_destroysynchronizationobject
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
targetos: Windows
req.typenames: D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT
f1_keywords:
 - _D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT
 - d3dumddi/_D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT
 - D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT
 - d3dumddi/D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT
 - D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT
---

# _D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT structure


## -description

The D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT structure contains the handle to a synchronization object to destroy.

## -struct-fields

### -field hSyncObject [in]

A D3DKMT_HANDLE value that represents the kernel-mode handle that the <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createsynchronizationobjectcb">pfnCreateSynchronizationObjectCb</a> function returns and that identifies the kernel-mode synchronization object to destroy.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createsynchronizationobjectcb">pfnCreateSynchronizationObjectCb</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_destroysynchronizationobjectcb">pfnDestroySynchronizationObjectCb</a>

