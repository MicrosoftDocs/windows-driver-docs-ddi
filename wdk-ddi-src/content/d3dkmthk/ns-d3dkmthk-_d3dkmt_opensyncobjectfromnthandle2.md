---
UID: NS:d3dkmthk._D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2
title: "_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2"
author: windows-driver-content
description: D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 is used with D3DKMTOpenSyncObjectFromNtHandle2 to open a monitored fence object.
old-location: display\d3dkmt_opensyncobjectfromnthandle2.htm
old-project: display
ms.assetid: 7C5F9ACF-AA21-4A2B-B943-3B1D940284E1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2, D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 structure [Display Devices], _D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2, d3dkmthk/D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2, display.d3dkmt_opensyncobjectfromnthandle2
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmthk.h
api_name:
-	D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2
product: Windows
targetos: Windows
req.typenames: D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2
---

# _D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 structure


## -description


<b>D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2</b> is used with <a href="https://msdn.microsoft.com/library/windows/hardware/dn906778">D3DKMTOpenSyncObjectFromNtHandle2</a> to open a monitored fence object.


## -struct-fields




### -field hNtHandle

[in] NT handle for the sync object to be opened.


### -field hDevice

[in] Device handle to use this sync object on.


### -field Flags

[in] Specifies the desired sync object behavior for this device, such as wait and signal semantics and TDR handling.


### -field hSyncObject

[out] Handle to the sync object that can be used in this process.


### -field MonitoredFence

Contains sync object virtual addresses that can be used in this process.


### -field MonitoredFence.FenceValueCPUVirtualAddress

[out] A read-only mapping of the fence value for the CPU. This is a user mode address readable from the process that created the monitored fence object. For 32 bit platforms that support 64 bit atomic reads via methods such as <code>InterlockedCompareExchange64(pointer,0,0)</code>, the mapping will be made read-write instead of read-only to avoid an access violation during the interlocked operation. Depending on the value of <b>No64BitAtomics</b> cap, this address points to either a 32 bit or a 64 bit underlying value.


### -field MonitoredFence.FenceValueGPUVirtualAddress

[out] A read-write mapping of the fence value for the GPU. A driver can signal a new fence value by inserting a GPU write command for this address into a command buffer, and the DirectX graphics  kernel will unblock waiters for this fence object value. This GPU virtual address is mapped asynchronously, and the driver should wait for the device that opened or created the monitored fence synchronization object to reach <b>PagingFenceValue</b> on its paging fence object prior to accessing this GPU virtual address. Depending on the value of <b>No64BitAtomics</b> cap, this address points to either a 32 bit or a 64 bit underlying value.


### -field MonitoredFence.EngineAffinity

[in] A bit field, where each bit position (starting from zero) defines a physical adapter index in an linked display adapter link where the GPU virtual address will be committed. Zero means that GPU virtual address will be committed to all physical adapters.


#### - Reserved

The consolidated value of the <b>MonitoredFence</b> structure.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906778">D3DKMTOpenSyncObjectFromNtHandle2</a>
 

 

