---
UID: NI:ehstorbandmgmt.IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS
title: IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS
author: windows-driver-content
description: This IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS request is sent to retrieve the list of bands for a storage device under band management. Banding information is returned in a table of band entries that includes band location and security properties.
old-location: storage\ioctl_ehstor_bandmgmt_enumerate_bands.htm
old-project: storage
ms.assetid: 80F7546C-3683-460B-A0D9-AD41386E6195
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS, IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS control, IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS control code [Storage Devices], ehstorbandmgmt/IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS, storage.ioctl_ehstor_bandmgmt_enumerate_bands
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	EhStorBandMgmt.h
api_name:
-	IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS
product: Windows
targetos: Windows
req.typenames: 
---

# IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS IOCTL


## -description


This <b>IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS</b> request is sent to retrieve the list of bands for a storage device under band management. Banding information is returned in a table of band entries that includes band location and security properties.


## -ioctlparameters




### -input-buffer

The buffer at <i>Irp-&gt;AssociatedIrp.SystemBuffer</i> must contain an <a href="https://msdn.microsoft.com/library/windows/hardware/hh439719">ENUMERATE_BANDS_PARAMETERS</a> structure. 


### -input-buffer-length

<i>Parameters.DeviceIoControl.InputBufferLength</i> indicates the size, in bytes, of the buffer, which must be at least <b>sizeof</b> (ENUMERATE_BANDS_PARAMETERS).


### -output-buffer

The buffer at <i>Irp-&gt;AssociatedIrp.SystemBuffer</i> contains a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439573">BAND_TABLE</a> structure followed by <b>BandTableEntryCount</b> band entries.


### -output-buffer-length

The length of a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439573">BAND_TABLE</a> structure followed by <b>BandTableEntryCount</b> band entries.


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
<td>Security features on the storage device were deactivated.</td>
</tr>
<tr>
<td>STATUS_INVALID_DEVICE_REQUEST</td>
<td>The storage device does not support band management.</td>
</tr>
<tr>
<td>STATUS_INVALID_BUFFER_SIZE</td>
<td>The input buffer size is invalid.</td>
</tr>
<tr>
<td>STATUS_INVALID_PARAMETER</td>
<td>Information in the input buffer is invalid.</td>
</tr>
<tr>
<td>STATUS_NOT_FOUND</td>
<td>No bands are configured for the enumeration parameters provided.</td>
</tr>
<tr>
<td>STATUS_BUFFER_OVERFLOW</td>
<td>A buffer is not provided or its size set to zero. The required size is returned in the <b>Information</b> field.</td>
</tr>
<tr>
<td>STATUS_IO_DEVICE_ERROR</td>
<td>Communication failed. The storage device might be incompatible with security protocols. </td>
</tr>
<tr>
<td>STATUS_BUFFER_TOO_SMALL</td>
<td>The output buffer supplied is not large enough to hold the output data returned.</td>
</tr>
</table>
 


## -remarks



A driver or application can query for the necessary output buffer size by setting the output buffer for the request to NULL and the output size to 0. The <b>IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS</b> request will return with the <b>Status</b> field of the <i>IoStatus</i> block set to STATUS_BUFFER_OVERFLOW and the <b>Information</b> field will contain the required buffer size.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439573">BAND_TABLE</a>



<b>ENUMERATE_BANDS_PARAMETERS</b>
 

 

