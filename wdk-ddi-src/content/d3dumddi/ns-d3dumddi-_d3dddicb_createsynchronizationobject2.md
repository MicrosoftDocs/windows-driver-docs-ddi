---
UID: NS:d3dumddi._D3DDDICB_CREATESYNCHRONIZATIONOBJECT2
title: _D3DDDICB_CREATESYNCHRONIZATIONOBJECT2 (d3dumddi.h)
description: Describes a synchronization object that the pfnCreateSynchronizationObject2Cb function creates.
old-location: display\d3dddicb_createsynchronizationobject2.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDICB_CREATESYNCHRONIZATIONOBJECT2 structure"]
ms.keywords: D3DDDICB_CREATESYNCHRONIZATIONOBJECT2, D3DDDICB_CREATESYNCHRONIZATIONOBJECT2 structure [Display Devices], _D3DDDICB_CREATESYNCHRONIZATIONOBJECT2, d3dumddi/D3DDDICB_CREATESYNCHRONIZATIONOBJECT2, display.d3dddicb_createsynchronizationobject2
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.typenames: D3DDDICB_CREATESYNCHRONIZATIONOBJECT2
f1_keywords:
 - _D3DDDICB_CREATESYNCHRONIZATIONOBJECT2
 - d3dumddi/_D3DDDICB_CREATESYNCHRONIZATIONOBJECT2
 - D3DDDICB_CREATESYNCHRONIZATIONOBJECT2
 - d3dumddi/D3DDDICB_CREATESYNCHRONIZATIONOBJECT2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dumddi.h
api_name:
 - D3DDDICB_CREATESYNCHRONIZATIONOBJECT2
---

# _D3DDDICB_CREATESYNCHRONIZATIONOBJECT2 structure


## -description

Describes a synchronization object that the <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createsynchronizationobject2cb">pfnCreateSynchronizationObject2Cb</a> function creates.

## -struct-fields

### -field Info

[in] A <a href="/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_synchronizationobjectinfo2">D3DDDI_SYNCHRONIZATIONOBJECTINFO2</a> structure that contains information about the kernel-mode synchronization object to create.

### -field hSyncObject

[out] A <b>D3DKMT_HANDLE</b> value that represents a kernel-mode handle to the created kernel-mode GPU synchronization object.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_synchronizationobjectinfo2">D3DDDI_SYNCHRONIZATIONOBJECTINFO2</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createsynchronizationobject2cb">pfnCreateSynchronizationObject2Cb</a>
