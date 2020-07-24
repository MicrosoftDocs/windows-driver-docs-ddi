---
UID: NF:wdfdevice.WdfDeviceSetAlignmentRequirement
title: WdfDeviceSetAlignmentRequirement function (wdfdevice.h)
description: The WdfDeviceSetAlignmentRequirement method registers the driver's preferred address alignment for the data buffers that the device uses during memory transfer operations.
old-location: wdf\wdfdevicesetalignmentrequirement.htm
tech.root: wdf
ms.assetid: 47e857d0-1423-45e5-a5a5-54507b8fa315
ms.date: 02/26/2018
keywords: ["WdfDeviceSetAlignmentRequirement function"]
ms.keywords: DFDeviceObjectGeneralRef_9648c639-95b8-4dd9-8d30-8fb6352fe5f6.xml, WdfDeviceSetAlignmentRequirement, WdfDeviceSetAlignmentRequirement method, kmdf.wdfdevicesetalignmentrequirement, wdf.wdfdevicesetalignmentrequirement, wdfdevice/WdfDeviceSetAlignmentRequirement
f1_keywords:
 - "wdfdevice/WdfDeviceSetAlignmentRequirement"
 - "WdfDeviceSetAlignmentRequirement"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDeviceSetAlignmentRequirement
targetos: Windows
req.typenames: 
---

# WdfDeviceSetAlignmentRequirement function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceSetAlignmentRequirement</b> method registers the driver's preferred address alignment for the data buffers that the device uses during memory transfer operations.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param AlignmentRequirement [in]

The hardware-dependent alignment requirement for a data buffer. This value must be one less than the alignment boundary. For example, you can specify 15 for a 16-byte alignment boundary and 31 for a 32-byte alignment boundary. You can also use one of the FILE_<i>Xxxx</i>_ALIGNMENT constants that are defined in <i>Wdm.h</i>, for example:

```
//
// Define alignment requirement values
//
#define FILE_BYTE_ALIGNMENT             0x00000000
#define FILE_WORD_ALIGNMENT             0x00000001
#define FILE_LONG_ALIGNMENT             0x00000003
#define FILE_QUAD_ALIGNMENT             0x00000007
#define FILE_OCTA_ALIGNMENT             0x0000000f
#define FILE_32_BYTE_ALIGNMENT          0x0000001f
#define FILE_64_BYTE_ALIGNMENT          0x0000003f
#define FILE_128_BYTE_ALIGNMENT         0x0000007f
#define FILE_256_BYTE_ALIGNMENT         0x000000ff
#define FILE_512_BYTE_ALIGNMENT         0x000001ff
```

## -remarks

A bug check occurs if the driver supplies an invalid object handle.




A driver that uses direct I/O can call  <b>WdfDeviceSetAlignmentRequirement</b> to register a preferred alignment requirement.  The alignment applies to I/O requests that go through the I/O Manager, and  not those sent to your driver from another driver that calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocalldriver">IoCallDriver</a>.

Because the I/O manager does not always use the requested alignment, the driver should be prepared for unaligned buffers.

The driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetalignmentrequirement">WdfDeviceGetAlignmentRequirement</a> to obtain the current value for the device's alignment requirement.

The I/O manager sets an alignment requirement value for the device when the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>. For more information about a device's alignment requirement value and when a driver must change the value, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/initializing-a-device-object">Initializing a Device Object</a> in the WDM documentation.

If your driver specifies an alignment requirement that is greater that the computer's page size (PAGE_SIZE), the logical addresses that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfcommonbuffer/nf-wdfcommonbuffer-wdfcommonbuffergetalignedlogicaladdress">WdfCommonBufferGetAlignedLogicalAddress</a> method returns are always aligned to the specified alignment requirement, but the virtual addresses that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfcommonbuffer/nf-wdfcommonbuffer-wdfcommonbuffergetalignedvirtualaddress">WdfCommonBufferGetAlignedVirtualAddress</a> method returns might not be aligned to the alignment requirement.

If your driver specifies an alignment requirement that is less than the computer's page size, all logical and virtual addresses are aligned to the specified alignment requirement.

For more information about calling <b>WdfDeviceSetAlignmentRequirement</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/enabling-dma-transactions">Enabling DMA Transactions</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-common-buffers">Using Common Buffers</a>.


#### Examples

The following code example is from the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/sample-kmdf-drivers">AMCC5933</a> sample driver. This example checks a device's current alignment requirement and sets the alignment requirement to a new value, if necessary.  Note that the exact alignment value is dependent on the hardware.

```cpp
ULONG alignReq;

alignReq = WdfDeviceGetAlignmentRequirement(device);
if (alignReq < AMCC5933_ALIGNMENT__32BITS) {
//
// Set the S5933 alignment requirement to a new value.
//
WdfDeviceSetAlignmentRequirement(
                                 device,
                                 AMCC5933_ALIGNMENT__32BITS
                                 );
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfcommonbuffer/nf-wdfcommonbuffer-wdfcommonbuffergetalignedlogicaladdress">WdfCommonBufferGetAlignedLogicalAddress</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfcommonbuffer/nf-wdfcommonbuffer-wdfcommonbuffergetalignedvirtualaddress">WdfCommonBufferGetAlignedVirtualAddress</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetalignmentrequirement">WdfDeviceGetAlignmentRequirement</a>
 

 

