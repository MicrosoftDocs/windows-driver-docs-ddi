---
UID: NS:d3dkmthk._D3DKMT_OPENSYNCHRONIZATIONOBJECT
title: _D3DKMT_OPENSYNCHRONIZATIONOBJECT (d3dkmthk.h)
description: The D3DKMT_OPENSYNCHRONIZATIONOBJECT structure describes a synchronization object that the D3DKMTOpenSynchronizationObject function opens.
old-location: display\d3dkmt_opensynchronizationobject.htm
ms.assetid: 58e71ce5-29d0-4ee2-8d91-02230021110d
ms.date: 05/10/2018
keywords: ["_D3DKMT_OPENSYNCHRONIZATIONOBJECT structure"]
ms.keywords: D3DKMT_OPENSYNCHRONIZATIONOBJECT, D3DKMT_OPENSYNCHRONIZATIONOBJECT structure [Display Devices], OpenGL_Structs_61f9f676-2b21-4cb3-8c6a-9f25ce3ac2bc.xml, _D3DKMT_OPENSYNCHRONIZATIONOBJECT, d3dkmthk/D3DKMT_OPENSYNCHRONIZATIONOBJECT, display.d3dkmt_opensynchronizationobject
f1_keywords:
 - "d3dkmthk/D3DKMT_OPENSYNCHRONIZATIONOBJECT"
 - "D3DKMT_OPENSYNCHRONIZATIONOBJECT"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_OPENSYNCHRONIZATIONOBJECT is supported beginning with the Windows 7 operating system.
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
- D3DKMT_OPENSYNCHRONIZATIONOBJECT
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_OPENSYNCHRONIZATIONOBJECT
---

# _D3DKMT_OPENSYNCHRONIZATIONOBJECT structure


## -description


The D3DKMT_OPENSYNCHRONIZATIONOBJECT structure describes a synchronization object that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopensynchronizationobject">D3DKMTOpenSynchronizationObject</a> function opens. 


## -struct-fields




### -field hSharedHandle

[in] A shared handle to the synchronization object to be opened. 


### -field hSyncObject

[out] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the kernel-mode synchronization object in the current process. 


### -field Reserved

[in] An array of 64-bit values that are reserved for future use. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopensynchronizationobject">D3DKMTOpenSynchronizationObject</a>
 

 

