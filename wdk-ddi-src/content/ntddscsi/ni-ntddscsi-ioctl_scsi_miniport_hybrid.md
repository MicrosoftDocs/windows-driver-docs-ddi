---
UID: NI:ntddscsi.IOCTL_SCSI_MINIPORT_HYBRID
title: IOCTL_SCSI_MINIPORT_HYBRID (ntddscsi.h)
description: The IOCTL_SCSI_MINIPORT_HYBRID control code sends a hybrid disk control request to an HBA-specific miniport driver.
old-location: storage\ioctl_scsi_miniport_hybrid.htm
tech.root: storage
ms.assetid: 57DA022A-FAC6-4727-94E1-BCF6FEF1E945
ms.date: 03/29/2018
ms.keywords: IOCTL_SCSI_MINIPORT_HYBRID, IOCTL_SCSI_MINIPORT_HYBRID control, IOCTL_SCSI_MINIPORT_HYBRID control code [Storage Devices], ntddscsi/IOCTL_SCSI_MINIPORT_HYBRID, storage.ioctl_scsi_miniport_hybrid
f1_keywords:
 - "ntddscsi/IOCTL_SCSI_MINIPORT_HYBRID"
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.1.
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddscsi.h
api_name:
- IOCTL_SCSI_MINIPORT_HYBRID
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SCSI_MINIPORT_HYBRID IOCTL


## -description


The 
     <b>IOCTL_SCSI_MINIPORT_HYBRID</b> control code sends a hybrid disk control request to an HBA-specific miniport driver. The <b>IOCTL_SCSI_MINIPORT_HYBRID</b> request is a sub-IOCTL of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ni-ntddscsi-ioctl_scsi_miniport">IOCTL_SCSI_MINIPORT</a>. This IOCTL is received and reformatted by StorPort, then sent  to the miniport as a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_storage_request_block">STORAGE_REQUEST_BLOCK</a> (SRB) with a function type of SRB_FUNCTION_IO_CONTROL. The input and output data is contained in the SRB data block. 

<b>IOCTL_SCSI_MINIPORT_HYBRID</b> is intended for use by third-party applications or filter drives which manage security features such as encryption or write-through behavior. 
<div class="alert"><b>Warning</b>  Use of <b>IOCTL_SCSI_MINIPORT_HYBRID</b> to modify hybrid cache behavior will conflict with the operation of Windows system components and is not supported.</div><div> </div><div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -ioctlparameters




### -input-buffer

The buffer specified in the <b>DataBuffer</b> member of the SRB must contain an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_srb_io_control">SRB_IO_CONTROL</a> structure and a <b>HYBRID_REQUEST_BLOCK</b> structure. Depending on the <b>Function</b> member of <b>HYBRID_REQUEST_BLOCK</b>, additional data can be supplied. 


### -input-buffer-length

<b>DataTransferLength</b> indicates the size, in bytes, of the buffer, which must be at least <b>sizeof</b> (SRB_IO_CONTROL) + <b>sizeof</b>(HYBRID_REQUEST_BLOCK), with additional storage for function data if the <b>DataBufferLength</b> member of the <b>HYBRID_REQUEST_BLOCK</b> is nonzero.


### -output-buffer

An updated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_srb_io_control">SRB_IO_CONTROL</a> structure is returned to the data buffer in the SRB. 


### -output-buffer-length

The <b>DataBufferOffset</b> and <b>DataBufferLength</b> members of <b>HYBRID_REQUEST_BLOCK</b> are nonzero when data is returned for the specified <b>Function</b>. The <b>DataTransferLength</b> member of the SRB is updated when data is returned for the request function.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The resulting status of the function request is set in the <b>ReturnCode</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_srb_io_control">SRB_IO_CONTROL</a>. The following are the hybrid disk IOCTL status codes.

<table>
<tr>
<th>Return Code</th>
<th>Description</th>
</tr>
<tr>
<td>HYBRID_STATUS_SUCCESS</td>
<td>The function completed successfully.</td>
</tr>
<tr>
<td>HYBRID_STATUS_ILLEGAL_REQUEST</td>
<td>The request contains an invalid function code.</td>
</tr>
<tr>
<td>HYBRID_STATUS_INVALID_PARAMETER</td>
<td>Either the input or output parameters are formatted incorrectly.</td>
</tr>
<tr>
<td>HYBRID_STATUS_OUTPUT_BUFFER_TOO_SMALL</td>
<td>The data length given in <b>DataBufferLength</b> is too  small to contain the request output.</td>
</tr>
</table>
 


## -remarks



A <b>HYBRID_REQUEST_BLOCK</b> structure immediately follows the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_srb_io_control">SRB_IO_CONTROL</a> structure in the data buffer.  <b>HYBRID_REQUEST_BLOCK</b> is defined in ntddscsi.h as the following.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _HYBRID_REQUEST_BLOCK {
    ULONG   Version;
    ULONG   Size;
    ULONG   Function;
    ULONG   Flags;
    ULONG   DataBufferOffset;
    ULONG   DataBufferLength;
} HYBRID_REQUEST_BLOCK, *PHYBRID_REQUEST_BLOCK;</pre>
</td>
</tr>
</table></span></div>


The parameter requirements depend on the function code of the hybrid disk request. The following table lists the parameters required for each function.

<table>
<tr>
<th>Function</th>
<th>Input Parameters</th>
<th>Output Parameters</th>
</tr>
<tr>
<td>HYBRID_FUNCTION_GET_INFO</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_srb_io_control">SRB_IO_CONTROL</a> +

<b>HYBRID_REQUEST_BLOCK</b>

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_srb_io_control">SRB_IO_CONTROL</a> +

<b>HYBRID_REQUEST_BLOCK</b> +


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_hybrid_information">HYBRID_INFORMATION</a>


</td>
</tr>
<tr>
<td>HYBRID_FUNCTION_DISABLE_CACHING_MEDIUM              
</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_srb_io_control">SRB_IO_CONTROL</a> +

<b>HYBRID_REQUEST_BLOCK</b>

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_srb_io_control">SRB_IO_CONTROL</a>


</td>
</tr>
<tr>
<td>HYBRID_FUNCTION_ENABLE_CACHING_MEDIUM</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_srb_io_control">SRB_IO_CONTROL</a> +

<b>HYBRID_REQUEST_BLOCK</b>

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_srb_io_control">SRB_IO_CONTROL</a>


</td>
</tr>
<tr>
<td>HYBRID_FUNCTION_SET_DIRTY_THRESHOLD</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_srb_io_control">SRB_IO_CONTROL</a> +

<b>HYBRID_REQUEST_BLOCK</b> +

<b>HYBRID_DIRTY_THRESHOLDS</b>

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_srb_io_control">SRB_IO_CONTROL</a>


</td>
</tr>
<tr>
<td>HYBRID_FUNCTION_DEMOTE_BY_SIZE</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_srb_io_control">SRB_IO_CONTROL</a> +

<b>HYBRID_REQUEST_BLOCK</b> +

<b>HYBRID_DEMOTE_BY_SIZE</b>

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_srb_io_control">SRB_IO_CONTROL</a>


</td>
</tr>
</table>
 

The <b>HYBRID_REQUEST_BLOCK</b> structure is located after the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_srb_io_control">SRB_IO_CONTROL</a> structure in the <b>DataBuffer</b> of the SRB. Any function data included with the request is found at the offset in <b>DataBufferOffset</b> after the beginning of the <b>SRB_IO_CONTROL</b> structure.

The following example demonstrates retrieval of  the function data for a HYBRID_FUNCTION_SET_DIRTY_THRESHOLD request.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    PSRB_IO_CONTROL srbIoCtl = (PSRB_IO_CONTROL)srb->DataBuffer;
    PHYBRID_REQUEST_BLOCK hybridRequest = (PHYBRID_REQUEST_BLOCK)(srbIoCtl + 1);
    PHYBRID_DIRTY_THRESHOLDS hybridDirtyThresholds = NULL;

    if (hybridRequest->DataBufferOffset >= sizeof(SRB_IO_CONTROL) + sizeof(HYBRID_REQUEST_BLOCK))
    {
        if (hybridRequest->DataBufferLength >= sizeof(HYBRID_FUNCTION_SET_DIRTY_THRESHOLD))
        {
            hybridDirtyThresholds = (PHYBRID_DIRTY_THRESHOLDS)((PUCHAR)srbIoCtl + hybridRequest->DataBufferOffset);
        }
        else
        {
            srbIoCtl->ReturnCode = HYBRID_STATUS_INVALID_PARAMETER;
        }
    }</pre>
</td>
</tr>
</table></span></div>
<b>HYBRID_DIRTY_THRESHOLDS</b>

The HYBRID_FUNCTION_SET_DIRTY_THRESHOLD function uses the <b>HYBRID_DIRTY_THRESHOLDS</b> structure for its input parameters. <b>HYBRID_DIRTY_THRESHOLDS</b> is defined in ntddscsi.h as the following.<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _HYBRID_DIRTY_THRESHOLDS {
    ULONG   Version;
    ULONG   Size;
    ULONG   DirtyLowThreshold;
    ULONG   DirtyHighThreshold;
} HYBRID_DIRTY_THRESHOLDS, *PHYBRID_DIRTY_THRESHOLDS;</pre>
</td>
</tr>
</table></span></div>


<dl>
<dt><a id="Version"></a><a id="version"></a><a id="VERSION"></a>Version</dt>
<dd>
The version of the structure. Set to HYBRID_REQUEST_INFO_STRUCTURE_VERSION.

</dd>
<dt><a id="Size"></a><a id="size"></a><a id="SIZE"></a>Size</dt>
<dd>
The size of the structure. Set to <b>sizeof</b>(HYBRID_DIRTY_THRESHOLDS).

</dd>
<dt><a id="DirtyLowThreshold"></a><a id="dirtylowthreshold"></a><a id="DIRTYLOWTHRESHOLD"></a>DirtyLowThreshold</dt>
<dd>
The fractional low threshold value for the hybrid disk cache to synchronize to disk.

</dd>
<dt><a id="DirtyHighThreshold"></a><a id="dirtyhighthreshold"></a><a id="DIRTYHIGHTHRESHOLD"></a>DirtyHighThreshold</dt>
<dd>
The fractional high threshold value for the hybrid disk cache  to synchronize to disk.

</dd>
</dl>


The values of <b>DirtyLowThreshold</b> and <b>DirtyHighThreshold</b> are expressed as the smaller part of a ratio between the threshold value and a fraction base. The fraction base is determined by the <b>FractionBase</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_hybrid_information">HYBRID_INFORMATION</a> structure.

<b>HYBRID_DEMOTE_BY_SIZE</b>

The HYBRID_FUNCTION_DEMOTE_BY_SIZE function uses the <b>HYBRID_DEMOTE_BY_SIZE</b> structure for its input parameters. <b>HYBRID_DEMOTE_BY_SIZE</b> is defined in ntddscsi.h as the following.<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _HYBRID_DEMOTE_BY_SIZE {
    ULONG       Version;
    ULONG       Size;
    UCHAR       SourcePriority;
    UCHAR       TargetPriority;
    USHORT      Reserved0;
    ULONG       Reserved1;
    ULONGLONG   LbaCount;
} HYBRID_DEMOTE_BY_SIZE, *PHYBRID_DEMOTE_BY_SIZE;</pre>
</td>
</tr>
</table></span></div>


<dl>
<dt><a id="Version"></a><a id="version"></a><a id="VERSION"></a>Version</dt>
<dd>
The version of the structure. Set to HYBRID_REQUEST_INFO_STRUCTURE_VERSION.

</dd>
<dt><a id="Size"></a><a id="size"></a><a id="SIZE"></a>Size</dt>
<dd>
The size of the structure. Set to <b>sizeof</b>(HYBRID_DEMOTE_BY_SIZE).

</dd>
<dt><a id="SourcePriority"></a><a id="sourcepriority"></a><a id="SOURCEPRIORITY"></a>SourcePriority</dt>
<dd>
The original priority level of the data to demote. This value must be <= the value in the <b>MaximumHybridPriorityLevel</b> member of the <b>HYBRID_INFORMATION</b> structure returned by from a <b>HYBRID_FUNCTION_GET_INFO</b> function request. This value must be > 0.

</dd>
<dt><a id="TargetPriority"></a><a id="targetpriority"></a><a id="TARGETPRIORITY"></a>TargetPriority</dt>
<dd>
The target priority level of the data to demote from the <i>SourcePriority</i> level. This value must be < <i>SourcePriority</i>.

</dd>
<dt><a id="Reserved0"></a><a id="reserved0"></a><a id="RESERVED0"></a>Reserved0</dt>
<dd>
Reserved.

</dd>
<dt><a id="Reserved1"></a><a id="reserved1"></a><a id="RESERVED1"></a>Reserved1</dt>
<dd>
Reserved.

</dd>
<dt><a id="LbaCount"></a><a id="lbacount"></a><a id="LBACOUNT"></a>LbaCount</dt>
<dd>
The number of LBAs to demote to the new priority level.

</dd>
</dl>


The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_srb_io_control">SRB_IO_CONTROL</a> structure for this IOCTL contains IOCTL_MINIPORT_SIGNATURE_HYBRDISK in its <b>Signature</b> member and <b>IOCTL_SCSI_MINIPORT_HYBRID</b> in the <b>ControlCode</b> member.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_hybrid_information">HYBRID_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ni-ntddscsi-ioctl_scsi_miniport">IOCTL_SCSI_MINIPORT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ns-ntddscsi-_srb_io_control">SRB_IO_CONTROL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_storage_request_block">STORAGE_REQUEST_BLOCK</a>
 

 

