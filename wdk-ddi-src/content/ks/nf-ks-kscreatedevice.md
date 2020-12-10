---
UID: NF:ks.KsCreateDevice
title: KsCreateDevice function (ks.h)
description: The KsCreateDevice function creates an AVStream device.
old-location: stream\kscreatedevice.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsCreateDevice function"]
ms.keywords: KsCreateDevice, KsCreateDevice function [Streaming Media Devices], avfunc_3a0ddeb1-7ea0-4e10-bc98-d761bbc5c2f4.xml, ks/KsCreateDevice, stream.kscreatedevice
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KsCreateDevice
 - ks/KsCreateDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsCreateDevice
---

# KsCreateDevice function


## -description

The<b> KsCreateDevice </b>function creates an AVStream device.

## -parameters

### -param DriverObject 

[in]
A pointer to the WDM driver object of the minidriver.

### -param PhysicalDeviceObject 

[in]
A pointer to the WDM physical device object for the device you want to create under AVStream.

### -param Descriptor 

[in, optional]
A pointer to a device descriptor that describes the characteristics of the device being created. If the caller does not specify this optional parameter, AVStream creates a device with default characteristics and no associated filter factories.

### -param ExtensionSize 

[in]
This parameter contains the size of the device extension. If this is zero, the default extension size is used. If not, it must be at least sizeof (KSDEVICE_HEADER).

### -param Device 

[out, optional]
A pointer to a memory location that contains the address of the created <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a> structure. Optional.

## -returns

Returns STATUS_SUCCESS if the device is created successfully. Otherwise, it returns an appropriate error code.

## -remarks

Normally, the minidriver does not call this function directly. Instead, <b>KsCreateDevice</b> is called by the default <i>AddDevice</i> handler, <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksadddevice">KsAddDevice</a>. Because <b>KsAddDevice</b> makes an internal call to <b>KsCreateDevice</b>, drivers that call <b>KsCreateDevice</b> should not call <b>KsAddDevice</b> separately.

A minidriver that calls <b>KsCreateDevice</b> directly should not use <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksinitializedriver">KsInitializeDriver</a>. If the minidriver is not calling <b>KsInitializeDriver</b>, it should instead provide its own <i>AddDevice</i> callback. The minidriver can then call <b>KsCreateDevice</b> from that <i>AddDevice</i> callback. 

If no <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice_descriptor">KSDEVICE_DESCRIPTOR</a> is provided, AVStream creates a device with the default characteristics and no associated filter factories. If a KSDEVICE_DESCRIPTOR is supplied and contains a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice_dispatch">KSDEVICE_DISPATCH</a> table with a create dispatch, the create dispatch is called.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice_descriptor">KSDEVICE_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice_dispatch">KSDEVICE_DISPATCH</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksadddevice">KsAddDevice</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksinitializedevice">KsInitializeDevice</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksinitializedriver">KsInitializeDriver</a>
