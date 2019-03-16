---
UID: NS:ks._KSDEVICE_DISPATCH
title: _KSDEVICE_DISPATCH (ks.h)
description: The KSDEVICE_DISPATCH structure describes the callbacks that a client can provide to receive notification of device creation and PnP events.
old-location: stream\ksdevice_dispatch.htm
tech.root: stream
ms.assetid: 1ae7af1d-5e1c-4728-82c5-efc8d60b5df6
ms.date: 04/23/2018
ms.keywords: "*PKSDEVICE_DISPATCH, KSDEVICE_DISPATCH, KSDEVICE_DISPATCH structure [Streaming Media Devices], PKSDEVICE_DISPATCH, PKSDEVICE_DISPATCH structure pointer [Streaming Media Devices], _KSDEVICE_DISPATCH, avstruct_7ceb03b7-6973-46bd-ad3e-32fdce7f4f11.xml, ks/KSDEVICE_DISPATCH, ks/PKSDEVICE_DISPATCH, stream.ksdevice_dispatch"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- KSDEVICE_DISPATCH
product:
- Windows
targetos: Windows
req.typenames: KSDEVICE_DISPATCH, *PKSDEVICE_DISPATCH
---

# _KSDEVICE_DISPATCH structure


## -description


The KSDEVICE_DISPATCH structure describes the callbacks that a client can provide to receive notification of device creation and PnP events.


## -struct-fields




### -field Add

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff554276">AVStrMiniDeviceAdd</a> callback routine.


### -field Start

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff556297">AVStrMiniDeviceStart</a> callback routine.


### -field PostStart

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff554284">AVStrMiniDevicePostStart</a> callback routine.


### -field QueryStop

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff554299">AVStrMiniDeviceQueryStop</a> callback routine.


### -field CancelStop

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff554281">AVStrMiniDeviceCancelStop</a> callback routine.


### -field Stop

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff556301">AVStrMiniDeviceStop</a> callback routine.


### -field QueryRemove

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff554297">AVStrMiniDeviceQueryRemove</a> callback routine.


### -field CancelRemove

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff554278">AVStrMiniDeviceCancelRemove</a> callback routine.


### -field Remove

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff554305">AVStrMiniDeviceRemove</a> callback routine.


### -field QueryCapabilities

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff554285">AVStrMiniDeviceQueryCapabilities</a> callback routine.


### -field SurpriseRemoval

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff556304">AVStrMiniDeviceSurpriseRemoval</a> callback routine.


### -field QueryPower

Optional. can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff554293">AVStrMiniDeviceQueryPower</a> callback routine.


### -field SetPower

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff554309">AVStrMiniDeviceSetPower</a> callback routine.


### -field QueryInterface

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff554290">AVStrMiniDeviceQueryInterface</a> callback routine.


## -remarks



In describing a device with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561691">KSDEVICE_DESCRIPTOR</a> structure, clients include a pointer to a dispatch table defined by this structure. Any member of this structure may be <b>NULL</b> indicating that the minidriver receives no notification for that particular message.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561691">KSDEVICE_DESCRIPTOR</a>
 

 

