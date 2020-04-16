---
UID: NI:ehstorbandmgmt.IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA
title: IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA (ehstorbandmgmt.h)
description: Metadata associated with a band is retrieved with an IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA request. The metadata for a band serves as a data area for a key manager application.
old-location: storage\ioctl_ehstor_bandmgmt_get_band_metadata.htm
tech.root: storage
ms.assetid: 543EB710-9BF5-428E-B5CE-7088B98586EA
ms.date: 03/29/2018
keywords: ["IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA IOCTL"]
ms.keywords: IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA, IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA control, IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA control code [Storage Devices], ehstorbandmgmt/IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA, storage.ioctl_ehstor_bandmgmt_get_band_metadata
f1_keywords:
 - "ehstorbandmgmt/IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- EhStorBandMgmt.h
api_name:
- IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA IOCTL


## -description


Metadata associated with a band is retrieved with an  <b> IOCTL_EHSTOR_BANDMGMT_GET_BAND_METADATA</b> request. The metadata for a band serves as a data area for a key manager application.


## -ioctlparameters




### -input-buffer

The input buffer at <i>Irp->AssociatedIrp.SystemBuffer</i> must contain a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_get_band_metadata_parameters"> GET_BAND_METADATA_PARAMETERS</a> structure. 


### -input-buffer-length

<i>Parameters.DeviceIoControl.InputBufferLength</i> indicates the size, in bytes, of the buffer, which must be at least <b>sizeof</b> (GET_BAND_METADATA_PARAMETERS).


### -output-buffer

The output buffer at <i>Irp->AssociatedIrp.SystemBuffer</i> contains a byte array of band metadata specified by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_get_band_metadata_parameters">GET_BAND_METADATA_PARAMETERS</a>.


### -output-buffer-length

The length of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_get_band_metadata_parameters">GET_BAND_METADATA_PARAMETERS</a> structure.


### -in-out-buffer








### -inout-buffer-length








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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_band_location_info">BAND_LOCATION_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_band_security_info">BAND_SECURITY_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_create_band_parameters">CREATE_BAND_PARAMETERS</a>
 

 

