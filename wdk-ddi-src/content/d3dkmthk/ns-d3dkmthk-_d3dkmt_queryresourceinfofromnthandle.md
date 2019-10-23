---
UID: NS:d3dkmthk._D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE
title: _D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE (d3dkmthk.h)
description: Describes information that is required to map a global NT handle to resource information.
old-location: display\d3dkmt_queryresourceinfofromnthandle.htm
ms.assetid: 098fe3b9-1169-4ff6-8822-0eb277cb73f9
ms.date: 05/10/2018
ms.keywords: D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE, D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE structure [Display Devices], _D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE, d3dkmthk/D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE, display.d3dkmt_queryresourceinfofromnthandle
ms.topic: struct
f1_keywords:
 - "d3dkmthk/D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE"
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
- D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE
---

# _D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE structure


## -description


Describes information that is required to map a global NT handle to resource information.


## -struct-fields




### -field hDevice

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the device.


### -field hNtHandle

[in] A global NT handle to the resource that is to be queried.


### -field pPrivateRuntimeData

[in] A pointer to a caller-supplied buffer where the runtime private data associated with the resource will be copied to.


### -field PrivateRuntimeDataSize

[in] The size, in bytes, of the buffer pointed to by the <b>pPrivateRuntimeData</b> member.

[out] If <b>pPrivateRuntimeData</b> is <b>NULL</b>, this member is the size, in bytes, of the buffer required to receive the runtime private data. Otherwise, this member is the size, in bytes, of runtime private data copied into the buffer.


### -field TotalPrivateDriverDataSize

[out] The size, in bytes, of the buffer that is required to hold all the driver private data for all allocations associated with the resource.


### -field ResourcePrivateDriverDataSize

[out] The size, in bytes, of the driver's resource private data.


### -field NumAllocations

[out] The number of allocations associated with the resource.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtqueryresourceinfofromnthandle">D3DKMTQueryResourceInfoFromNtHandle</a>
 

 

