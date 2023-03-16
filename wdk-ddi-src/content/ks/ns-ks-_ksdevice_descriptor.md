---
UID: NS:ks._KSDEVICE_DESCRIPTOR
title: _KSDEVICE_DESCRIPTOR (ks.h)
description: The KSDEVICE_DESCRIPTOR structure describes the characteristics of a particular device.
tech.root: stream
ms.date: 03/06/2023
keywords: ["KSDEVICE_DESCRIPTOR structure"]
ms.keywords: "*PKSDEVICE_DESCRIPTOR, KSDEVICE_DESCRIPTOR, KSDEVICE_DESCRIPTOR structure [Streaming Media Devices], PKSDEVICE_DESCRIPTOR, PKSDEVICE_DESCRIPTOR structure pointer [Streaming Media Devices], _KSDEVICE_DESCRIPTOR, avstruct_b51d9c2c-278f-4357-b84a-da6959ea9959.xml, ks/KSDEVICE_DESCRIPTOR, ks/PKSDEVICE_DESCRIPTOR, stream.ksdevice_descriptor"
req.header: ks.h
req.include-header: Ks.h
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
targetos: Windows
req.typenames: KSDEVICE_DESCRIPTOR, *PKSDEVICE_DESCRIPTOR
f1_keywords:
 - _KSDEVICE_DESCRIPTOR
 - ks/_KSDEVICE_DESCRIPTOR
 - PKSDEVICE_DESCRIPTOR
 - ks/PKSDEVICE_DESCRIPTOR
 - KSDEVICE_DESCRIPTOR
 - ks/KSDEVICE_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - _KSDEVICE_DESCRIPTOR
 - PKSDEVICE_DESCRIPTOR
 - KSDEVICE_DESCRIPTOR
---

## -description

The **KSDEVICE_DESCRIPTOR** structure describes the characteristics of a particular device.

## -struct-fields

### -field Dispatch

A pointer to the client dispatch table for this device. This dispatch table contains client dispatch functions for PNP messages such as **Add**, **Start**, **Stop**, **Remove**. Clients are not required to supply a dispatch table unless they want to receive callbacks for the PNP messages described in the dispatch table. Any member of the dispatch table can be **NULL** to indicate that the client does not want to receive notification for that particular message. For more information, see [**KSDEVICE_DISPATCH**](./ns-ks-_ksdevice_dispatch.md).

### -field FilterDescriptorsCount

This member contains the number of filter descriptors for this device that will be provided in the **FilterDescriptors** member. Zero is a legal value for this member; clients can create filter factories dynamically with the [KsCreateFilterFactory](./nf-ks-kscreatefilterfactory.md) function instead of statically describing them in the device descriptor.

### -field FilterDescriptors

A pointer to an array of filter descriptors that describe filters that can be created by this device. This member may be **NULL** if **FilterDescriptorsCount** is zero. For more information, see [**KSFILTER_DESCRIPTOR**](./ns-ks-_ksfilter_descriptor.md).

### -field Version

A value of type ULONG. This should be one and only one of the values in the following table, or set to zero if writing a pre-version 0x100 driver.

| Value | Description |
|---|---|
| KSDEVICE_DESCRIPTOR_VERSION | Indicates support of the [AVStrMiniDeviceQueryInterface](/previous-versions/ff554290(v=vs.85)) dispatch of [KSDEVICE_DISPATCH](./ns-ks-_ksdevice_dispatch.md). |
| KSDEVICE_DESCRIPTOR_VERSION_2 | Indicates support of the **Flags** member of KSDEVICE_DESCRIPTOR. |

### -field Flags

A value of type ULONG. There is only one flag currently defined.

| Flag | Description |
|---|---|
| KSDEVICE_FLAG_ENABLE_REMOTE_WAKEUP | Indicates that the device supports remote wakeup. |

### -field Alignment

## -remarks

Most often, this structure is used in conjunction with [KsInitializeDriver](./nf-ks-ksinitializedriver.md) in the client's **DriverEntry** function to initialize the device. This structure is also used to manually initialize or create devices with the [KsInitializeDevice](./nf-ks-ksinitializedevice.md) and [KsCreateDevice](./nf-ks-kscreatedevice.md) functions.

If you set **Version** to KSDEVICE_DESCRIPTOR_VERSION_2 and run your driver on an early version of AVStream that does not support **Flags**, all flags will be considered to be zero.

Similarly, using an earlier version descriptor on later versions of AVStream causes no flags to be specified.

## -see-also

[**KSDEVICE_DISPATCH**](./ns-ks-_ksdevice_dispatch.md)

[**KSFILTER_DESCRIPTOR**](./ns-ks-_ksfilter_descriptor.md)

[KsCreateDevice](./nf-ks-kscreatedevice.md)

[KsInitializeDevice](./nf-ks-ksinitializedevice.md)

[KsInitializeDriver](./nf-ks-ksinitializedriver.md)