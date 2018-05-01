---
UID: NS:hdaudio._HDAUDIO_BUS_INTERFACE_V2
title: "_HDAUDIO_BUS_INTERFACE_V2"
author: windows-driver-content
description: The HDAUDIO_BUS_INTERFACE_V2 structure specifies the information that a client requires to call the routines in the HDAUDIO_BUS_INTERFACE_V2 version of the HD Audio DDI.
old-location: audio\hdaudio_bus_interface_v2.htm
old-project: audio
ms.assetid: 7d639909-dc56-4ec5-b596-bfbbf262a3d9
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*PHDAUDIO_BUS_INTERFACE_V2, HDAUDIO_BUS_INTERFACE_V2, HDAUDIO_BUS_INTERFACE_V2 structure [Audio Devices], PHDAUDIO_BUS_INTERFACE_V2, PHDAUDIO_BUS_INTERFACE_V2 structure pointer [Audio Devices], _HDAUDIO_BUS_INTERFACE_V2, aud-prop2_42a4681c-608a-479b-a33d-725f9625d64b.xml, audio.hdaudio_bus_interface_v2, hdaudio/HDAUDIO_BUS_INTERFACE_V2, hdaudio/PHDAUDIO_BUS_INTERFACE_V2"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hdaudio.h
req.include-header: Hdaudio.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
-	hdaudio.h
api_name:
-	HDAUDIO_BUS_INTERFACE_V2
product: Windows
targetos: Windows
req.typenames: HDAUDIO_BUS_INTERFACE_V2, *PHDAUDIO_BUS_INTERFACE_V2
---

# _HDAUDIO_BUS_INTERFACE_V2 structure


## -description


The HDAUDIO_BUS_INTERFACE_V2 structure specifies the information that a client requires to call the routines in the HDAUDIO_BUS_INTERFACE_V2 version of the HD Audio DDI. The interface represented by this structure provides all the functionality of <a href="https://msdn.microsoft.com/library/windows/hardware/ff536413">HDAUDIO_BUS_INTERFACE</a> and can also support flexible DMA-driven event notification.


## -struct-fields




### -field Size

Specifies the size, in bytes, of the HDAUDIO_BUS_INTERFACE_V2 structure.


### -field Version

Specifies the version of the baseline HD Audio DDI.


### -field Context

A pointer to interface-specific context information.


### -field InterfaceReference

A pointer to a driver-supplied routine that increments the reference count for the interface.


### -field InterfaceDereference

A pointer to a driver-supplied routine that decrements the reference count for the interface.


### -field TransferCodecVerbs

A function pointer to the <a href="https://msdn.microsoft.com/0ba92f5c-c4a3-48de-b8af-9c444b2e65b5">TransferCodecVerbs</a> routine.


### -field AllocateCaptureDmaEngine

A function pointer to the <a href="https://msdn.microsoft.com/038e52be-04db-41c2-aa19-85bc4eb8bc57">AllocateCaptureDmaEngine</a> routine.


### -field AllocateRenderDmaEngine

A function pointer to the <a href="https://msdn.microsoft.com/fb2a64ca-7e8e-4352-86c6-b9500e535c75">AllocateRenderDmaEngine</a> routine.


### -field ChangeBandwidthAllocation

A function pointer to the <a href="https://msdn.microsoft.com/4dcf8fb6-71f5-4e11-a92a-0292c2a1515c">ChangeBandwidthAllocation</a> routine.


### -field AllocateDmaBuffer

A function pointer to the <a href="https://msdn.microsoft.com/44fd988a-24b3-4587-88d9-30585800ffbf">AllocateDmaBuffer</a> routine.


### -field FreeDmaBuffer

A function pointer to the <a href="https://msdn.microsoft.com/658e32d2-40e2-4479-8212-df7140fe6b74">FreeDmaBuffer</a> routine.


### -field FreeDmaEngine

A function pointer to the <a href="https://msdn.microsoft.com/3f068ac0-2b18-4242-86de-7044ce558788">FreeDmaEngine</a> routine.


### -field SetDmaEngineState

A function pointer to the <a href="https://msdn.microsoft.com/05cfb827-e143-4d77-b378-e02dd381e429">SetDmaEngineState</a> routine.


### -field GetWallClockRegister

A function pointer to the <a href="https://msdn.microsoft.com/4efe4b23-eb4f-4170-8d73-05cae2ba21c2">GetWallClockRegister</a> routine.


### -field GetLinkPositionRegister

A function pointer to the <a href="https://msdn.microsoft.com/8b8c7f61-c22a-421f-999f-291999bb243f">GetLinkPositionRegister</a> routine.


### -field RegisterEventCallback

A function pointer to the <a href="https://msdn.microsoft.com/0f94146b-aa60-4106-aba6-0f1cb3e53008">RegisterEventCallback</a> routine.


### -field UnregisterEventCallback

A function pointer to the <a href="https://msdn.microsoft.com/698017a0-13d5-4ed5-a1ce-1a50a62135e0">UnregisterEventCallback</a> routine.


### -field GetDeviceInformation

A function pointer to the <a href="https://msdn.microsoft.com/bdd08133-0641-4eea-bfa3-75f700356132">GetDeviceInformation</a> routine.


### -field GetResourceInformation

A function pointer to the <a href="https://msdn.microsoft.com/ba1f0fa2-77dd-4ec3-86c8-c5d74465743f">GetResourceInformation</a> routine.


### -field AllocateDmaBufferWithNotification

A function pointer to the <a href="https://msdn.microsoft.com/c74b5969-35d4-45db-b631-31e00572107d">AllocateDmaBufferWithNotification</a> routine.


### -field FreeDmaBufferWithNotification

A function pointer to the <a href="https://msdn.microsoft.com/98fc6201-d9b4-4c85-b624-011f360df068">FreeDmaBufferWithNotification</a> routine.


### -field RegisterNotificationEvent

A function pointer to the <a href="https://msdn.microsoft.com/44702d79-80ac-411f-ae47-bf60b9cb541d">RegisterNotificationEvent</a> routine.


### -field UnregisterNotificationEvent

A function pointer to the <a href="https://msdn.microsoft.com/525e2dd9-68e1-468d-895e-d9f57372d619">UnregisterNotificationEvent</a> routine.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> IOCTL uses this structure to provide interface information to a client that is querying the HD Audio bus driver for the HD Audio DDI.

The names and definitions of the first five members of the <b>HDAUDIO_BUS_INTERFACE_V2</b> structure (Size, Version, Context, InterfaceReference, and InterfaceDereference) are the same as in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn895657">INTERFACE</a> structure. The remaining members are specific to the baseline HD Audio DDI and specify function pointers to the routines in the DDI. 




## -see-also




<a href="https://msdn.microsoft.com/038e52be-04db-41c2-aa19-85bc4eb8bc57">AllocateCaptureDmaEngine</a>



<a href="https://msdn.microsoft.com/44fd988a-24b3-4587-88d9-30585800ffbf">AllocateDmaBuffer</a>



<a href="https://msdn.microsoft.com/c74b5969-35d4-45db-b631-31e00572107d">AllocateDmaBufferWithNotification</a>



<a href="https://msdn.microsoft.com/fb2a64ca-7e8e-4352-86c6-b9500e535c75">AllocateRenderDmaEngine</a>



<a href="https://msdn.microsoft.com/4dcf8fb6-71f5-4e11-a92a-0292c2a1515c">ChangeBandwidthAllocation</a>



<a href="https://msdn.microsoft.com/658e32d2-40e2-4479-8212-df7140fe6b74">FreeDmaBuffer</a>



<a href="https://msdn.microsoft.com/98fc6201-d9b4-4c85-b624-011f360df068">FreeDmaBufferWithNotification</a>



<a href="https://msdn.microsoft.com/3f068ac0-2b18-4242-86de-7044ce558788">FreeDmaEngine</a>



<a href="https://msdn.microsoft.com/bdd08133-0641-4eea-bfa3-75f700356132">GetDeviceInformation</a>



<a href="https://msdn.microsoft.com/8b8c7f61-c22a-421f-999f-291999bb243f">GetLinkPositionRegister</a>



<a href="https://msdn.microsoft.com/ba1f0fa2-77dd-4ec3-86c8-c5d74465743f">GetResourceInformation</a>



<a href="https://msdn.microsoft.com/4efe4b23-eb4f-4170-8d73-05cae2ba21c2">GetWallClockRegister</a>



<a href="https://msdn.microsoft.com/0f94146b-aa60-4106-aba6-0f1cb3e53008">RegisterEventCallback</a>



<a href="https://msdn.microsoft.com/44702d79-80ac-411f-ae47-bf60b9cb541d">RegisterNotificationEvent</a>



<a href="https://msdn.microsoft.com/05cfb827-e143-4d77-b378-e02dd381e429">SetDmaEngineState</a>



<a href="https://msdn.microsoft.com/0ba92f5c-c4a3-48de-b8af-9c444b2e65b5">TransferCodecVerbs</a>



<a href="https://msdn.microsoft.com/698017a0-13d5-4ed5-a1ce-1a50a62135e0">UnregisterEventCallback</a>



<a href="https://msdn.microsoft.com/525e2dd9-68e1-468d-895e-d9f57372d619">UnregisterNotificationEvent</a>
 

 

