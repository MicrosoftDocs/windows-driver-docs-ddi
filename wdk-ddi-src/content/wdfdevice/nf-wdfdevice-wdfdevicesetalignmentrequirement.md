---
UID: NF:wdfdevice.WdfDeviceSetAlignmentRequirement
title: WdfDeviceSetAlignmentRequirement function
author: windows-driver-content
description: The WdfDeviceSetAlignmentRequirement method registers the driver's preferred address alignment for the data buffers that the device uses during memory transfer operations.
old-location: wdf\wdfdevicesetalignmentrequirement.htm
old-project: wdf
ms.assetid: 47e857d0-1423-45e5-a5a5-54507b8fa315
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFDEVICESETALIGNMENTREQUIREMENT, WdfDeviceSetAlignmentRequirement method, wdfdevice/WdfDeviceSetAlignmentRequirement, DFDeviceObjectGeneralRef_9648c639-95b8-4dd9-8d30-8fb6352fe5f6.xml, kmdf.wdfdevicesetalignmentrequirement, WdfDeviceSetAlignmentRequirement, wdf.wdfdevicesetalignmentrequirement
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfDeviceSetAlignmentRequirement
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceSetAlignmentRequirement function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceSetAlignmentRequirement</b> method registers the driver's preferred address alignment for the data buffers that the device uses during memory transfer operations.


## -syntax


````
VOID WdfDeviceSetAlignmentRequirement(
  _In_ WDFDEVICE Device,
  _In_ ULONG     AlignmentRequirement
);
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param AlignmentRequirement [in]

The alignment requirement for a data buffer. This value must be one less than the alignment boundary. For example, you can specify 15 for a 16-byte alignment boundary and 31 for a 32-byte alignment boundary. You can also use one of the FILE_<i>Xxxx</i>_ALIGNMENT constants that are defined in <i>Wdm.h</i>.


## -returns


None.

A bug check occurs if the driver supplies an invalid object handle.



## -remarks


A driver that uses direct I/O can call  <b>WdfDeviceSetAlignmentRequirement</b> to register a preferred alignment requirement.  The alignment applies to I/O requests that go through the I/O Manager, and  not those sent to your driver from another driver that calls <a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a>.

 Because the I/O manager does not always use the requested alignment, the driver should be prepared for unaligned buffers.

The driver can call <a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetalignmentrequirement.md">WdfDeviceGetAlignmentRequirement</a> to obtain the current value for the device's alignment requirement.

The I/O manager sets an alignment requirement value for the device when the driver calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. For more information about a device's alignment requirement value and when a driver must change the value, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547807">Initializing a Device Object</a> in the WDM documentation.

If your driver specifies an alignment requirement that is greater that the computer's page size (PAGE_SIZE), the logical addresses that the <a href="..\wdfcommonbuffer\nf-wdfcommonbuffer-wdfcommonbuffergetalignedlogicaladdress.md">WdfCommonBufferGetAlignedLogicalAddress</a> method returns are always aligned to the specified alignment requirement, but the virtual addresses that the <a href="..\wdfcommonbuffer\nf-wdfcommonbuffer-wdfcommonbuffergetalignedvirtualaddress.md">WdfCommonBufferGetAlignedVirtualAddress</a> method returns might not be aligned to the alignment requirement.

If your driver specifies an alignment requirement that is less than the computer's page size, all logical and virtual addresses are aligned to the specified alignment requirement.

For more information about calling <b>WdfDeviceSetAlignmentRequirement</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/enabling-dma-transactions">Enabling DMA Transactions</a> and <a href="https://msdn.microsoft.com/81a56f62-917e-4798-b2cc-6469c802fab8">Using Common Buffers</a>.



## -see-also

<a href="..\wdfcommonbuffer\nf-wdfcommonbuffer-wdfcommonbuffergetalignedvirtualaddress.md">WdfCommonBufferGetAlignedVirtualAddress</a>

<a href="..\wdfcommonbuffer\nf-wdfcommonbuffer-wdfcommonbuffergetalignedlogicaladdress.md">WdfCommonBufferGetAlignedLogicalAddress</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetalignmentrequirement.md">WdfDeviceGetAlignmentRequirement</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceSetAlignmentRequirement method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

