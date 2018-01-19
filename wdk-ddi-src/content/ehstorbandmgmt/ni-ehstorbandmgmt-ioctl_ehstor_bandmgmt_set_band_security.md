---
UID: NI:ehstorbandmgmt.IOCTL_EHSTOR_BANDMGMT_SET_BAND_SECURITY
title: IOCTL_EHSTOR_BANDMGMT_SET_BAND_SECURITY
author: windows-driver-content
description: The security properties of bands in a band-managed storage device are modified with the IOCTL_EHSTOR_BANDMGMT_SET_BAND_SECURITY request.
old-location: storage\ioctl_ehstor_bandmgmt_set_band_security.htm
old-project: storage
ms.assetid: CBA94AF4-649D-47C9-879B-4B939DE32BE2
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
req.alt-api: IOCTL_EHSTOR_BANDMGMT_SET_BAND_SECURITY
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

# IOCTL_EHSTOR_BANDMGMT_SET_BAND_SECURITY IOCTL



## -description
The security properties of bands in a band-managed storage device are modified with the <b>IOCTL_EHSTOR_BANDMGMT_SET_BAND_SECURITY</b> request.



## -ioctlparameters

### -input-buffer
The buffer at <i>Irp-&gt;AssociatedIrp.SystemBuffer</i> must contain a <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_set_band_security_parameters.md"> SET_BAND_SECURITY_PARAMETERS</a> structure followed by the <b>AUTH_KEY</b> and <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_security_info.md">BAND_SECURITY_INFO</a> structures. 

If the <b>AuthKeyOffset</b> member of <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_set_band_security_parameters.md">SET_BAND_SECURITY_PARAMETERS</a> is set to <b>EHSTOR_BANDMGR_NO_KEY</b>, the input data in the system buffer need not include an <b>AUTH_KEY</b> structure. Also, if a new authentication key is not given, no updated key structure is included.


### -input-buffer-length
<i>Parameters.DeviceIoControl.InputBufferLength</i> indicates the size, in bytes, of the buffer, which must be at least <b>sizeof</b> (SET_BAND_SECURITY_PARAMETERS)   + 2 * <b>sizeof</b>(AUTH_KEY) + <b>sizeof</b>(BAND_SECURITY_INFO) when all input structures are required.


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
Read and write locking and unlocking for bands are set with this IOCTL in the  <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_security_info.md">BAND_SECURITY_INFO</a> structure included as input in the system buffer. 

Authentication key changes will not affect the lock state of the band. It is not necessary to unmount a volume to change an authentication key with this request.

When a band is unlocked, meaning either the  <b>Readlock</b> or <b>WriteLock</b> members of  <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_security_info.md">BAND_SECURITY_INFO</a> are FALSE, the silo driver will cache the provided authentication key if <b>SETBANDSEC_AUTHKEY_CACHING_ENABLED</b> is set in the <b>Flags</b> member of <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_set_band_security_parameters.md">SET_BAND_SECURITY_PARAMETERS</a>.

As a special case, this IOCTL can be used to notify the silo driver that a band was unlocked without the use of the locking members in <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_security_info.md">BAND_SECURITY_INFO</a>. To do this, the <b>NewAuthKeyOffset</b> member of <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_set_band_security_parameters.md">SET_BAND_SECURITY_PARAMETERS</a> is set to <b>CurrentAuthKeyOffset</b> with  <b>BandSecurityInfoOffset</b> set to 0. In this case, no security changes occur, but the key provided at <b>CurrentAuthKeyOffset</b> is cached in memory, provided that <b>SETBANDSEC_AUTHKEY_CACHING_ENABLED</b> is set in <b>Flags</b>.

The changes made to the band table by this request are committed to the device atomically before the IOCTL request completes. Therefore, it is guaranteed that the band is modified with all of its properties set or no properties set at all should a system or power failure occur.


## -see-also
<dl>
<dt>
<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_security_info.md">BAND_SECURITY_INFO</a>
</dt>
<dt>
<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_set_band_security_parameters.md">SET_BAND_SECURITY_PARAMETERS</a>
</dt>
<dt>
<a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_delete_band.md">IOCTL_EHSTOR_BANDMGMT_DELETE_BAND</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_EHSTOR_BANDMGMT_SET_BAND_SECURITY control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

