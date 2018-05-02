---
UID: NI:ehstorbandmgmt.IOCTL_EHSTOR_BANDMGMT_ERASE_BAND
title: IOCTL_EHSTOR_BANDMGMT_ERASE_BAND
author: windows-driver-content
description: The IOCTL_EHSTOR_BANDMGMT_ERASE_BAND request will cryptographically erase and reset the authentication key of a band. The remaining configuration of the band is left unmodified.
old-location: storage\ioctl_ehstor_bandmgmt_erase_band.htm
old-project: storage
ms.assetid: E7DE8E55-B753-42AF-B25F-F806EE37DCF1
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_EHSTOR_BANDMGMT_ERASE_BAND, IOCTL_EHSTOR_BANDMGMT_ERASE_BAND control, IOCTL_EHSTOR_BANDMGMT_ERASE_BAND control code [Storage Devices], ehstorbandmgmt/IOCTL_EHSTOR_BANDMGMT_ERASE_BAND, storage.ioctl_ehstor_bandmgmt_erase_band
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
-	IOCTL_EHSTOR_BANDMGMT_ERASE_BAND
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_EHSTOR_BANDMGMT_ERASE_BAND IOCTL


## -description


The <b>IOCTL_EHSTOR_BANDMGMT_ERASE_BAND</b> request will cryptographically erase and reset the authentication key of a band. The remaining configuration of the band is left unmodified.


## -ioctlparameters




### -input-buffer

The input buffer at <i>Irp-&gt;AssociatedIrp.SystemBuffer</i> must contain an   <a href="https://msdn.microsoft.com/library/windows/hardware/hh439726">ERASE_BAND_PARAMETERS</a> and possibly an <b>AUTH_KEY</b> structure. 

If the <b>NewAuthKeyOffset</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/hh439726">ERASE_BAND_PARAMETERS</a> is set to <b>EHSTOR_BANDMGR_NO_KEY</b>, the input data in the system buffer need not include an <b>AUTH_KEY</b> structure.


### -input-buffer-length

<i>Parameters.DeviceIoControl.InputBufferLength</i> indicates the size, in bytes, of the buffer, which must be at least <b>sizeof</b> (ERASE_BAND_PARAMETERS)    + <b>sizeof</b>(AUTH_KEY).


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
<td>The erase authentication key is not a default key and the band cannot be erased.</td>
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



A current erase authentication key is not provided in an <b>IOCTL_EHSTOR_BANDMGMT_ERASE_BAND</b> request. The erase authentication key for the storage device is previously configured.

No method is provided in Windows to change the erase authentication key for a storage device. Provided that the correct parameters are given as input in the system buffer, this request should succeed. If  the erase authentication key was changed outside of Windows, such as in a dual-boot environment with a different operating system, this request may fail.

When a band is erased with <b>IOCTL_EHSTOR_BANDMGMT_ERASE_BAND</b>, the only prior properties that remain are band start and band size. The previous media encryption key is removed and a new key is generated. Locking is set to <b>PERSISTANT_UNLOCK</b> for both reading and writing. Security metadata previously set is erased. The new authentication key specified in  <a href="https://msdn.microsoft.com/CD7388DD-84CD-4158-91F3-9DB0559DFC2F"> ERASE_BAND_PARAMETERS</a> is set unless use  of the default key is indicated.

To prevent other applications from taking control of a band and erase by using the default key, a new authentication key should be included with the <b>IOCTL_EHSTOR_BANDMGMT_ERASE_BAND</b> request. 

The changes made to the band table by this request are committed to the device atomically before the IOCTL request completes. Therefore, it is guaranteed that the band is modified with all of its properties set or no properties set at all should a system or power failure occur.




## -see-also




<a href="https://msdn.microsoft.com/CD7388DD-84CD-4158-91F3-9DB0559DFC2F"> ERASE_BAND_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451376">IOCTL_EHSTOR_BANDMGMT_DELETE_BAND</a>
 

 

