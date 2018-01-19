---
UID: NI:ehstorbandmgmt.IOCTL_EHSTOR_BANDMGMT_SET_BAND_LOCATION
title: IOCTL_EHSTOR_BANDMGMT_SET_BAND_LOCATION
author: windows-driver-content
description: The location properties of bands in a band-managed storage device are modified with the IOCTL_EHSTOR_BANDMGMT_SET_BAND_LOCATION request.
old-location: storage\ioctl_ehstor_bandmgmt_set_band_location.htm
old-project: storage
ms.assetid: FE6DA52C-6EE3-450E-A559-A7BCE47FA327
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _DXVA_VideoSample32, DXVA_VideoSample32
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
req.alt-api: IOCTL_EHSTOR_BANDMGMT_SET_BAND_LOCATION
req.alt-loc: EhStorBandMgmt.h
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
req.typenames: DXVA_VideoSample32
---

# IOCTL_EHSTOR_BANDMGMT_SET_BAND_LOCATION IOCTL



## -description
The location properties of bands in a band-managed storage device are modified with the <b>IOCTL_EHSTOR_BANDMGMT_SET_BAND_LOCATION</b> request.



## -ioctlparameters

### -input-buffer
The buffer at <i>Irp-&gt;AssociatedIrp.SystemBuffer</i> must contain a   <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_set_band_location_parameters.md">SET_BAND_LOCATION_PARAMETERS</a> structure followed by the <b>AUTH_KEY</b> and <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_location_info.md">BAND_LOCATION_INFO</a> structures. 

If the <b>AuthKeyOffset</b> member of <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_set_band_location_parameters.md">SET_BAND_LOCATION_PARAMETERS</a> is set to <b>EHSTOR_BANDMGR_NO_KEY</b>, the input data in the system buffer need not include an <b>AUTH_KEY</b> structure.


### -input-buffer-length
<i>Parameters.DeviceIoControl.InputBufferLength</i> indicates the size, in bytes, of the buffer, which must be at least <b>sizeof</b> (SET_BAND_LOCATION_PARAMETERS)   + <b>sizeof</b>(AUTH_KEY) + <b>sizeof</b>(BAND_LOCATION_INFO).


### -output-buffer
None.


### -output-buffer-length
None.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
One of the following values can be returned in the <b>Status</b> field.

 


## -remarks
Data in LBAs that remains after resizing is not modified by the operation. Also,  it is unnecessary to unmount a volume during a resize operation if the LBA range that spans the volume remains within the band after  resizing.

The changes made to the band table by this request are committed to the device atomically before the IOCTL request completes. Therefore, it is guaranteed that the band is modified with all of its properties set or no properties set at all should a system or power failure occur.

The <b>BandSize</b> member of <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_location_info.md">BAND_LOCATION_INFO</a> must be greater than  0. This IOCTL cannot resize a band to 0 to cause a band deletion. To delete a band, the <a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_create_band.md">IOCTL_EHSTOR_BANDMGMT_DELETE_BAND</a> request is used.

If <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_location_info.md">BAND_LOCATION_INFO</a> specifies properties for the global band, <b>BandStart</b> must be set to 0 and <b>BandSize</b> must be set to –1.


## -see-also
<dl>
<dt>
<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_location_info.md">BAND_LOCATION_INFO</a>
</dt>
<dt>
<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_set_band_location_parameters.md">SET_BAND_LOCATION_PARAMETERS</a>
</dt>
<dt>
<a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_delete_band.md">IOCTL_EHSTOR_BANDMGMT_DELETE_BAND</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_EHSTOR_BANDMGMT_SET_BAND_LOCATION control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

