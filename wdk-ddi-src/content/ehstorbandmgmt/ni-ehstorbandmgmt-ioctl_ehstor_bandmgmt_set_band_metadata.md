---
UID: NI:ehstorbandmgmt.IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA
title: IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA (ehstorbandmgmt.h)
description: Metadata associated with a band is set with an IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA request. The metadata for a band serves as a data area for a key manager application.
old-location: storage\ioctl_ehstor_bandmgmt_set_band_metadata.htm
tech.root: storage
ms.assetid: 5FBEAB29-C256-47EF-B673-6584679B8908
ms.date: 03/29/2018
keywords: ["IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA IOCTL"]
ms.keywords: IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA, IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA control, IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA control code [Storage Devices], ehstorbandmgmt/IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA, storage.ioctl_ehstor_bandmgmt_set_band_metadata
f1_keywords:
 - "ehstorbandmgmt/IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA"
 - "IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA"
req.header: ehstorbandmgmt.h
req.include-header: EhStorBandMgmt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
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
- IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA
targetos: Windows
req.typenames: 
---

# IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA IOCTL


## -description


Metadata associated with a band is set with an <b>IOCTL_EHSTOR_BANDMGMT_SET_BAND_METADATA</b> request. The metadata for a band serves as a data area for a key manager application.


## -ioctlparameters




### -input-buffer

The input buffer at <i>Irp->AssociatedIrp.SystemBuffer</i> must contain a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_set_band_metadata_parameters">SET_BAND_METADATA_PARAMETERS</a> and possibly an <b>AUTH_KEY</b> structure along with the new metadata to set for the band. 

If the <b>AuthKeyOffset</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_set_band_metadata_parameters">SET_BAND_METADATA_PARAMETERS</a> is set to <b>EHSTOR_BANDMGR_NO_KEY</b>, the input data in the system buffer need not include an <b>AUTH_KEY</b> structure.


### -input-buffer-length

<i>Parameters.DeviceIoControl.InputBufferLength</i> indicates the size, in bytes, of the buffer, which must be at least <b>sizeof</b> (SET_BAND_METADATA_PARAMETERS)    + <b>MetadataSize</b> + <b>sizeof</b>(AUTH_KEY).


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

One of the following values may be returned in the <b>Status</b> field: 

<table>
<tr>
<th>Status Value</th>
<th>Description</th>
</tr>
<tr>
<td>STATUS_SUCCESS</td>
<td>The metadata was set for the selected band.</td>
</tr>
<tr>
<td>STATUS_INVALID_DEVICE_REQUEST</td>
<td>Storage device does not support band management.</td>
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
<td>STATUS_NOT_FOUND</td>
<td>Band was not found for the selection criteria provided.</td>
</tr>
<tr>
<td>STATUS_IO_DEVICE_ERROR</td>
<td>Communication failed. The storage device might be incompatible with security protocols. </td>
</tr>
</table>
 


## -remarks



Metadata can also be erased by using this IOCTL. To erase metadata for a band, set the metadata portion of input buffer to all zeros or some other erase pattern. To ensure removal of sensitive information in metadata blobs, this erase operation should be performed prior to deleting a band from the silo driver's band table.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_set_band_metadata_parameters">SET_BAND_METADATA_PARAMETERS</a>
 

 

