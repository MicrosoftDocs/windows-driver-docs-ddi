---
UID: NS:d3dkmthk._D3DKMT_LOCK2
title: "_D3DKMT_LOCK2"
author: windows-driver-content
description: D3DKMT_LOCK2 describes parameters for locking an allocation.
old-location: display\d3dkmt_lock2.htm
old-project: display
ms.assetid: AFDA9D5F-2590-4034-B2CF-07990F4553C8
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DKMT_LOCK2, D3DKMT_LOCK2 structure [Display Devices], _D3DKMT_LOCK2, d3dkmthk/D3DKMT_LOCK2, display.d3dkmt_lock2
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_LOCK2
product: Windows
targetos: Windows
req.typenames: D3DKMT_LOCK2
---

# _D3DKMT_LOCK2 structure


## -description


<b>D3DKMT_LOCK2</b> describes parameters for locking an allocation.


## -syntax


````
typedef struct _D3DKMT_LOCK2 {
  D3DKMT_HANDLE       hDevice;
  D3DKMT_HANDLE       hAllocation;
  D3DDDICB_LOCK2FLAGS Flags;
  PVOID               pData;
} D3DKMT_LOCK2;
````


## -struct-fields




### -field hDevice

The handle to the device.


### -field hAllocation

The handle to the allocation to lock.


### -field Flags

A set of flags to pass to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtlock2.md">Lock2</a> kernel function which will determine how the allocation is locked. See <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddicb_lock2flags.md">D3DDDICB_LOCK2FLAGS</a> for details.


### -field pData

A CPU virtual address pointing a valid memory location pointing to the CPU backing store or the GPU frame buffer.

