---
UID: NS:strmini._HW_INITIALIZATION_DATA
title: "_HW_INITIALIZATION_DATA"
author: windows-driver-content
description: The HW_INITIALIZATION_DATA structure specifies the basic information the class driver needs to begin initializing the minidriver.
old-location: stream\hw_initialization_data.htm
old-project: stream
ms.assetid: 5be9ba51-bd6c-4650-9c48-f89267a2ac16
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PHW_INITIALIZATION_DATA, HW_INITIALIZATION_DATA, HW_INITIALIZATION_DATA structure [Streaming Media Devices], PHW_INITIALIZATION_DATA, PHW_INITIALIZATION_DATA structure pointer [Streaming Media Devices], _HW_INITIALIZATION_DATA, _HW_INITIALIZATION_DATA structure [Streaming Media Devices], strclass-struct_7c987d6a-732c-4de9-b98a-b68873458c41.xml, stream.hw_initialization_data, strmini/HW_INITIALIZATION_DATA, strmini/PHW_INITIALIZATION_DATA"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: strmini.h
req.include-header: Strmini.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	strmini.h
api_name:
-	HW_INITIALIZATION_DATA
product: Windows
targetos: Windows
req.typenames: HW_INITIALIZATION_DATA, *PHW_INITIALIZATION_DATA
req.product: Windows 10 or later.
---

# _HW_INITIALIZATION_DATA structure


## -description


The HW_INITIALIZATION_DATA structure specifies the basic information the class driver needs to begin initializing the minidriver. The minidriver passes an HW_INITIALIZATION_DATA structure to the class driver when it registers itself by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff568263">StreamClassRegisterMinidriver</a>.


## -struct-fields




### -field SizeOfThisPacket

 


### -field StreamClassVersion

 


### -field HwInitializationDataSize

Specifies the size of this data structure, in bytes.


### -field HwInterrupt

Points to the minidriver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568459">StrMiniInterrupt</a> routine.


### -field HwReceivePacket

Points to the minidriver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568463">StrMiniReceiveDevicePacket</a> routine.


### -field HwCancelPacket

Points to the minidriver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568448">StrMiniCancelPacket</a> routine.


### -field HwRequestTimeoutHandler

Points to the minidriver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568473">StrMiniRequestTimeout</a> routine.


### -field DeviceExtensionSize

Specifies the size in bytes of the buffer the class driver should allocate for the minidriver's device extension. The minidriver may use this buffer to record private information. The class driver passes pointers to this buffer in the <b>HwDeviceExtension</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff559697">HW_STREAM_OBJECT</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff559702">HW_STREAM_REQUEST_BLOCK</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff559706">HW_TIME_CONTEXT</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff567785">PORT_CONFIGURATION_INFORMATION</a> structures it passes to the minidriver.


### -field PerRequestExtensionSize

Specifies the size in bytes of the buffer the class driver should allocate for the buffer pointed to by <b>SRBExtension</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff559702">HW_STREAM_REQUEST_BLOCK</a> structures it passes to the minidriver. The class driver will allocate one buffer for each HW_STREAM_REQUEST_BLOCK.


### -field PerStreamExtensionSize

Specifies the size in bytes of the buffer the class driver should allocate for the buffer pointed to by the <b>HwStreamExtension</b> member of a stream's <a href="https://msdn.microsoft.com/library/windows/hardware/ff559697">HW_STREAM_OBJECT</a>. The class driver will allocate one buffer for each stream.


### -field FilterInstanceExtensionSize

Specifies the size in bytes of the buffer the class extension should allocate for the buffer pointed to by the <b>HwInstanceExtension</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff559702">HW_STREAM_REQUEST_BLOCK</a> structures it passes to the minidriver. The class driver allocates one buffer for each instance of the minidriver.


### -field BusMasterDMA

If <b>TRUE</b>, the device can perform direct bus-master DMA to the minidriver's DMA buffer.


### -field Dma24BitAddresses

Minidrivers should set this to <b>TRUE</b> if the DMA hardware the devices uses can access only the lower 24 bits of the address space.


### -field BufferAlignment

Specifies the alignment requirement, in bytes, for DMA buffers. For example, a value of 4 indicates the DMA buffers should be aligned on 4-byte boundaries.


### -field TurnOffSynchronization

If <b>TRUE</b>, the minidriver will handle its own synchronization; otherwise the class driver handles synchronization. Most minidrivers should set this value to <b>FALSE</b>. See <a href="https://msdn.microsoft.com/2f560e7a-4717-4b3f-9513-e34fcb2b5e6c">Minidriver Synchronization</a> in the <i>Streaming Minidriver Design Guide</i> for more information.


### -field DmaBufferSize

Specifies the size in bytes of the DMA buffer the class driver should allocate for the minidriver. The minidriver gets a pointer to this buffer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff568243">StreamClassGetDmaBuffer</a>. The class driver allocates contiguous nonpageable memory that will not be available to the operating system, or to other drivers, so this value should be as small as possible.


### -field NumNameExtensions

 


### -field NameExtensionArray

 


### -field Reserved

Reserved for system use. Minidrivers should ignore this member.

