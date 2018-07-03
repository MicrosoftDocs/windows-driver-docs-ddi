---
UID: NI:ehstorbandmgmt.IOCTL_EHSTOR_BANDMGMT_SET_BAND_LOCATION
title: IOCTL_EHSTOR_BANDMGMT_SET_BAND_LOCATION
author: windows-driver-content
description: The location properties of bands in a band-managed storage device are modified with the IOCTL_EHSTOR_BANDMGMT_SET_BAND_LOCATION request.
old-location: storage\ioctl_ehstor_bandmgmt_set_band_location.htm
old-project: storage
ms.assetid: FE6DA52C-6EE3-450E-A559-A7BCE47FA327
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_EHSTOR_BANDMGMT_SET_BAND_LOCATION, IOCTL_EHSTOR_BANDMGMT_SET_BAND_LOCATION control, IOCTL_EHSTOR_BANDMGMT_SET_BAND_LOCATION control code [Storage Devices], ehstorbandmgmt/IOCTL_EHSTOR_BANDMGMT_SET_BAND_LOCATION, storage.ioctl_ehstor_bandmgmt_set_band_location
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	EhStorBandMgmt.h
api_name:
-	IOCTL_EHSTOR_BANDMGMT_SET_BAND_LOCATION
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_EHSTOR_BANDMGMT_SET_BAND_LOCATION IOCTL


## -description


The location properties of bands in a band-managed storage device are modified with the <b>IOCTL_EHSTOR_BANDMGMT_SET_BAND_LOCATION</b> request.


## -ioctlparameters




### -input-buffer

The buffer at <i>Irp-&gt;AssociatedIrp.SystemBuffer</i> must contain a   <a href="https://msdn.microsoft.com/library/windows/hardware/hh464113">SET_BAND_LOCATION_PARAMETERS</a> structure followed by the <b>AUTH_KEY</b> and <a href="https://msdn.microsoft.com/library/windows/hardware/hh439557">BAND_LOCATION_INFO</a> structures. 

If the <b>AuthKeyOffset</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/hh464113">SET_BAND_LOCATION_PARAMETERS</a> is set to <b>EHSTOR_BANDMGR_NO_KEY</b>, the input data in the system buffer need not include an <b>AUTH_KEY</b> structure.


### -input-buffer-length

<i>Parameters.DeviceIoControl.InputBufferLength</i> indicates the size, in bytes, of the buffer, which must be at least <b>sizeof</b> (SET_BAND_LOCATION_PARAMETERS)   + <b>sizeof</b>(AUTH_KEY) + <b>sizeof</b>(BAND_LOCATION_INFO).


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

One of the following values can be returned in the <b>Status</b> field.

<table>
<tr>
<th>Status Value</th>
<th>Description</th>
</tr>
<tr>
<td>STATUS_SUCCESS</td>
<td>The location properties for the band were changed.</td>
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
<td>The band was not found for the selection criteria provided.</td>
</tr>
<tr>
<td>STATUS_ACCESS_DENIED</td>
<td>The authentication key provided is not valid.</td>
</tr>
<tr>
<td>STATUS_IO_DEVICE_ERROR</td>
<td>Communication failed. The storage device might be incompatible with security protocols. </td>
</tr>
</table>
 


## -remarks



Data in LBAs that remains after resizing is not modified by the operation. Also,  it is unnecessary to unmount a volume during a resize operation if the LBA range that spans the volume remains within the band after  resizing.

The changes made to the band table by this request are committed to the device atomically before the IOCTL request completes. Therefore, it is guaranteed that the band is modified with all of its properties set or no properties set at all should a system or power failure occur.

The <b>BandSize</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/hh439557">BAND_LOCATION_INFO</a> must be greater than  0. This IOCTL cannot resize a band to 0 to cause a band deletion. To delete a band, the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451376">IOCTL_EHSTOR_BANDMGMT_DELETE_BAND</a> request is used.

If <a href="https://msdn.microsoft.com/library/windows/hardware/hh439557">BAND_LOCATION_INFO</a> specifies properties for the global band, <b>BandStart</b> must be set to 0 and <b>BandSize</b> must be set to –1.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439557">BAND_LOCATION_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451376">IOCTL_EHSTOR_BANDMGMT_DELETE_BAND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh464113">SET_BAND_LOCATION_PARAMETERS</a>
 

 

