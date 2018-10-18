---
UID: NS:ks._KSPIN_DISPATCH
title: "_KSPIN_DISPATCH"
author: windows-driver-content
description: The KSPIN_DISPATCH structure describes the callbacks for which clients can register in order to receive notification of pin events.
old-location: stream\kspin_dispatch.htm
tech.root: stream
ms.assetid: 6c4aea1f-e788-49c7-91c0-831c87c6fd39
ms.date: 04/23/2018
ms.keywords: "*PKSPIN_DISPATCH, KSPIN_DISPATCH, KSPIN_DISPATCH structure [Streaming Media Devices], PKSPIN_DISPATCH, PKSPIN_DISPATCH structure pointer [Streaming Media Devices], _KSPIN_DISPATCH, avstruct_2ef1e08b-327f-476c-9c0b-804582f67815.xml, ks/KSPIN_DISPATCH, ks/PKSPIN_DISPATCH, stream.kspin_dispatch"
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
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
-	ks.h
api_name:
-	KSPIN_DISPATCH
product:
- Windows
targetos: Windows
req.typenames: KSPIN_DISPATCH, *PKSPIN_DISPATCH
---

# _KSPIN_DISPATCH structure


## -description


The KSPIN_DISPATCH structure describes the callbacks for which clients can register in order to receive notification of pin events.


## -struct-fields




### -field Create

A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff556334">AVStrMiniPinCreate</a> callback routine. Optional. Can be <b>NULL</b>.


### -field Close

A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff556329">AVStrMiniPinClose</a> callback routine. Optional. Can be <b>NULL</b>.


### -field Process

A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff556351">AVStrMiniPinProcess</a> callback routine. Optional. Can be <b>NULL</b>.


### -field Reset

A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff556354">AVStrMiniPinReset</a> callback routine. Optional. Can be <b>NULL</b>.


### -field SetDataFormat

A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff556355">AVStrMiniPinSetDataFormat</a> callback routine. Optional. Can be <b>NULL</b>.


### -field SetDeviceState

A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff556359">AVStrMiniPinSetDeviceState</a> callback routine. Optional. Can be <b>NULL</b>.


### -field Connect

A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff556332">AVStrMiniPinConnect</a> callback routine. Optional. Can be <b>NULL</b>.


### -field Disconnect

A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff556337">AVStrMiniPinDisconnect</a> callback routine. Optional. Can be <b>NULL</b>.


### -field Clock

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561017">KSCLOCK_DISPATCH</a> structure. Specify this member for a pin that exposes a clock. Optional. Can be <b>NULL</b>.


### -field Allocator

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560976">KSALLOCATOR_DISPATCH</a> structure. Specify this member for a pin that is capable of performing kernel-level allocation. Optional. Can be <b>NULL</b>.


## -remarks



Any of the callback pointers can be <b>NULL</b>, indicating that the minidriver does not require to receive notification for this particular dispatch.

If the minidriver needs to determine whether it has been signaled to go to a specific state (for example KSSTATE_RUN), comparing the value of the <b>DeviceState</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> to <b>KSSTATE_RUN</b> is not a reliable method of doing this. <b>DeviceState</b> refers to the state to which the pin has been signaled to go, not the pipe. To perform the above reliably, instead create a variable in the <b>SetDeviceState</b> callback of this structure and then check this variable to make the determination.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560976">KSALLOCATOR_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561017">KSCLOCK_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561025">KsCompletePendingRequest</a>
 

 

