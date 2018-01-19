---
UID: NI:ntddscsi.IOCTL_SCSI_MINIPORT_HYBRID
title: IOCTL_SCSI_MINIPORT_HYBRID
author: windows-driver-content
description: The IOCTL_SCSI_MINIPORT_HYBRID control code sends a hybrid disk control request to an HBA-specific miniport driver.
old-location: storage\ioctl_scsi_miniport_hybrid.htm
old-project: storage
ms.assetid: 57DA022A-FAC6-4727-94E1-BCF6FEF1E945
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _MP_STORAGE_DIAGNOSTIC_TARGET_TYPE, *PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE, MP_STORAGE_DIAGNOSTIC_TARGET_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_SCSI_MINIPORT_HYBRID
req.alt-loc: Ntddscsi.h
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
req.typenames: *PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE, MP_STORAGE_DIAGNOSTIC_TARGET_TYPE
---

# IOCTL_SCSI_MINIPORT_HYBRID IOCTL



## -description
The 
     <b>IOCTL_SCSI_MINIPORT_HYBRID</b> control code sends a hybrid disk control request to an HBA-specific miniport driver. The <b>IOCTL_SCSI_MINIPORT_HYBRID</b> request is a sub-IOCTL of <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_miniport.md">IOCTL_SCSI_MINIPORT</a>. This IOCTL is received and reformatted by StorPort, then sent  to the miniport as a <a href="..\srb\ns-srb-_storage_request_block.md">STORAGE_REQUEST_BLOCK</a> (SRB) with a function type of SRB_FUNCTION_IO_CONTROL. The input and output data is contained in the SRB data block. 

<b>IOCTL_SCSI_MINIPORT_HYBRID</b> is intended for use by third-party applications or filter drives which manage security features such as encryption or write-through behavior. 



## -syntax

````
typedef struct _HYBRID_REQUEST_BLOCK {
    ULONG   Version;
    ULONG   Size;
    ULONG   Function;
    ULONG   Flags;
    ULONG   DataBufferOffset;
    ULONG   DataBufferLength;
} HYBRID_REQUEST_BLOCK, *PHYBRID_REQUEST_BLOCK;
````


## -ioctlparameters

### -input-buffer
The buffer specified in the <b>DataBuffer</b> member of the SRB must contain an <a href="..\ntddscsi\ns-ntddscsi-_srb_io_control.md">SRB_IO_CONTROL</a> structure and a <b>HYBRID_REQUEST_BLOCK</b> structure. Depending on the <b>Function</b> member of <b>HYBRID_REQUEST_BLOCK</b>, additional data can be supplied. 


### -input-buffer-length
<b>DataTransferLength</b> indicates the size, in bytes, of the buffer, which must be at least <b>sizeof</b> (SRB_IO_CONTROL) + <b>sizeof</b>(HYBRID_REQUEST_BLOCK), with additional storage for function data if the <b>DataBufferLength</b> member of the <b>HYBRID_REQUEST_BLOCK</b> is nonzero.


### -output-buffer
An updated <a href="..\ntddscsi\ns-ntddscsi-_srb_io_control.md">SRB_IO_CONTROL</a> structure is returned to the data buffer in the SRB. 


### -output-buffer-length
The <b>DataBufferOffset</b> and <b>DataBufferLength</b> members of <b>HYBRID_REQUEST_BLOCK</b> are nonzero when data is returned for the specified <b>Function</b>. The <b>DataTransferLength</b> member of the SRB is updated when data is returned for the request function.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The resulting status of the function request is set in the <b>ReturnCode</b> member of <a href="..\ntddscsi\ns-ntddscsi-_srb_io_control.md">SRB_IO_CONTROL</a>. The following are the hybrid disk IOCTL status codes.

 


## -remarks
A <b>HYBRID_REQUEST_BLOCK</b> structure immediately follows the <a href="..\ntddscsi\ns-ntddscsi-_srb_io_control.md">SRB_IO_CONTROL</a> structure in the data buffer.  <b>HYBRID_REQUEST_BLOCK</b> is defined in ntddscsi.h as the following.



The version of the structure. Set to HYBRID_REQUEST_BLOCK_STRUCTURE_VERSION.

The size of the structure. Set to <b>sizeof</b>(HYBRID_REQUEST_BLOCK).

The hybrid disk request function. The function code is one of the following.

Returns information about the capabilities and attributes of a hybrid devices, such as supported priority levels, command set support, and cache size in a <a href="..\ntddscsi\ns-ntddscsi-_hybrid_information.md">HYBRID_INFORMATION</a> structure. On input, the <b>DataBuffer</b> specified in the SRB must contain the <a href="..\ntddscsi\ns-ntddscsi-_srb_io_control.md">SRB_IO_CONTROL</a> and <b>HYBRID_REQUEST_BLOCK</b> structures. The <b>DataBufferLength</b> must be large enough to include the <b>HYBRID_INFORMATION</b> structure returned. The <b>DataBufferOffset</b> points to the output data containing <b>HYBRID_INFORMATION</b>. If  the buffer is too small to return the data,  the <b>ReturnCode</b> member of <b>SRB_IO_CONTROL</b> is set to HYBRID_STATUS_OUTPUT_BUFFER_TOO_SMALL and <b>DataBufferLength</b> of the <b>HYBRID_REQUEST_BLOCK</b> is set to indicate the required length.

Disables the hybrid cache. Disabling the cache  can take several minutes. If queried during this operation, the <b>NV_CACHE_STATUS</b> member of the <a href="..\ntddscsi\ns-ntddscsi-_hybrid_information.md">HYBRID_INFORMATION</a> structure is set to <b>NvCacheStatusDisabling</b> until the cache is completely disabled. The caller should check the status of <b>NV_CACHE_STATUS</b> to verify that the caching medium is disabled. Once the cache is fully disabled, the status is <b>NvCacheStatusDisabled</b>. For this function, the <b>DataBufferOffset</b> member of <b>HYBRID_REQUEST_BLOCK</b> is set 0. This function has no output parameters.

Sets the caching medium to its default state, which is “enabled”. The <b>DataBufferOffset</b> member of <b>HYBRID_REQUEST_BLOCK</b> is set to 0. When this function completes, when queried, the <b>NV_CACHE_STATUS</b> member of the <a href="..\ntddscsi\ns-ntddscsi-_hybrid_information.md">HYBRID_INFORMATION</a> structure is set to <b>NvCacheStatusEnabled</b>. For this function, the <b>DataBufferOffset</b> member of <b>HYBRID_REQUEST_BLOCK</b> is set 0. This function has no output parameters.

Sets the thresholds for dirty data synchronization on the device. In addition to <a href="..\ntddscsi\ns-ntddscsi-_srb_io_control.md">SRB_IO_CONTROL</a> and <b>HYBRID_REQUEST_BLOCK</b>, this function requires a <b>HYBRID_DIRTY_THRESHOLDS</b> structure included as input. The <b>DataBufferOffset</b> member is set to the beginning of the <b>HYBRID_DIRTY_THRESHOLDS</b> structure. This function has no output parameters.

This function demotes the priority of a given amount of cache contents to a lower priority. It can be used to achieve a soft reset of the cache by demoting all cache contents to priority 0. In addition to <a href="..\ntddscsi\ns-ntddscsi-_srb_io_control.md">SRB_IO_CONTROL</a> and <b>HYBRID_REQUEST_BLOCK</b>, this function requires a <b>HYBRID_DEMOTE_BY_SIZE</b> structure included as input. The <b>DataBufferOffset</b> member is set to the beginning of the <b>HYBRID_DEMOTE_BY_SIZE</b> structure. This function has no output parameters.

Reserved. Set to 0.

The offset for additional data that was sent or is returned for the function specified in  <b>Function</b>. This value varies on the data required for <b>Function</b>.  This value is the offset from the beginning the <b>DataBuffer</b> of the SRB which contains a <a href="..\ntddscsi\ns-ntddscsi-_srb_io_control.md">SRB_IO_CONTROL</a> structure and other required data structures. It should point to the first location after <b>SRB_IO_CONTROL</b> and <b>HYBRID_REQUEST_BLOCK</b>. This value is aligned at a multiple of <b>sizeof</b>(PVOID). If there is no buffer then <b>DataBufferOffset</b> is set to 0.

The size the data block found at <b>DataBufferOffset</b>.

The parameter requirements depend on the function code of the hybrid disk request. The following table lists the parameters required for each function.


<a href="..\ntddscsi\ns-ntddscsi-_srb_io_control.md">SRB_IO_CONTROL</a> +

<b>HYBRID_REQUEST_BLOCK</b>

<b>HYBRID_REQUEST_BLOCK</b> +


<a href="..\ntddscsi\ns-ntddscsi-_hybrid_information.md">HYBRID_INFORMATION</a>



<a href="..\ntddscsi\ns-ntddscsi-_srb_io_control.md">SRB_IO_CONTROL</a>


<b>HYBRID_DIRTY_THRESHOLDS</b>

<b>HYBRID_DEMOTE_BY_SIZE</b>

The <b>HYBRID_REQUEST_BLOCK</b> structure is located after the <a href="..\ntddscsi\ns-ntddscsi-_srb_io_control.md">SRB_IO_CONTROL</a> structure in the <b>DataBuffer</b> of the SRB. Any function data included with the request is found at the offset in <b>DataBufferOffset</b> after the beginning of the <b>SRB_IO_CONTROL</b> structure.

The following example demonstrates retrieval of  the function data for a HYBRID_FUNCTION_SET_DIRTY_THRESHOLD request.

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


The version of the structure. Set to HYBRID_REQUEST_INFO_STRUCTURE_VERSION.

The size of the structure. Set to <b>sizeof</b>(HYBRID_DIRTY_THRESHOLDS).

The fractional low threshold value for the hybrid disk cache to synchronize to disk.

The fractional high threshold value for the hybrid disk cache  to synchronize to disk.

The values of <b>DirtyLowThreshold</b> and <b>DirtyHighThreshold</b> are expressed as the smaller part of a ratio between the threshold value and a fraction base. The fraction base is determined by the <b>FractionBase</b> member of the <a href="..\ntddscsi\ns-ntddscsi-_hybrid_information.md">HYBRID_INFORMATION</a> structure.

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
The original priority level of the data to demote. This value must be &lt;= the value in the <b>MaximumHybridPriorityLevel</b> member of the <b>HYBRID_INFORMATION</b> structure returned by from a <b>HYBRID_FUNCTION_GET_INFO</b> function request. This value must be &gt; 0.

</dd>
<dt><a id="TargetPriority"></a><a id="targetpriority"></a><a id="TARGETPRIORITY"></a>TargetPriority</dt>
<dd>
The target priority level of the data to demote from the <i>SourcePriority</i> level. This value must be &lt; <i>SourcePriority</i>.

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


The size of the structure. Set to <b>sizeof</b>(HYBRID_DEMOTE_BY_SIZE).

The original priority level of the data to demote. This value must be &lt;= the value in the <b>MaximumHybridPriorityLevel</b> member of the <b>HYBRID_INFORMATION</b> structure returned by from a <b>HYBRID_FUNCTION_GET_INFO</b> function request. This value must be &gt; 0.

The target priority level of the data to demote from the <i>SourcePriority</i> level. This value must be &lt; <i>SourcePriority</i>.

Reserved.

The number of LBAs to demote to the new priority level.

The <a href="..\ntddscsi\ns-ntddscsi-_srb_io_control.md">SRB_IO_CONTROL</a> structure for this IOCTL contains IOCTL_MINIPORT_SIGNATURE_HYBRDISK in its <b>Signature</b> member and <b>IOCTL_SCSI_MINIPORT_HYBRID</b> in the <b>ControlCode</b> member.


## -see-also
<dl>
<dt>
<a href="..\ntddscsi\ns-ntddscsi-_hybrid_information.md">HYBRID_INFORMATION</a>
</dt>
<dt>
<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_miniport.md">IOCTL_SCSI_MINIPORT</a>
</dt>
<dt>
<a href="..\ntddscsi\ns-ntddscsi-_srb_io_control.md">SRB_IO_CONTROL</a>
</dt>
<dt>
<a href="..\srb\ns-srb-_storage_request_block.md">STORAGE_REQUEST_BLOCK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_SCSI_MINIPORT_HYBRID control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

