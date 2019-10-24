---
UID: NS:d3dkmthk._D3DKMT_OPENRESOURCEFROMNTHANDLE
title: _D3DKMT_OPENRESOURCEFROMNTHANDLE (d3dkmthk.h)
description: Describes information that is required to open a shared resource from an NT handle to the process. The shared resource can be a set of allocations, a keyed mutex, or a synchronization object.
old-location: display\d3dkmt_openresourcefromnthandle.htm
ms.assetid: 3f595816-29b5-4efc-a00c-77597dd9fa48
ms.date: 05/10/2018
ms.keywords: D3DKMT_OPENRESOURCEFROMNTHANDLE, D3DKMT_OPENRESOURCEFROMNTHANDLE structure [Display Devices], _D3DKMT_OPENRESOURCEFROMNTHANDLE, d3dkmthk/D3DKMT_OPENRESOURCEFROMNTHANDLE, display.d3dkmt_openresourcefromnthandle
ms.topic: struct
f1_keywords:
 - "d3dkmthk/D3DKMT_OPENRESOURCEFROMNTHANDLE"
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
- D3DKMT_OPENRESOURCEFROMNTHANDLE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_OPENRESOURCEFROMNTHANDLE
---

# _D3DKMT_OPENRESOURCEFROMNTHANDLE structure


## -description


Describes information that is required to open a shared resource from an NT handle to the process. The shared resource can be a set of allocations, a keyed mutex, or a synchronization object.


## -struct-fields




### -field hDevice

[in] A D3DKMT_HANDLE data type that represents the device.


### -field hNtHandle

[in] An NT handle to the process.


### -field NumAllocations

[in] The number of allocations associated with the resource.


### -field pOpenAllocationInfo2

[in] This member is reserved and should be set to zero.


### -field PrivateRuntimeDataSize

[in] The size, in bytes, of the buffer pointed to by the <b>pPrivateRuntimeData</b> member.


### -field pPrivateRuntimeData

[in] A caller-supplied buffer where the runtime private data associated with this resource will be copied to.


### -field ResourcePrivateDriverDataSize

[in] The size, in bytes, of the  buffer pointed to by the <b>pResourcePrivateDriverData</b> member.


### -field pResourcePrivateDriverData

[in] A caller-supplied buffer where the driver private data associated with the resource will be copied to.


### -field TotalPrivateDriverDataBufferSize

[in] The size, in bytes, of the buffer pointed to by the <b>pTotalPrivateDriverDataBuffer</b> member.

[out] The size, in bytes, of  the data written to <b>pTotalPrivateDriverDataBuffer</b>.


### -field pTotalPrivateDriverDataBuffer

[in] A pointer to a caller-supplied buffer where the driver private data will be stored.


### -field hResource

[out] A handle to the resource in this process.


### -field hKeyedMutex

[out] A handle to the keyed mutex in this process.


### -field pKeyedMutexPrivateRuntimeData

[in] A buffer that contains initial private data.

The data in this buffer will be copied only if the keyed mutex does not already have private data.

If this member has a value of <b>NULL</b>, the value of the <b>KeyedMutexPrivateRuntimeDataSize</b> member must be zero.


### -field KeyedMutexPrivateRuntimeDataSize

[in] The size, in bytes, of the buffer pointed to by the <b>pKeyedMutexPrivateRuntimeData</b> member.


### -field hSyncObject

[out] A handle to the synchronization object in this process.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/display/d3dddi-openallocationinfo2">D3DDDI_OPENALLOCATIONINFO2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopennthandlefromname">D3DKMTOpenNtHandleFromName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtshareobjects">D3DKMTShareObjects</a>
 

 

