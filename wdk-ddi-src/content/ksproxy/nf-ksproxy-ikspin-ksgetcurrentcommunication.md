---
UID: NF:ksproxy.IKsPin.KsGetCurrentCommunication
title: IKsPin::KsGetCurrentCommunication (ksproxy.h)
description: The KsGetCurrentCommunication method retrieves the current communication direction, interface, and medium of a pin.
tech.root: stream
ms.date: 03/07/2023
keywords: ["IKsPin::KsGetCurrentCommunication"]
ms.keywords: IKsPin interface [Streaming Media Devices],KsGetCurrentCommunication method, IKsPin.KsGetCurrentCommunication, IKsPin::KsGetCurrentCommunication, KsGetCurrentCommunication, KsGetCurrentCommunication method [Streaming Media Devices], KsGetCurrentCommunication method [Streaming Media Devices],IKsPin interface, ksproxy/IKsPin::KsGetCurrentCommunication, ksproxy_2619bbb1-bc7d-4a69-99fb-2e35a36c4f02.xml, stream.ikspin_ksgetcurrentcommunication
req.header: ksproxy.h
req.include-header: Ksproxy.h
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IKsPin::KsGetCurrentCommunication
 - ksproxy/IKsPin::KsGetCurrentCommunication
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ksproxy.h
api_name:
 - IKsPin::KsGetCurrentCommunication
---

## -description

The **KsGetCurrentCommunication** method retrieves the current communication direction, interface, and medium of a pin.

## -parameters

### -param Communication [out, optional]

Pointer to a variable that receives one of the following values from the KSPIN_COMMUNICATION enumerated type describing the current communication direction for a pin:

| Value | Description |
|---|---|
| KSPIN_COMMUNICATION_NONE | The pin factory does not create any pin instances. |
| KSPIN_COMMUNICATION_SINK | The pin factory creates instances of IRP sink pins. Such pins can only be connected to IRP source pins. |
| KSPIN_COMMUNICATION_SOURCE | The pin factory creates instances of IRP source pins. Such pins can only be connected to IRP sink pins. |
| KSPIN_COMMUNICATION_BOTH | The pin factory creates instances of pins that are both IRP sinks and IRP sources. |
| KSPIN_COMMUNICATION_BRIDGE | The pin cannot connect to other pins, but instances may be created on it to receive non-KS I/O requests. |

### -param Interface [out, optional]

Pointer to a variable that receives a [KSPIN_INTERFACE](/windows-hardware/drivers/stream/kspin-interface-structure) structure that describes the current interface for a pin.

### -param Medium [out, optional]

Pointer to a variable that receives a [KSPIN_MEDIUM](/windows-hardware/drivers/stream/kspin-medium-structure) structure that describes the current medium for a pin.

## -returns

Returns NOERROR if successful; otherwise, returns an error code.

## -remarks

Source pins send IRPs to sink pins. Do not confuse the communication direction with data flow direction. (See [KSPROPERTY_PIN_DATAFLOW](/windows-hardware/drivers/stream/ksproperty-pin-dataflow).) A source pin may read or write data, and a sink pin may have data read to it or written from it.

The current communication direction, interface, and medium of a pin are a subset of those available to the pin, and are selected when the pin handle is created.

## -see-also

[KSPIN_INTERFACE](/windows-hardware/drivers/stream/kspin-interface-structure)

[KSPIN_MEDIUM](/windows-hardware/drivers/stream/kspin-medium-structure)

[KSPROPERTY_PIN_DATAFLOW](/windows-hardware/drivers/stream/ksproperty-pin-dataflow)
