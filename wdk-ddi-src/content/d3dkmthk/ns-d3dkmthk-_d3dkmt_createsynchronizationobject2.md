---
UID: NS:d3dkmthk._D3DKMT_CREATESYNCHRONIZATIONOBJECT2
title: _D3DKMT_CREATESYNCHRONIZATIONOBJECT2 (d3dkmthk.h)
description: The D3DKMT_CREATESYNCHRONIZATIONOBJECT2 structure describes a synchronization object that the D3DKMTCreateSynchronizationObject2 function creates.
old-location: display\d3dkmt_createsynchronizationobject2.htm
ms.assetid: fa5cf57e-826b-43f6-881d-caf2aecb2dde
ms.date: 05/10/2018
ms.keywords: D3DKMT_CREATESYNCHRONIZATIONOBJECT2, D3DKMT_CREATESYNCHRONIZATIONOBJECT2 structure [Display Devices], OpenGL_Structs_a2f18286-355e-4a93-9692-344fbb2bd5a2.xml, _D3DKMT_CREATESYNCHRONIZATIONOBJECT2, d3dkmthk/D3DKMT_CREATESYNCHRONIZATIONOBJECT2, display.d3dkmt_createsynchronizationobject2
ms.topic: struct
f1_keywords:
 - "d3dkmthk/D3DKMT_CREATESYNCHRONIZATIONOBJECT2"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_CREATESYNCHRONIZATIONOBJECT2 is supported beginning with the Windows 7 operating system.
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
- d3dkmthk.h
api_name:
- D3DKMT_CREATESYNCHRONIZATIONOBJECT2
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_CREATESYNCHRONIZATIONOBJECT2
---

# _D3DKMT_CREATESYNCHRONIZATIONOBJECT2 structure


## -description


The D3DKMT_CREATESYNCHRONIZATIONOBJECT2 structure describes a synchronization object that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreatesynchronizationobject2">D3DKMTCreateSynchronizationObject2</a> function creates. 


## -struct-fields




### -field hDevice

[in] A handle to the device that the synchronization object is associated with. 


### -field Info

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_synchronizationobjectinfo2">D3DDDI_SYNCHRONIZATIONOBJECTINFO2</a> structure that describes information about the kernel-mode synchronization object. 


### -field hSyncObject

[out] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the kernel-mode synchronization object. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_synchronizationobjectinfo2">D3DDDI_SYNCHRONIZATIONOBJECTINFO2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreatesynchronizationobject2">D3DKMTCreateSynchronizationObject2</a>
 

 

