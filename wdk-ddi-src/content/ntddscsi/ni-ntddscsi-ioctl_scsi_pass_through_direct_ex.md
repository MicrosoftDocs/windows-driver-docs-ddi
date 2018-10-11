---
UID: NI:ntddscsi.IOCTL_SCSI_PASS_THROUGH_DIRECT_EX
title: IOCTL_SCSI_PASS_THROUGH_DIRECT_EX
author: windows-driver-content
description: The IOCTL_SCSI_PASS_THROUGH_DIRECT_EX control code request is the extended version of the IOCTL_SCSI_PASS_THROUGH_DIRECT request. This request provides support for bidirectional data transfers and allows a command data block (CDB) &gt; 16 bytes.
old-location: storage\ioctl_scsi_pass_through_direct_ex.htm
tech.root: storage
ms.assetid: FB210147-9CF3-4D32-884E-256BEAFAE6C4
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_SCSI_PASS_THROUGH_DIRECT_EX, IOCTL_SCSI_PASS_THROUGH_DIRECT_EX control, IOCTL_SCSI_PASS_THROUGH_DIRECT_EX control code [Storage Devices], ntddscsi/IOCTL_SCSI_PASS_THROUGH_DIRECT_EX, storage.ioctl_scsi_pass_through_direct_ex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddscsi.h
api_name:
-	IOCTL_SCSI_PASS_THROUGH_DIRECT_EX
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SCSI_PASS_THROUGH_DIRECT_EX IOCTL


## -description


The <b>IOCTL_SCSI_PASS_THROUGH_DIRECT_EX</b> control code request
     is the extended version of the <b>IOCTL_SCSI_PASS_THROUGH_DIRECT</b> request. This request provides support for bidirectional data transfers and allows a command data block (CDB) &gt; 16 bytes.

Allows an application to send almost any SCSI command to a target device, with the following restrictions:
<ul>
<li>
Multitarget commands, such as COPY, are not allowed.

</li>
<li>
If a class driver for the target type of device exists, the request must be sent to that class driver. Thus, an application can send this request directly to the system port driver for a target logical unit only if there is no class driver for the type of device connected to that LU.

</li>
<li>
This request <i>must</i> be made if the input CDB might require the underlying miniport driver to access memory directly.

</li>
</ul>The calling application creates the SCSI command descriptor block, which can include a request for request-sense data if a CHECK CONDITION occurs. If the CDB requests a data transfer operation, the caller must set up an adapter device aligned buffer from which or into which the miniport driver can transfer data directly. This request is typically used for transferring larger amounts of data (&gt;16K).

Applications can send this request by means of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a> request. 

Storage class drivers set the minor IRP number to IRP_MN_SCSI_CLASS to indicate that the request has been processed by a storage class driver. 
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -ioctlparameters




### -input-buffer

<i>
       Parameters.DeviceIoControl.InputBufferLength</i> indicates the size, in bytes, of the buffer at <i>Irp-&gt;AssociatedIrp.SystemBuffer</i>, which must be at least (<i>sense data size</i> + <b>sizeof</b>(SCSI_PASS_THROUGH_DIRECT_EX)). The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/jj553713">SCSI_PASS_THROUGH_DIRECT_EX</a> structure is fixed.

This structure includes a SCSI CDB, which must be initialized by the caller except for the path, target ID, and LUN, which are filled in by the port driver. For a data-out command, the data to be transferred must be in an adapter device aligned buffer. The <b>DataInBuffer</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/jj553713">SCSI_PASS_THROUGH_DIRECT_EX</a> is a pointer to this adapter device aligned buffer. The caller must allocate additional storage, following the <b>SCSI_PASS_THROUGH_DIRECT_EX</b> structure, if the caller asks for request-sense data.


### -input-buffer-length

<i>
       Parameters.DeviceIoControl.InputBufferLength</i> indicates the size, in bytes, of the buffer at <i>Irp-&gt;AssociatedIrp.SystemBuffer</i>, which must be at least (<i>sense data size</i> + <b>sizeof</b>(SCSI_PASS_THROUGH_DIRECT_EX)). The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/jj553713">SCSI_PASS_THROUGH_DIRECT_EX</a> structure is fixed.


### -output-buffer

The port driver returns any request-sense data and the <a href="https://msdn.microsoft.com/library/windows/hardware/jj553713">SCSI_PASS_THROUGH_DIRECT_EX</a> structure to the buffer at <i>Irp-&gt;AssociatedIrp.SystemBuffer</i>. 


### -output-buffer-length

<b>SenseInfoLength</b> and <b>DataOutTransferLength</b> are updated to indicate the amount of data transferred. The port driver returns any data transferred from the device to the supplied cache-aligned buffer at <b>DataOutBuffer</b>.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the number of bytes returned in the output buffer at <i>Irp-&gt;AssociatedIrp.SystemBuffer</i>. The <b>Status</b> field is set to <b>STATUS_SUCCESS</b>, or possibly to <b>STATUS_BUFFER_TOO_SMALL</b> or <b>STATUS_INVALID_PARAMETER</b> if the input <b>Length</b> value in <a href="https://msdn.microsoft.com/library/windows/hardware/jj553713">SCSI_PASS_THROUGH_DIRECT_EX</a> is improperly set or the buffer specified in  <b>DataInBuffer</b> is not properly device aligned.



## -remarks



For data transfer operations, a buffer with alignment  matching the adapter device  is required. Applications can retrieve the device alignment mask by issuing an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560590">IOCTL_STORAGE_QUERY_PROPERTY</a> control code request with a query type of <b>PropertyStandardQuery</b> and property id of <b>StorageAdapterProperty</b>. The alignment mask is found in the <b>AlignmentMask</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566346">STORAGE_ADAPTER_DESCRIPTOR</a> structure that is returned. Drivers may also use the value in the <b>AlignmentMask</b> member of the adapter's <i>DeviceObject</i>.

In the following  example function, a   buffer is prepared as a device  aligned data transfer buffer.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>
PVOID AllocateAlignedBuffer(ULONG size, ULONG AlignmentMask, PVOID *pUnAlignedBuffer)
{
    PVOID AlignedBuffer;
    ULONG_PTR FullWordMask = (ULONG_PTR)AlignmentMask;

    if (AlignmentMask == 0)
    {
        AlignedBuffer = malloc(size);
        // return the original buffer to free later
        *pUnAlignedBuffer = AlignedBuffer;
    }
    else
    {
        // expand the size for the alignment window
        size += AlignmentMask;
        AlignedBuffer = malloc(size);
        // return the original buffer to free later
        *pUnAlignedBuffer = AlignedBuffer;
        // adjust buffer pointer for the desired alignment
        AlignedBuffer = (PVOID)(((ULONG_PTR)AlignedBuffer + FullWordMask) &amp; ~FullWordMask);
    }

    return AlignedBuffer;
}</pre>
</td>
</tr>
</table></span></div>
In order to issue an <b>IOCTL_SCSI_PASS_THROUGH_DIRECT_EX</b> request, the underlying storage device must support extended SRBs. This means that the supported SRB type is <b>SRB_TYPE_STORAGE_REQUEST_BLOCK</b>. An application can query for SRB support with the <b>IOCTL_STORAGE_QUERY_PROPERTY</b> request with a query type of <b>PropertyStandardQuery</b> and a property type of <b>StorageDeviceProperty</b>. The <b>SrbType</b> member returned in the <a href="https://msdn.microsoft.com/83ef2a1a-f95e-4b05-8911-e5e900192630">STORAGE_ADAPTER_DESCRIPTIOR</a> structure will indicate either <b>SRB_TYPE_SCSI_REQUEST_BLOCK</b> or <b>SRB_TYPE_STORAGE_REQUEST_BLOCK</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj602801">IOCTL_SCSI_PASS_THROUGH_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560590">IOCTL_STORAGE_QUERY_PROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj553713">SCSI_PASS_THROUGH_DIRECT_EX</a>
 

 

