---
UID: NS:d3dkmthk._D3DKMT_ACQUIREKEYEDMUTEX2
title: _D3DKMT_ACQUIREKEYEDMUTEX2 (d3dkmthk.h)
description: Describes a keyed mutex object that the D3DKMTAcquireKeyedMutex2 function acquires that includes private data.
old-location: display\d3dkmt_acquirekeyedmutex2.htm
ms.assetid: 6e7ccf24-6403-44bf-9369-d2825646e950
ms.date: 05/10/2018
keywords: ["_D3DKMT_ACQUIREKEYEDMUTEX2 structure"]
ms.keywords: D3DKMT_ACQUIREKEYEDMUTEX2, D3DKMT_ACQUIREKEYEDMUTEX2 structure [Display Devices], _D3DKMT_ACQUIREKEYEDMUTEX2, d3dkmthk/D3DKMT_ACQUIREKEYEDMUTEX2, display.d3dkmt_acquirekeyedmutex2
f1_keywords:
 - "d3dkmthk/D3DKMT_ACQUIREKEYEDMUTEX2"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3dkmthk.h
api_name:
- D3DKMT_ACQUIREKEYEDMUTEX2
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_ACQUIREKEYEDMUTEX2
---

# _D3DKMT_ACQUIREKEYEDMUTEX2 structure


## -description


Describes a keyed mutex object that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtacquirekeyedmutex2">D3DKMTAcquireKeyedMutex2</a> function acquires that includes private data.


## -struct-fields




### -field hKeyedMutex

[in] A D3DKMT_HANDLE data type that represents a handle to the keyed mutex.


### -field Key

[in] The key value to acquire.


### -field pTimeout

[in] An NT-style timeout value.


### -field FenceValue

[out] The current fence value of the GPU sync object.


### -field pPrivateRuntimeData

[out] A pointer to a buffer to copy private data to.


### -field PrivateRuntimeDataSize

[in] The size, in bytes, of the <b>pPrivateRuntimeData</b> member.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtacquirekeyedmutex2">D3DKMTAcquireKeyedMutex2</a>
 

 

