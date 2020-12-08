---
UID: NF:strmini.StreamClassRegisterFilterWithNoKSPins
title: StreamClassRegisterFilterWithNoKSPins function (strmini.h)
description: The StreamClassRegisterFilterWithNoKSPins routine is used to register filter drivers with Microsoft DirectShow that have no kernel streaming pins and, therefore, do not stream in kernel mode.
old-location: stream\streamclassregisterfilterwithnokspins.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["StreamClassRegisterFilterWithNoKSPins function"]
ms.keywords: StreamClassRegisterFilterWithNoKSPins, StreamClassRegisterFilterWithNoKSPins routine [Streaming Media Devices], strclass-routines_d338a3be-7760-46b6-aeba-e9cbac45afe3.xml, stream.streamclassregisterfilterwithnokspins, strmini/StreamClassRegisterFilterWithNoKSPins
req.header: strmini.h
req.include-header: Strmini.h
req.target-type: Desktop
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
req.lib: Stream.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - StreamClassRegisterFilterWithNoKSPins
 - strmini/StreamClassRegisterFilterWithNoKSPins
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Stream.lib
 - Stream.dll
api_name:
 - StreamClassRegisterFilterWithNoKSPins
---

# StreamClassRegisterFilterWithNoKSPins function


## -description

The <b>StreamClassRegisterFilterWithNoKSPins</b> routine is used to register filter drivers with Microsoft DirectShow that have no kernel streaming pins and, therefore, do not stream in kernel mode.

## -parameters

### -param DeviceObject 

[in]
Points to the driver's device object.

### -param InterfaceClassGUID 

[in]
Specifies the interface class GUID to register.

### -param PinCount 

[in]
Specifies the number of pins on the filter.

### -param PinDirection 

[in]
Specifies a <i>PinCount</i>-sized array of Boolean values, one for each pin on the filter. The values indicate the pin direction for each pin. If <b>TRUE</b>, this pin is an output pin. If <b>FALSE</b>, the pin is an input pin.

### -param MediumList 

[in]
Specifies a <i>PinCount</i>-sized array of <a href="/previous-versions/ff563538(v=vs.85)">KSPIN_MEDIUM</a> structures, one for each pin on the filter.

### -param CategoryList 

[in, optional]
If non-NULL, specifies an array of pin category GUIDs, one for each pin on the filter.

## -returns

Returns STATUS_SUCCESS on success, or the appropriate error code on failure.

## -see-also

<a href="/previous-versions/ff563538(v=vs.85)">KSPIN_MEDIUM</a>
