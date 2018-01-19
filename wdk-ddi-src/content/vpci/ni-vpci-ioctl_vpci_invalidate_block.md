---
UID: NI:vpci.IOCTL_VPCI_INVALIDATE_BLOCK
title: IOCTL_VPCI_INVALIDATE_BLOCK
author: windows-driver-content
description: The driver for a PCI Express (PCIe) virtual function (VF) issues the IOCTL_VPCI_INVALIDATE_BLOCK IOCTL request in order to be notified of changes to data in one or more VF configuration blocks.
old-location: pci\IOCTL_VPCI_INVALIDATE_BLOCK.htm
old-project: PCI
ms.assetid: 66D1626A-7F22-48B8-8DB3-7B6E1634BABE
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _VMB_CHANNEL_STATE_CHANGE_CALLBACKS, *PVMB_CHANNEL_STATE_CHANGE_CALLBACKS, VMB_CHANNEL_STATE_CHANGE_CALLBACKS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: vpci.h
req.include-header: Wdm.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2012 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_VPCI_INVALIDATE_BLOCK
req.alt-loc: Vpci.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
req.typenames: *PVMB_CHANNEL_STATE_CHANGE_CALLBACKS, VMB_CHANNEL_STATE_CHANGE_CALLBACKS
req.product: Windows 10 or later.
---

# IOCTL_VPCI_INVALIDATE_BLOCK IOCTL



## -description

The driver for a PCI Express (PCIe) virtual function (VF) issues the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439301">IOCTL_VPCI_INVALIDATE_BLOCK</a> IOCTL request in order to be notified of changes to data in one or more VF configuration blocks. The driver is notified of these changes when the IOCTL is completed. Once notified, the driver should assume that any data previously read from the  specified VF configuration blocks has become invalid. Therefore, the driver should update its cache by reading the configuration block data again.

The driver issues this IOCTL to the next-lower driver in the driver stack.



The driver for a PCI Express (PCIe) virtual function (VF) issues the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439301">IOCTL_VPCI_INVALIDATE_BLOCK</a> IOCTL request in order to be notified of changes to data in one or more VF configuration blocks. The driver is notified of these changes when the IOCTL is completed. Once notified, the driver should assume that any data previously read from the  specified VF configuration blocks has become invalid. Therefore, the driver should update its cache by reading the configuration block data again.

The driver issues this IOCTL to the next-lower driver in the driver stack.



## -ioctlparameters

### -input-buffer

<text></text>

### -input-buffer-length

<text></text>

### -output-buffer

<text></text>

### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code. 
For more information, see [XREF-LINK:NTSTATUS Values].

## -remarks
The driver must first allocate or reuse an I/O request packet (<a href="..\wdm\ns-wdm-_irp.md">IRP</a>). You can use the <a href="..\wdm\nf-wdm-iobuilddeviceiocontrolrequest.md">IoBuildDeviceIoControlRequest</a> routine to specifically allocate an IOCTL IRP. You can also use general-purpose IRP creation and initialization routines, such as <a href="..\wdm\nf-wdm-ioallocateirp.md">IoAllocateIrp</a>, <a href="..\wdm\nf-wdm-ioreuseirp.md">IoReuseIrp</a>, or <a href="..\wdm\nf-wdm-ioinitializeirp.md">IoInitializeIrp</a>. For more information about IRP allocation, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542899">Creating IRPs for Lower-Level Drivers</a>.

The driver must then set the  members of the <a href="..\wdm\ns-wdm-_irp.md">IRP</a> structure as described in the following table.

<b>NULL</b>

The address of the event object that was initialized in the call to the <a href="..\wdm\nf-wdm-keinitializeevent.md">KeInitializeEvent</a> routine.<div class="alert"><b>Note</b>  If asynchronous completion of the IOCTL request is not required, this member should be set to <b>NULL</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>.</div>
<div> </div>


The address of a caller-allocated <a href="..\wdm\ns-wdm-_io_status_block.md">IO_STATUS_BLOCK</a> structure. This structure is updated by the lower driver to indicate the final status of the I/O request.

The driver calls the <a href="..\wdm\nf-wdm-iogetnextirpstacklocation.md">IoGetNextIrpStackLocation</a> routine to access the lower driver's I/O stack location. This function returns a pointer to an <a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a> structure that contains the parameters for the I/O stack location.

The driver must then set the members in the <a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a> structure as described in the following table.

<b>MajorFunction</b>


<a href="https://msdn.microsoft.com/library/windows/hardware/ff550766">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>


<b>Parameters</b>.<b>DeviceIoControl</b>.<b>IoControlCode</b>


## -see-also
<dl>
<dt><b></b></dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_io_status_block.md">IO_STATUS_BLOCK</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_irp.md">IRP</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550766">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_sriov_vf_invalidate_config_block_info.md">NDIS_SRIOV_VF_INVALIDATE_CONFIG_BLOCK_INFO</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisminvalidateconfigblock.md">NdisMInvalidateConfigBlock</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451903">OID_SRIOV_VF_INVALIDATE_CONFIG_BLOCK</a>
</dt>
<dt>
<a href="..\vpci\ns-vpci-_vpci_invalidate_block_output.md">VPCI_INVALIDATE_BLOCK_OUTPUT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\pci]:%20IOCTL_VPCI_INVALIDATE_BLOCK control code%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

