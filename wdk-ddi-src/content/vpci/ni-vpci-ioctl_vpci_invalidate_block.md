---
UID: NI:vpci.IOCTL_VPCI_INVALIDATE_BLOCK
title: IOCTL_VPCI_INVALIDATE_BLOCK
author: windows-driver-content
description: The driver for a PCI Express (PCIe) virtual function (VF) issues the IOCTL_VPCI_INVALIDATE_BLOCK IOCTL request in order to be notified of changes to data in one or more VF configuration blocks.
old-location: pci\IOCTL_VPCI_INVALIDATE_BLOCK.htm
tech.root: PCI
ms.assetid: 66D1626A-7F22-48B8-8DB3-7B6E1634BABE
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_VPCI_INVALIDATE_BLOCK, IOCTL_VPCI_INVALIDATE_BLOCK control code, PCI.IOCTL_VPCI_INVALIDATE_BLOCK, vpci/IOCTL_VPCI_INVALIDATE_BLOCK
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Vpci.h
api_name:
-	IOCTL_VPCI_INVALIDATE_BLOCK
product:
- Windows
targetos: Windows
req.typenames: VMB_CHANNEL_STATE_CHANGE_CALLBACKS, *PVMB_CHANNEL_STATE_CHANGE_CALLBACKS
req.product: Windows 10 or later.
---

# IOCTL_VPCI_INVALIDATE_BLOCK IOCTL


##  Major Code:


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



The driver for a PCI Express (PCIe) virtual function (VF) issues the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439301">IOCTL_VPCI_INVALIDATE_BLOCK</a> IOCTL request in order to be notified of changes to data in one or more VF configuration blocks. The driver is notified of these changes when the IOCTL is completed. Once notified, the driver should assume that any data previously read from the  specified VF configuration blocks has become invalid. Therefore, the driver should update its cache by reading the configuration block data again.

The driver issues this IOCTL to the next-lower driver in the driver stack.


<div class="alert"><b>Note</b>  This IOCTL request is issued by the driver of a PCIe  VF on a device that supports the single root I/O virtualization (SR-IOV) interface. </div><div> </div>When the driver issues the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439301">IOCTL_VPCI_INVALIDATE_BLOCK</a> IOCTL, the driver must follow these steps:
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
</dl>For more information about issuing IOCTLs between kernel-mode drivers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>.


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
The driver must first allocate or reuse an I/O request packet (<a href="..\wdm\ns-wdm-_irp.md">IRP</a>). You can use the <a href="..\wdm\nf-wdm-iobuilddeviceiocontrolrequest.md">IoBuildDeviceIoControlRequest</a> routine to specifically allocate an IOCTL IRP. You can also use general-purpose IRP creation and initialization routines, such as <a href="..\wdm\nf-wdm-ioallocateirp.md">IoAllocateIrp</a>, <a href="..\wdm\nf-wdm-ioreuseirp.md">IoReuseIrp</a>, or <a href="..\wdm\nf-wdm-ioinitializeirp.md">IoInitializeIrp</a>. For more information about IRP allocation, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542899">Creating IRPs for Lower-Level Drivers</a>.

The driver must then set the  members of the <a href="..\wdm\ns-wdm-_irp.md">IRP</a> structure as described in the following table.

<table>
<tr>
<th>
<a href="..\wdm\ns-wdm-_irp.md">IRP</a> member</th>
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
The address of the event object that was initialized in the call to the <a href="..\wdm\nf-wdm-keinitializeevent.md">KeInitializeEvent</a> routine.<div class="alert"><b>Note</b>  If asynchronous completion of the IOCTL request is not required, this member should be set to <b>NULL</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>.</div>
<div> </div>


</td>
</tr>
<tr>
<td><b>UserIosb</b></td>
<td>
The address of a caller-allocated <a href="..\wudfwdm\ns-wudfwdm-_io_status_block.md">IO_STATUS_BLOCK</a> structure. This structure is updated by the lower driver to indicate the final status of the I/O request.

</td>
</tr>
</table>
 

<h3><a id="preparing_an_i_o_stack_location_structure"></a><a id="PREPARING_AN_I_O_STACK_LOCATION_STRUCTURE"></a>Preparing an I/O Stack Location Structure</h3>
The driver calls the <a href="..\wdm\nf-wdm-iogetnextirpstacklocation.md">IoGetNextIrpStackLocation</a> routine to access the lower driver's I/O stack location. This function returns a pointer to an <a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a> structure that contains the parameters for the I/O stack location.

The driver must then set the members in the <a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a> structure as described in the following table.

<table>
<tr>
<th>
<a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a> member</th>
<th>Value</th>
</tr>
<tr>
<td>
<b>MajorFunction</b>

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550766">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>


</td>
</tr>
<tr>
<td>
<b>Parameters</b>.<b>DeviceIoControl</b>.<b>IoControlCode</b>

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439301">IOCTL_VPCI_INVALIDATE_BLOCK</a>


</td>
</tr>
<tr>
<td>
<b>Parameters</b>.<b>DeviceIoControl</b>.<b>Type3InputBuffer</b>

</td>
<td>
A pointer to a <a href="..\vpci\ns-vpci-_vpci_invalidate_block_output.md">VPCI_INVALIDATE_BLOCK_OUTPUT</a> structure. The driver formats this structure with the parameters for the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439301">IOCTL_VPCI_INVALIDATE_BLOCK</a>
   I/O request.

</td>
</tr>
<tr>
<td>I<b>Parameters</b>.<b>DeviceIoControl</b>.<b>InputBufferLength</b>

</td>
<td>
The size, in bytes, of the <a href="..\vpci\ns-vpci-_vpci_invalidate_block_output.md">VPCI_INVALIDATE_BLOCK_OUTPUT</a> structure.

</td>
</tr>
<tr>
<td>
<b>Parameters</b>.<b>DeviceIoControl</b>.<b>OutputBufferLength</b>

</td>
<td>
The size, in bytes, of the caller-allocated buffer that will contain the configuration data to be read.<div class="alert"><b>Note</b>  This value must be the same as the value of the <b>BytesRequested</b> member of the <a href="..\vpci\ns-vpci-_vpci_invalidate_block_output.md">VPCI_INVALIDATE_BLOCK_OUTPUT</a> structure.</div>
<div> </div>


</td>
</tr>
</table>
 

<h3><a id="issuing_the_ioctl_request"></a><a id="ISSUING_THE_IOCTL_REQUEST"></a>Issuing the IOCTL Request</h3>
To issue this IOCTL request, the driver calls the <a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a> routine to pass the request on to the next-lower driver  in the driver stack. The driver sets the parameters of <b>IoCallDriver</b> as described in the following table.

<table>
<tr>
<th>
<a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a> parameter</th>
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
The address of the <a href="..\wdm\ns-wdm-_irp.md">IRP</a> that was previously allocated and initialized. For more information, see <a href="https://docs.microsoft.com/">Preparing an I/O Request Packet Structure</a>.

</td>
</tr>
</table>
 

<h3><a id="ioctl_request_completion_results"></a><a id="IOCTL_REQUEST_COMPLETION_RESULTS"></a>IOCTL Request Completion Results</h3>

      When the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439301">IOCTL_VPCI_INVALIDATE_BLOCK</a> IOCTL request is completed, the  members of the caller-allocated <a href="..\wudfwdm\ns-wudfwdm-_io_status_block.md">IO_STATUS_BLOCK</a> structure are set to  the values in the following table.

<table>
<tr>
<th>Status value</th>
<th>Value</th>
</tr>
<tr>
<td><b>Status</b></td>
<td>
<b>STATUS_SUCCESS</b>

</td>
</tr>
<tr>
<td><b>Information</b></td>
<td>
Zero

</td>
</tr>
</table>
 

When the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439301">IOCTL_VPCI_INVALIDATE_BLOCK</a> IOCTL is issued and completed, the VF driver is notified that the PF driver has changed (<i>invalidated</i>) data in one or more VF configuration blocks.

<div class="alert"><b>Note</b>  The operating system reserves and manages the resources that are required for the successful completion of this IOCTL. </div>
<div> </div>
A VF configuration block is used for backchannel communication between the drivers of the PCIe PF and a VF on a device that supports the SR-IOV interface. VF configuration data can be exchanged between the following drivers:

<ul>
<li>
The VF driver, which runs in the guest operating system. This operating system runs within a Hyper-V child partition.



</li>
<li>
The PF driver, which runs in the management operating system.

This operating system runs within the Hyper-V parent partition.

</li>
</ul>
Starting with NDIS 6.30, the VF miniport driver should not issue an <a href="https://msdn.microsoft.com/library/windows/hardware/hh439301">IOCTL_VPCI_INVALIDATE_BLOCK</a> request. Instead, the following steps are performed in order to handle notifications of invalidated VF configuration block data.

<ol>
<li>
In the guest OS, NDIS issues an <a href="https://msdn.microsoft.com/library/windows/hardware/hh439301">IOCTL_VPCI_INVALIDATE_BLOCK</a> request.

</li>
<li>
In the management OS, the following steps occur:<ol>
<li>The PF miniport driver calls the <a href="..\ndis\nf-ndis-ndisminvalidateconfigblock.md">NdisMInvalidateConfigBlock</a> function to notify NDIS that VF configuration data has changed and is no longer valid. The driver sets the <i>BlockMask</i> parameter to a <b>ULONGLONG</b> bitmask that specifies which VF configuration blocks have changed. Each bit in the bitmask corresponds to a VF configuration block. If a bit is set to one, the data in the corresponding VF configuration block has changed.
</li>
<li>
NDIS signals the virtualization stack, which runs in the management OS, about the change in VF configuration block data. The virtualization stack caches the <i>BlockMask</i> parameter data.

<div class="alert"><b>Note</b>  Each time that the PF miniport driver calls <a href="..\ndis\nf-ndis-ndisminvalidateconfigblock.md">NdisMInvalidateConfigBlock</a>, the virtualization  stack <b>OR</b>s the <i>BlockMask</i> parameter data with the current value in its cache.</div>
<div> </div>
</li>
<li>
The virtualization stack notifies the virtual PCI (VPCI) driver, which  runs in the guest OS, about the invalidation of VF configuration data.  The virtualization stack sends the cached <i>BlockMask</i> parameter data to the VPCI driver.

</li>
</ol>


</li>
<li>
In the Guest OS, the following steps occur:<ol>
<li>
The VPCI driver saves the cached <i>BlockMask</i> parameter data in the <b>BlockMask</b> member of the <a href="..\vpci\ns-vpci-_vpci_invalidate_block_output.md">VPCI_INVALIDATE_BLOCK_OUTPUT</a> structure that is associated with the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439301">IOCTL_VPCI_INVALIDATE_BLOCK</a> request.

</li>
<li>
The VPCI driver successfully completes  the  <a href="https://msdn.microsoft.com/library/windows/hardware/hh439301">IOCTL_VPCI_INVALIDATE_BLOCK</a> request. When this happens, NDIS issues an object identifier (OID) request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451903">OID_SRIOV_VF_INVALIDATE_CONFIG_BLOCK</a>  to the VF miniport driver. A pointer to an <a href="..\ntddndis\ns-ntddndis-_ndis_sriov_vf_invalidate_config_block_info.md">NDIS_SRIOV_VF_INVALIDATE_CONFIG_BLOCK_INFO</a> structure is passed along in the OID request. This structure contains the cached <i>BlockMask</i> parameter data.

NDIS also issues another <a href="https://msdn.microsoft.com/library/windows/hardware/hh439301">IOCTL_VPCI_INVALIDATE_BLOCK</a> request to handle successive notifications of changes to VF configuration data.

</li>
<li>
When the VF driver handles the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451903">OID_SRIOV_VF_INVALIDATE_CONFIG_BLOCK</a> request, it reads data from the specified VF configuration blocks.

</li>
</ol>


</li>
</ol>
<div class="alert"><b>Note</b>  The  usage of the VF configuration block and the format of its configuration data are defined by the  independent hardware vendor (IHV) of the device. The configuration data is used only by the drivers of the PF and VF.</div>
<div> </div>



## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_io_status_block.md">IO_STATUS_BLOCK</a>



<a href="..\vpci\ns-vpci-_vpci_invalidate_block_output.md">VPCI_INVALIDATE_BLOCK_OUTPUT</a>



<a href="..\ndis\nf-ndis-ndisminvalidateconfigblock.md">NdisMInvalidateConfigBlock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550766">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="..\wdm\ns-wdm-_irp.md">IRP</a>



<a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a>



<a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451903">OID_SRIOV_VF_INVALIDATE_CONFIG_BLOCK</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_sriov_vf_invalidate_config_block_info.md">NDIS_SRIOV_VF_INVALIDATE_CONFIG_BLOCK_INFO</a>



<b></b>



 

 


