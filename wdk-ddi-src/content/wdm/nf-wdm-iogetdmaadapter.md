---
UID: NF:wdm.IoGetDmaAdapter
title: IoGetDmaAdapter function (wdm.h)
description: The IoGetDmaAdapter routine returns a pointer to the DMA adapter structure for a physical device object.
tech.root: kernel
ms.date: 12/12/2022
keywords: ["IoGetDmaAdapter function"]
ms.keywords: IoGetDmaAdapter, IoGetDmaAdapter routine [Kernel-Mode Driver Architecture], k104_36398d16-2a22-4a85-a260-265aa9c54bbd.xml, kernel.iogetdmaadapter, wdm/IoGetDmaAdapter
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoPassive5, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoGetDmaAdapter
 - wdm/IoGetDmaAdapter
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoGetDmaAdapter
---

## -description

The **IoGetDmaAdapter** routine returns a pointer to the DMA adapter structure for a physical device object.

## -parameters

### -param PhysicalDeviceObject [in, optional]

Pointer to the physical device object for the device requesting the DMA adapter structure.

### -param DeviceDescription [in]

Pointer to a [**DEVICE_DESCRIPTION**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_description) structure, which describes the attributes of the physical device. Regardless of the version set in the DEVICE_DESCRIPTION structure, this function always returns `DMA_ADAPTER->Version == 1`.

### -param NumberOfMapRegisters [out]

A pointer to, on output, the maximum number of map registers that the driver can allocate for any DMA transfer operation.

## -returns

**IoGetDmaAdapter** returns a pointer to a [**DMA_ADAPTER**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter) structure, which contains pointers to functions that support system-defined DMA operations. If the structure cannot be allocated, the routine returns **NULL**.  See version comment above in description of *DeviceDescription* parameter.

## -remarks

Before calling this routine, a driver must zero-initialize the [**DEVICE_DESCRIPTION**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_description) structure pointed to by *DeviceDescription* and then add the relevant information for its device to this structure.

On success, the routine's return value points to a **DMA_ADAPTER** structure. This structure contains a pointer to a [**DMA_OPERATIONS**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations) structure, which is a table of pointers to functions that the driver can subsequently use to perform DMA operations. The version of this structure that the routine returns is determined as follows:

- If the driver sets the **Version** member of the **DEVICE_DESCRIPTION** structure to DEVICE_DESCRIPTION_VERSION or DEVICE_DESCRIPTION_VERSION1, the returned **DMA_ADAPTER** structure points to version 1 of the **DMA_OPERATIONS** structure.</li>

- If the driver sets **Version** = DEVICE_DESCRIPTION_VERSION2, the returned **DMA_ADAPTER** structure points to version 2 of the **DMA_OPERATIONS** structure if version 2 is supported; otherwise, the routine returns **NULL**. Drivers must check to see if version 2 is supported before attempting to use any version 2 function.</li>

- If the driver sets **Version** = DEVICE_DESCRIPTION_VERSION3, the returned **DMA_ADAPTER** structure points to version 3 of the **DMA_OPERATIONS** structure if version 3 is supported; otherwise, the routine returns **NULL**. Drivers must check to see if version 3 is supported before attempting to use any version 3 function. Version 3 is supported starting with Windows 8.

A PnP driver calls **IoGetDmaAdapter** when its [AddDevice](/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device) routine is called or when it handles a PnP [IRP_MN_START_DEVICE](/windows-hardware/drivers/kernel/irp-mn-start-device) request for a device. This IRP includes information about the device's hardware resources that the driver must supply in the *DeviceDescription* structure.

The caller uses the **MaximumLength** member in the *DeviceDescription* structure to indicate the optimal number of map registers it can use. The I/O manager will attempt to allocate enough map registers to accommodate a DMA transfer operation of this maximum size. On output, the I/O manager returns, in the *NumberOfMapRegisters* parameter, the number of map registers that it allocates. Drivers should check the returned value; there is no guarantee a driver will receive the same number of map registers it requested.

To free the adapter object, the driver should call [PutDmaAdapter](/windows-hardware/drivers/ddi/wdm/nc-wdm-pput_dma_adapter) through the pointer returned in the **DMA_ADAPTER** structure.  

As previously described, **IoGetDmaAdapter** returns **NULL** if it does not support the version of the **DMA_ADAPTER** structure that is specified by *DeviceDescription-*&gt;**Version**. Callers should rely on this behavior to determine whether the routine returns a pointer to the requested version of the **DMA_ADAPTER** structure. When **IoGetDmaAdapter** returns a pointer to version 1 or version 2 or version 3 of the **DMA_ADAPTER** structure, the **Version** member of this structure is always set to 1. Thus, the caller cannot use the **Version** member of the returned **DMA_ADAPTER** structure to distinguish between versions 1, 2 and 3 of this structure.

## -see-also

[AddDevice](/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device)

[**DEVICE_DESCRIPTION**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_description)

[**DMA_ADAPTER**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter)

[**DMA_OPERATIONS**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations)

[IRP_MN_START_DEVICE](/windows-hardware/drivers/kernel/irp-mn-start-device)

[PutDmaAdapter](/windows-hardware/drivers/ddi/wdm/nc-wdm-pput_dma_adapter)
