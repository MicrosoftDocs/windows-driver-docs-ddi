---
UID: NF:ks.KsDeviceRegisterAdapterObject
title: KsDeviceRegisterAdapterObject function (ks.h)
description: The KsDeviceRegisterAdapterObject function registers a DMA adapter object with AVStream for performing scatter/gather DMA on the specified device. All drivers compiled for Win64 should use IKsDeviceFunctions::RegisterAdapterObjectEx instead.
tech.root: stream
ms.date: 01/04/2023
keywords: ["KsDeviceRegisterAdapterObject function"]
ms.keywords: KsDeviceRegisterAdapterObject, KsDeviceRegisterAdapterObject function [Streaming Media Devices], avfunc_59ad20f2-ca31-4fbb-808e-48df3a0c87a8.xml, ks/KsDeviceRegisterAdapterObject, stream.ksdeviceregisteradapterobject
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KsDeviceRegisterAdapterObject
 - ks/KsDeviceRegisterAdapterObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsDeviceRegisterAdapterObject
---

## -description

The **KsDeviceRegisterAdapterObject** function registers a DMA adapter object with AVStream for performing scatter/gather DMA on the specified device. All drivers compiled for Win64 should use [IKsDeviceFunctions::RegisterAdapterObjectEx](./nf-ks-iksdevicefunctions-registeradapterobjectex.md) instead.

## -parameters

### -param Device [in]

A pointer to the [KSDEVICE](./ns-ks-_ksdevice.md) structure representing the AVStream device for which to register an adapter object.

### -param AdapterObject [in]

A pointer to the [DMA_ADAPTER](../wdm/ns-wdm-_dma_adapter.md) structure returned by [IoGetDmaAdapter](../wdm/nf-wdm-iogetdmaadapter.md) that represents the DMA controller..

### -param MaxMappingsByteCount [in]

This parameter specifies the maximum number of bytes that the device can handle for a single mapping. Allows AVStream to automatically break up large chunks of contiguous physical memory into multiple scatter/gather elements for devices that impose a size limit on individual mappings in DMA transfers. Breaks are not guaranteed to occur on page boundaries.

### -param MappingTableStride [in]

This parameter specifies how many bytes each entry in the mapping table requires. This must be at least **sizeof** ([KSMAPPING](./ns-ks-_ksmapping.md)) and can be as large as necessary.

Additional space can be used by the minidriver as context information.

## -remarks

A minidriver that calls **KsDeviceRegisterAdapterObject** is responsible for previously acquiring the adapter object through [IoGetDmaAdapter](../wdm/nf-wdm-iogetdmaadapter.md).

Also note that if the minidriver specifies the KSPIN_FLAG_GENERATE_MAPPINGS flag for any pin on any filter on the device, the minidriver must call **KsDeviceRegisterAdapterObject** before processing any data. More information about this flag can be found in the reference page for [KSPIN_DESCRIPTOR_EX](./ns-ks-_kspin_descriptor_ex.md). Also see [AVStream DMA Services](/windows-hardware/drivers/stream/avstream-dma-services).

If you set *MaxMappingByteCount* to one physical page in length, mappings are not guaranteed to reside on a single physical page. In addition, as noted in the member description above, setting *MaxMappingsByteCount* does not guarantee that breaks will occur on page boundaries. If you require breaks on page boundaries, consider not specifying a limit on mapping sizes; instead, break the returned scatter/gather mappings into page-aligned chunks manually.

Also see [Supporting DMA in 64-Bit AVStream Drivers](/windows-hardware/drivers/stream/supporting-dma-in-64-bit-avstream-drivers).

## -see-also

[IoGetDmaAdapter](../wdm/nf-wdm-iogetdmaadapter.md)

[KSFILTER_DESCRIPTOR](./ns-ks-_ksfilter_descriptor.md)

[KSMAPPING](./ns-ks-_ksmapping.md)

[KSPIN_DESCRIPTOR_EX](./ns-ks-_kspin_descriptor_ex.md)
