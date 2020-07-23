---
UID: NS:d3dkmthk._D3DKMT_CREATEKEYEDMUTEX
title: _D3DKMT_CREATEKEYEDMUTEX (d3dkmthk.h)
description: The D3DKMT_CREATEKEYEDMUTEX structure describes a keyed mutex that the D3DKMTCreateKeyedMutex function creates.
old-location: display\d3dkmt_createkeyedmutex.htm
ms.assetid: ab028faf-d3f7-4267-81c7-7ababe845667
ms.date: 05/10/2018
keywords: ["_D3DKMT_CREATEKEYEDMUTEX structure"]
ms.keywords: D3DKMT_CREATEKEYEDMUTEX, D3DKMT_CREATEKEYEDMUTEX structure [Display Devices], OpenGL_Structs_6ab1fe5f-9963-46ab-946d-689d74c70d11.xml, _D3DKMT_CREATEKEYEDMUTEX, d3dkmthk/D3DKMT_CREATEKEYEDMUTEX, display.d3dkmt_createkeyedmutex
f1_keywords:
 - "d3dkmthk/D3DKMT_CREATEKEYEDMUTEX"
 - "D3DKMT_CREATEKEYEDMUTEX"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_CREATEKEYEDMUTEX is supported beginning with the Windows 7 operating system.
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
- D3DKMT_CREATEKEYEDMUTEX
targetos: Windows
tech.root: display
req.typenames: D3DKMT_CREATEKEYEDMUTEX
---

# _D3DKMT_CREATEKEYEDMUTEX structure


## -description


The D3DKMT_CREATEKEYEDMUTEX structure describes a keyed mutex that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreatekeyedmutex">D3DKMTCreateKeyedMutex</a> function creates. 


## -struct-fields




### -field InitialValue

[in] A 64-bit value that specifies the initial value to create the keyed mutex for. 


### -field hSharedHandle

[out] A D3DKMT_HANDLE data type that represents a kernel-mode shared global handle to the keyed mutex object. 


### -field hKeyedMutex

[out] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the keyed mutex object in the current process. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreatekeyedmutex">D3DKMTCreateKeyedMutex</a>
 

 

