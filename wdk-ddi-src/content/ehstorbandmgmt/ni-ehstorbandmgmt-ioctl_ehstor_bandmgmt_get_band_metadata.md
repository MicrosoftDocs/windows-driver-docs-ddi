---
UID: NI:ehstorbandmgmt.IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA
title: IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA
author: windows-driver-content
description: Metadata associated with a band is retrieved with an IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA request. The metadata for a band serves as a data area for a key manager application.
old-location: storage\ioctl_ehstor_bandmgmt_get_band_metadata.htm
old-project: storage
ms.assetid: 543EB710-9BF5-428E-B5CE-7088B98586EA
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_ehstor_bandmgmt_get_band_metadata, IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA control code [Storage Devices], IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA, ehstorbandmgmt/IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ehstorbandmgmt.h
req.include-header: EhStorBandMgmt.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8
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
-	IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA
product: Windows
targetos: Windows
req.typenames: DXVA_VideoSample32
---

# IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


Metadata associated with a band is retrieved with an  <b> IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA</b> request. The metadata for a band serves as a data area for a key manager application.


## -ioctlparameters




### -input-buffer

The input buffer at <i>Irp-&gt;AssociatedIrp.SystemBuffer</i> must contain a <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_get_band_metadata_parameters.md"> GET_BAND_METADATA_PARAMETERS</a> structure. 


### -input-buffer-length

<i>Parameters.DeviceIoControl.InputBufferLength</i> indicates the size, in bytes, of the buffer, which must be at least <b>sizeof</b> (GET_BAND_METADATA_PARAMETERS).


### -output-buffer

The output buffer at <i>Irp-&gt;AssociatedIrp.SystemBuffer</i> contains a byte array of band metadata specified by <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_get_band_metadata_parameters.md">GET_BAND_METADATA_PARAMETERS</a>.


### -output-buffer-length

The length of a <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_get_band_metadata_parameters.md">GET_BAND_METADATA_PARAMETERS</a> structure.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

The <b>Information</b> field contains the number of bytes returned in the output buffer. One of the following values can be returned in the <b>Status</b> field. 
<table>
<tr>
<th>Status Value</th>
<th>Description</th>
</tr>
<tr>
<td>STATUS_SUCCESS</td>
<td>The metadata was returned in the system buffer.</td>
</tr>
<tr>
<td>STATUS_INVALID_DEVICE_REQUEST</td>
<td>The storage device does not support band management.</td>
</tr>
<tr>
<td>STATUS_INVALID_BUFFER_SIZE</td>
<td>The output buffer size is incorrect.</td>
</tr>
<tr>
<td>STATUS_INVALID_PARAMETER</td>
<td>Information in the input buffer is invalid.</td>
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


Authentication for this IOCTL is unnecessary and an authentication key is not included as input.



## -see-also

<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_location_info.md">BAND_LOCATION_INFO</a>

<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_security_info.md">BAND_SECURITY_INFO</a>

<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_create_band_parameters.md">CREATE_BAND_PARAMETERS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

