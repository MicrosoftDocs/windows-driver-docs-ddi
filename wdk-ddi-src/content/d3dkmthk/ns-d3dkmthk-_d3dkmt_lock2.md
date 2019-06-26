---
UID: NS:d3dkmthk._D3DKMT_LOCK2
title: _D3DKMT_LOCK2 (d3dkmthk.h)
description: D3DKMT_LOCK2 describes parameters for locking an allocation.
old-location: display\d3dkmt_lock2.htm
ms.assetid: AFDA9D5F-2590-4034-B2CF-07990F4553C8
ms.date: 05/10/2018
ms.keywords: D3DKMT_LOCK2, D3DKMT_LOCK2 structure [Display Devices], _D3DKMT_LOCK2, d3dkmthk/D3DKMT_LOCK2, display.d3dkmt_lock2
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
- D3DKMT_LOCK2
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_LOCK2
---

# _D3DKMT_LOCK2 structure


## -description


<b>D3DKMT_LOCK2</b> describes parameters for locking an allocation.


## -struct-fields




### -field hDevice

The handle to the device.


### -field hAllocation

The handle to the allocation to lock.


### -field Flags

A set of flags to pass to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/nf-d3dkmthk-d3dkmtlock2">Lock2</a> kernel function which will determine how the allocation is locked. See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ns-d3dukmdt-_d3dddicb_lock2flags">D3DDDICB_LOCK2FLAGS</a> for details.


### -field pData

A CPU virtual address pointing a valid memory location pointing to the CPU backing store or the GPU frame buffer.

