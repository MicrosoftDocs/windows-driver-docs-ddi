---
UID: NI:vpci.IOCTL_VPCI_WRITE_BLOCK
title: IOCTL_VPCI_WRITE_BLOCK (vpci.h)
description: The driver for a PCI Express (PCIe) virtual function (VF) issues an IOCTL_VPCI_WRITE_BLOCK I/O control code (IOCTL) in order to write data to a VF configuration block. The driver issues this IOCTL to the next-lower driver in the driver stack.
old-location: pci\ioctl_vpci_write_block.htm
tech.root: PCI
ms.assetid: 5214053E-28AB-4728-9F4F-6705F8F56AC7
ms.date: 02/24/2018
keywords: ["IOCTL_VPCI_WRITE_BLOCK IOCTL"]
ms.keywords: IOCTL_VPCI_WRITE_BLOCK, IOCTL_VPCI_WRITE_BLOCK control code, PCI.ioctl_vpci_write_block, vpci/IOCTL_VPCI_WRITE_BLOCK
f1_keywords:
 - "vpci/IOCTL_VPCI_WRITE_BLOCK"
req.header: vpci.h
req.include-header: Wdm.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Server 2012 and later versions of Windows.
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
req.irql: DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Vpci.h
api_name:
- IOCTL_VPCI_WRITE_BLOCK
product:
- Windows
targetos: Windows
req.typenames: VMB_CHANNEL_STATE_CHANGE_CALLBACKS, *PVMB_CHANNEL_STATE_CHANGE_CALLBACKS
req.product: Windows 10 or later.
---

# IOCTL_VPCI_WRITE_BLOCK IOCTL


##  Major Code:


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



The driver for a PCI Express (PCIe) virtual function (VF) issues an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vpci/ni-vpci-ioctl_vpci_write_block">IOCTL_VPCI_WRITE_BLOCK</a>
   I/O control code (IOCTL) in order to write data to a VF configuration block. The driver issues this IOCTL to the next-lower driver in the driver stack.


<div class="alert"><b>Note</b>  This IOCTL request is issued by the driver of a PCIe  VF on a device that supports the single root I/O virtualization (SR-IOV) interface. </div><div> </div>When the driver issues the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vpci/ni-vpci-ioctl_vpci_write_block">IOCTL_VPCI_WRITE_BLOCK</a> IOCTL, the driver must follow these steps:
<dl>
<dd>
<a href="https://docs.microsoft.com/">Preparing an I/O Request Packet Structure</a>

</dd>
<dd>
<a href="https://docs.microsoft.com/">Preparing an I/O Stack Location Structure</a>

</dd>
<dd>
<a href="https://docs.microsoft.com/">Issuing the IOCTL Request</a>

</dd>
<dd>
<a href="https://docs.microsoft.com/">IOCTL Request Completion Results</a>

</dd>
</dl>For more information about issuing IOCTLs between kernel-mode drivers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>.


## -ioctlparameters




### -input-buffer








### -input-buffer-length








### -output-buffer








### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block



Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code.

For more information, see [XREF-LINK:NTSTATUS Values].




## -remarks



<h3><a id="preparing_an_i_o_request_packet_structure"></a><a id="PREPARING_AN_I_O_REQUEST_PACKET_STRUCTURE"></a>Preparing an I/O Request Packet Structure</h3>
The driver must first allocate or reuse an I/O request packet (<a href="..\wdm\ns-wdm-_irp.md">IRP</a>). You can use the <a href="..\wdm\nf-wdm-iobuilddeviceiocontrolrequest.md">IoBuildDeviceIoControlRequest</a> routine to specifically allocate an IOCTL IRP. You can also use general-purpose IRP creation and initialization routines, such as <a href="..\wdm\nf-wdm-ioallocateirp.md">IoAllocateIrp</a>, <a href="..\wdm\nf-wdm-ioreuseirp.md">IoReuseIrp</a>, or <a href="..\wdm\nf-wdm-ioinitializeirp.md">IoInitializeIrp</a>. For more information about IRP allocation, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-irps-for-lower-level-drivers">Creating IRPs for Lower-Level Drivers</a>.

The driver must then set the  members of the <a href="..\wdm\ns-wdm-_irp.md">IRP</a> structure as described in the following table.

<table>
<tr>
<th>IRP member</th>
<th>Value</th>
</tr>
<tr>
<td><b>UserBuffer</b></td>
<td>
<b>NULL</b>

</td>
</tr>
<tr>
<td><b>UserEvent</b></td>
<td>
The address of the event object that was initialized in the call to the <a href="..\wdm\nf-wdm-keinitializeevent.md">KeInitializeEvent</a> routine.<div class="alert"><b>Note</b>  If asynchronous completion of the IOCTL request is not required, this member should be set to <b>NULL</b>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>.</div>
<div> </div>


</td>
</tr>
<tr>
<td><b>UserIosb</b></td>
<td>
The address of a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a> structure. This structure is updated by the lower driver to indicate the final status of the I/O request.

</td>
</tr>
</table>
 

<h3><a id="preparing_an_i_o_stack_location_structure"></a><a id="PREPARING_AN_I_O_STACK_LOCATION_STRUCTURE"></a>Preparing an I/O Stack Location Structure</h3>
The driver calls the <a href="..\wdm\nf-wdm-iogetnextirpstacklocation.md">IoGetNextIrpStackLocation</a> routine to access the lower driver's I/O stack location. This function returns a pointer to an <a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a> structure that contains the parameters for the I/O stack location.

The driver must then set the members in the <a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a> structure as described in the following table:

<table>
<tr>
<th>IO_STACK_LOCATION member</th>
<th>Value</th>
</tr>
<tr>
<td><b>MajorFunction</b></td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-internal-device-control">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>


</td>
</tr>
<tr>
<td><b>Parameters.DeviceIoControl.IoControlCode</b></td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vpci/ni-vpci-ioctl_vpci_write_block">IOCTL_VPCI_WRITE_BLOCK</a>


</td>
</tr>
<tr>
<td><b>Parameters.DeviceIoControl.Type3InputBuffer</b></td>
<td>
A pointer to a <a href="..\vpci\ns-vpci-_vpci_write_block_input.md">VPCI_WRITE_BLOCK_INPUT</a> structure. The driver formats this structure with the parameters for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vpci/ni-vpci-ioctl_vpci_write_block">IOCTL_VPCI_WRITE_BLOCK</a>
   I/O request.

</td>
</tr>
<tr>
<td>I<b>Parameters.DeviceIoControl.InputBufferLength</b></td>
<td>
The size, in bytes, of the <a href="..\vpci\ns-vpci-_vpci_write_block_input.md">VPCI_WRITE_BLOCK_INPUT</a> structure.

</td>
</tr>
<tr>
<td><b>Parameters.DeviceIoControl.OutputBufferLength</b></td>
<td>
Zero

</td>
</tr>
</table>
 

<h3><a id="issuing_the_ioctl_request"></a><a id="ISSUING_THE_IOCTL_REQUEST"></a>Issuing the IOCTL Request</h3>
To issue this IOCTL request, the driver  calls the <a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a> routine to pass the request on to the next-lower driver  in the driver stack. The driver sets the parameters of <b>IoCallDriver</b> as described in the following table.

<table>
<tr>
<th>IoCallDriver parameter</th>
<th>Value</th>
</tr>
<tr>
<td><i>DeviceObject</i></td>
<td>
The device object of the lower driver.

</td>
</tr>
<tr>
<td><i>Irp</i></td>
<td>
The address of the <a href="..\wdm\ns-wdm-_irp.md">IRP</a> that was previously allocated and initialized. For more information, see <a href="https://docs.microsoft.com/">Preparing an I/O Request Packet (IRP) Structure</a>.

</td>
</tr>
</table>
 

<h3><a id="ioctl_request_completion_results"></a><a id="IOCTL_REQUEST_COMPLETION_RESULTS"></a>IOCTL Request Completion Results</h3>
      When the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vpci/ni-vpci-ioctl_vpci_write_block">IOCTL_VPCI_WRITE_BLOCK</a> IOCTL request is completed, the <b>Status</b> member of the caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a> structure is set to one of the values in the following table.:

<table>
<tr>
<th>Status value</th>
<th>Description</th>
</tr>
<tr>
<td>
<b>STATUS_SUCCESS</b>

</td>
<td>
The IOCTL completed successfully.

</td>
</tr>
<tr>
<td>
<b>STATUS_PENDING</b>

</td>
<td>
The IOCTL has not completed. The driver must call the <a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a> routine in order to put the current thread into a wait state. The driver sets the <i>Object</i> parameter to the address of an event object that was initialized in the call to the <a href="..\wdm\nf-wdm-keinitializeevent.md">KeInitializeEvent</a> routine.

The event is signaled when the IOCTL request is completed. Once the event is signaled, the thread resumes execution.

</td>
</tr>
<tr>
<td>
<b>STATUS_BUFFER_TOO_SMALL</b>

</td>
<td>
The <b>Parameters.DeviceIoControl.InputBufferLength</b> member was set to a value less than the size, in bytes, of the <a href="..\vpci\ns-vpci-_vpci_write_block_input.md">VPCI_WRITE_BLOCK_INPUT</a> structure.

</td>
</tr>
</table>
 

If the request completed successfully, the
      <b>Information</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a> structure is set to the number of bytes written. Otherwise, the
      <b>Information</b> member is set to zero.

When the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vpci/ni-vpci-ioctl_vpci_write_block">IOCTL_VPCI_WRITE_BLOCK</a> IOCTL is issued, the driver of the PCIe physical function (PF) is notified to write the data to the specified VF configuration block.

<div class="alert"><b>Note</b>  The operating system reserves and manages the resources that are required for the successful completion of this IOCTL. </div>
<div> </div>
A VF configuration block is used for backchannel communication between the drivers of the PCIe PF and a VF on a device that supports the SR-IOV interface. The PF driver allocates a configuration block for each VF within unused blocks of the device's PCI configuration space.



As soon as the VF configuration block is allocated, VF configuration data can be exchanged in a protected manner between the following drivers:

<ul>
<li>
The VF driver, which runs in the guest operating system. This operating system runs within a Hyper-V child partition.



</li>
<li>
The PF driver, which runs in the management operating system.

This operating system runs within the Hyper-V parent partition.

</li>
</ul>
The  usage of the VF configuration block and the format of its configuration data are defined by the  independent hardware vendor (IHV) of the device. The configuration data is used only by the drivers of the PF and VF.

<div class="alert"><b>Note</b>  The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vpci/ni-vpci-ioctl_vpci_write_block">IOCTL_VPCI_WRITE_BLOCK</a> IOCTL offers an asynchronous alternative to the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/hh451609(v=vs.85)">WriteVfConfigBlock</a> routine.</div>
<div> </div>



## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-internal-device-control">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/hh451609(v=vs.85)">WriteVfConfigBlock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="..\wdm\ns-wdm-_irp.md">IRP</a>



<a href="..\vpci\ns-vpci-_vpci_write_block_input.md">VPCI_WRITE_BLOCK_INPUT</a>



<a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a>



<a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a>



<b></b>



 

 


