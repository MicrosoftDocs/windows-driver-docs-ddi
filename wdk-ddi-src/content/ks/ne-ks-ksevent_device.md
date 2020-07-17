---
UID: NE:ks.__unnamed_enum_30
title: KSEVENT_DEVICE (ks.h)
description: Specifies event notifications that the driver generates to indicate that a device has been lost or preempted.
old-location: stream\ksevent_device.htm
tech.root: stream
ms.assetid: 92594bdd-a458-4262-ac4c-013cffb7a725
ms.date: 04/23/2018
keywords: ["KSEVENT_DEVICE enumeration"]
ms.keywords: KSEVENT_DEVICE, KSEVENT_DEVICE enumeration [Streaming Media Devices], KSEVENT_DEVICE_LOST, KSEVENT_DEVICE_PREEMPTED, ks/KSEVENT_DEVICE, ks/KSEVENT_DEVICE_LOST, ks/KSEVENT_DEVICE_PREEMPTED, stream.ksevent_device
f1_keywords:
 - "ks/KSEVENT_DEVICE"
 - "KSEVENT_DEVICE"
req.header: ks.h
req.include-header: Ks.h
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
- Ks.h
api_name:
- KSEVENT_DEVICE
product:
- Windows
targetos: Windows
req.typenames: KSEVENT_DEVICE
---

# KSEVENT_DEVICE enumeration


## -description


Specifies event notifications that the driver generates to indicate that a device has been lost or preempted.


## -enum-fields




### -field KSEVENT_DEVICE_LOST

A camera device has been removed from the system. See <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksevent-device-lost">KSEVENT_DEVICE_LOST</a>.


### -field KSEVENT_DEVICE_PREEMPTED

A camera device has been preempted by a new Windows app. See <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksevent-device-preempted">KSEVENT_DEVICE_PREEMPTED</a>.


### -field KSEVENT_DEVICE_THERMAL_HIGH


### -field KSEVENT_DEVICE_THERMAL_LOW




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksevent-device-lost">KSEVENT_DEVICE_LOST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksevent-device-preempted">KSEVENT_DEVICE_PREEMPTED</a>
 

 

