---
UID: NF:ks.KsInitializeDriver
title: KsInitializeDriver function (ks.h)
description: The KsInitializeDriver function initializes the driver object of an AVStream minidriver.
tech.root: stream
ms.date: 07/13/2022
keywords: ["KsInitializeDriver function"]
ms.keywords: KsInitializeDriver, KsInitializeDriver function [Streaming Media Devices], avfunc_2a16bc8c-a92a-4792-8007-29735a19f806.xml, ks/KsInitializeDriver, stream.ksinitializedriver
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
 - KsInitializeDriver
 - ks/KsInitializeDriver
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsInitializeDriver
---

## -description

The **KsInitializeDriver** function initializes the driver object of an AVStream minidriver.

## -parameters

### -param DriverObject [in]

A pointer to the [DRIVER_OBJECT](/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object) structure for the AVStream driver being initialized. Minidrivers that call **KsInitializeDriver** should use the driver object passed to **DriverEntry** by the operating system.

### -param RegistryPathName [in]

A pointer to a Unicode string containing the registry path string passed into the minidriver's **DriverEntry** function by the operating system.

### -param Descriptor [in, optional]

A pointer to a [KSDEVICE_DESCRIPTOR](/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice_descriptor) structure that specifies the characteristics of the device being initialized. If this pointer is **NULL**, a device is created with default characteristics and no associated filter factories.

## -returns

**KsInitializeDriver** returns STATUS_SUCCESS or an appropriate error code as returned by [IoCreateDevice](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatedevice) or internal AVStream device initialization routines.

## -remarks

This function is typically called from **DriverEntry**. If the minidriver passes in a device descriptor, AVStream creates a device with the specified characteristics at **AddDevice** time. Minidrivers that perform device initialization themselves do not necessarily need to call **KsInitializeDriver**.  For more information, see [Initializing an AVStream Minidriver](/windows-hardware/drivers/stream/initializing-an-avstream-minidriver).

## -see-also

[DEVICE_OBJECT](/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object)

[DRIVER_OBJECT](/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object)

[DriverEntry of AVStream](/previous-versions/ff558721(v=vs.85))

[IoCreateDevice](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatedevice)

[KSDEVICE_DESCRIPTOR](/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice_descriptor)

[KSDEVICE_DISPATCH](/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice_dispatch)

[KSFILTER_DESCRIPTOR](/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_descriptor)

[KsInitializeDevice](/windows-hardware/drivers/ddi/ks/nf-ks-ksinitializedevice)
