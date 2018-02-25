---
UID: NI:ehstorbandmgmt.IOCTL_EHSTOR_BANDMGMT_DELETE_BAND
title: IOCTL_EHSTOR_BANDMGMT_DELETE_BAND
author: windows-driver-content
description: A configured band on a storage device is deleted with the IOCTL_EHSTOR_BANDMGMT_DELETE_BAND request. An erase option in the input parameters allows the request to perform a cryptographic erase of the band data.
old-location: storage\ioctl_ehstor_bandmgmt_delete_band.htm
old-project: storage
ms.assetid: CA0002E6-D9E7-417B-AD48-32E25E24EC32
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IOCTL_EHSTOR_BANDMGMT_DELETE_BAND, IOCTL_EHSTOR_BANDMGMT_DELETE_BAND control code [Storage Devices], ehstorbandmgmt/IOCTL_EHSTOR_BANDMGMT_DELETE_BAND, storage.ioctl_ehstor_bandmgmt_delete_band
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ehstorbandmgmt.h
req.include-header: EhStorBandMgmt.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with  Windows 8.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	EhStorBandMgmt.h
apiname:
-	IOCTL_EHSTOR_BANDMGMT_DELETE_BAND
product: Windows
targetos: Windows
req.typenames: DXVA_VideoSample32
---

# IOCTL_EHSTOR_BANDMGMT_DELETE_BAND IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


A configured band on a storage device is deleted with the <b>IOCTL_EHSTOR_BANDMGMT_DELETE_BAND</b> request. An erase option in the input parameters allows the request to perform a cryptographic erase of the band data.


## -ioctlparameters




### -input-buffer

The input buffer at <i>Irp-&gt;AssociatedIrp.SystemBuffer</i> must contain a <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_set_band_metadata_parameters.md">DELETE_BAND_PARAMETERS</a> and possibly an <b>AUTH_KEY</b> structure. 

If the <b>AuthKeyOffset</b> member of <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_set_band_metadata_parameters.md">DELETE_BAND_PARAMETERS</a> is set to <b>EHSTOR_BANDMGR_NO_KEY</b>, the input data in the system buffer need not include an <b>AUTH_KEY</b> structure.


### -input-buffer-length

<i>Parameters.DeviceIoControl.InputBufferLength</i> indicates the size, in bytes, of the buffer, which must be at least <b>sizeof</b> (DELETE_BAND_PARAMETERS)    + <b>sizeof</b>(AUTH_KEY).


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

One of the following values can be returned in the <b>Status</b> field. 

<table>
<tr>
<th>Status Value</th>
<th>Description</th>
</tr>
<tr>
<td>STATUS_SUCCESS</td>
<td>The band was successfully deleted.</td>
</tr>
<tr>
<td>STATUS_INVALID_DEVICE_REQUEST</td>
<td>The storage device does not support band management.</td>
</tr>
<tr>
<td>STATUS_INVALID_BUFFER_SIZE</td>
<td>The input buffer size is incorrect.</td>
</tr>
<tr>
<td>STATUS_INVALID_PARAMETER</td>
<td>Information in the input buffer is invalid.</td>
</tr>
<tr>
<td>STATUS_ACCESS_DENIED</td>
<td>The authentication key is invalid or band is locked for writing.</td>
</tr>
<tr>
<td>STATUS_NOT_FOUND</td>
<td>The band was not found for the selection criteria provided.</td>
</tr>
<tr>
<td>STATUS_IO_DEVICE_ERROR</td>
<td>Communication failed. The storage device might be incompatible with security protocols. </td>
</tr>
</table>
 


## -remarks



An authentication key is required to delete a band without performing an erase first. To request a band erase, the <b>DELBAND_ERASE_BEFORE_DELETE</b> flag is set in the <b>Flags</b> member of <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_delete_band_parameters.md">DELETE_BAND_PARAMETERS</a>.

After a band delete, all LBAs contained in the deleted band are returned to the global band. The locking conditions for the global band now apply to the LBAs returned to the global band. The LBAs returned to the global band are now associated with the media key for the global band and encrypted data in those LBAs is unrecoverable.

The deleted band remains in the silo driver's band table but becomes unconfigured. The authentication key is reset to the default value, band and key metadata contains zeros, and the lock states revert to <b>PERSISTENT_UNLOCK</b>. The band is now available for reconfiguration with an <a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_create_band.md">IOCTL_EHSTOR_BANDMGMT_CREATE_BAND</a> request.

Deleting a band without a cryptographic erase will not remove the encryption key for that band. It is possible to later create a band with the same configuration and band identifier as the deleted band. In this case, data previously stored in the band and not overwritten since the deletion of the previous band will be available. To avoid this situation, delete the band with the <b>DELBAND_ERASE_BEFORE_DELETE</b> flag set in <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_delete_band_parameters.md">DELETE_BAND_PARAMETERS</a>.

The <b>IOCTL_EHSTOR_BANDMGMT_DELETE_BAND</b> will not delete the global band. A request to do so will return <b>STATUS_INVALID_PARAMETER</b>. 




## -see-also

<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_delete_band_parameters.md">DELETE_BAND_PARAMETERS</a>



<a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_erase_band.md">IOCTL_EHSTOR_BANDMGMT_ERASE_BAND</a>



<a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_create_band.md">IOCTL_EHSTOR_BANDMGMT_CREATE_BAND</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_EHSTOR_BANDMGMT_DELETE_BAND control code%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

