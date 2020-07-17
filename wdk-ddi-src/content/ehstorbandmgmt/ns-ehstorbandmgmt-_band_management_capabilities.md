---
UID: NS:ehstorbandmgmt._BAND_MANAGEMENT_CAPABILITIES
title: _BAND_MANAGEMENT_CAPABILITIES (ehstorbandmgmt.h)
description: The BAND_MANAGEMENT_CAPABILITIES structure contains the security capabilities available for a storage device. This structure is returned in the system buffer by the IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES request.
old-location: storage\band_management_capabilities.htm
tech.root: storage
ms.assetid: 102C7CEC-B1DD-49F6-AB7F-0CE0A22EBE54
ms.date: 03/29/2018
keywords: ["_BAND_MANAGEMENT_CAPABILITIES structure"]
ms.keywords: "*PBAND_MANAGEMENT_CAPABILITIES, 0, BAND_MANAGEMENT_CAPABILITIES, BAND_MANAGEMENT_CAPABILITIES structure [Storage Devices], CAPS_ACTIVATED, CAPS_BANDCROSSING_SUPPORTED, CAPS_SID_SECURED, MEDIAKEY_PROTECTEDBY_AUTHKEY, MEDIAKEY_PROTECTEDBY_VENDORSCHEME, PBAND_MANAGEMENT_CAPABILITIES, PBAND_MANAGEMENT_CAPABILITIES structure pointer [Storage Devices], _BAND_MANAGEMENT_CAPABILITIES, ehstorbandmgmt/BAND_MANAGEMENT_CAPABILITIES, ehstorbandmgmt/PBAND_MANAGEMENT_CAPABILITIES, storage.band_management_capabilities"
f1_keywords:
 - "ehstorbandmgmt/BAND_MANAGEMENT_CAPABILITIES"
 - "BAND_MANAGEMENT_CAPABILITIES"
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
- BAND_MANAGEMENT_CAPABILITIES
product:
- Windows
targetos: Windows
req.typenames: BAND_MANAGEMENT_CAPABILITIES, *PBAND_MANAGEMENT_CAPABILITIES
---

# _BAND_MANAGEMENT_CAPABILITIES structure


## -description


The <b>BAND_MANAGEMENT_CAPABILITIES</b> structure contains the security capabilities available for a storage device. This structure is returned in the system buffer by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_query_capabilities">IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES</a> request.


## -struct-fields




### -field StructSize

The size of this structure in bytes. Set to <b>sizeof</b>(BAND_MANAGEMENT_CAPABILITIES).


### -field Capabilities

Security capability flags for a storage device. This is a bitwise OR value of the following flags.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="CAPS_ACTIVATED"></a><a id="caps_activated"></a><dl>
<dt><b>CAPS_ACTIVATED</b></dt>
</dl>
</td>
<td width="60%">
If set, the capability members of this structure are available. Otherwise, the remaining members of this structure are not valid.

</td>
</tr>
<tr>
<td width="40%"><a id="CAPS_BANDCROSSING_SUPPORTED"></a><a id="caps_bandcrossing_supported"></a><dl>
<dt><b>CAPS_BANDCROSSING_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The storage device supports reads and writes across multiple bands. If this flag is not set, single reads or writes  spanning multiple bands are divided into multiple IO requests for a device.

</td>
</tr>
<tr>
<td width="40%"><a id="CAPS_SID_SECURED"></a><a id="caps_sid_secured"></a><dl>
<dt><b>CAPS_SID_SECURED</b></dt>
</dl>
</td>
<td width="60%">
SID authority is secured. If set, the default SID pin cannot be used to modify the security configuration of the storage device.

</td>
</tr>
</table>
 


### -field KeyProtectionMechanism

The mechanism used to protect the media keys. This member is set to one of the following.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="0"></a><dl>
<dt><b>0</b></dt>
</dl>
</td>
<td width="60%">
Keys are not protected.

</td>
</tr>
<tr>
<td width="40%"><a id="MEDIAKEY_PROTECTEDBY_VENDORSCHEME"></a><a id="mediakey_protectedby_vendorscheme"></a><dl>
<dt><b>MEDIAKEY_PROTECTEDBY_VENDORSCHEME</b></dt>
</dl>
</td>
<td width="60%">
Keys are protected by a vendor-supplied method. Do not use. This option is not supported.

</td>
</tr>
<tr>
<td width="40%"><a id="MEDIAKEY_PROTECTEDBY_AUTHKEY"></a><a id="mediakey_protectedby_authkey"></a><dl>
<dt><b>MEDIAKEY_PROTECTEDBY_AUTHKEY</b></dt>
</dl>
</td>
<td width="60%">
Keys are encrypted by keys derived from band authentication keys. Key derivation results in negligible entropy loss from the band authentication data.

</td>
</tr>
</table>
 


### -field MinAuthKeyLength

The minimum length, in bytes, of the  band authentication or erase keys accepted by the storage device.


### -field MaxAuthKeyLength

The maximum length, in bytes, of the  band authentication or erase keys accepted by the storage device.


### -field MaxBandCount

The maximum number of simultaneous bands configured in the storage device. This includes the global band.


### -field MaxSimultaneousReencryptionCount

The number of simultaneous band re-encryptions the hardware on the device supports. If this member is 0, hardware-driven band re-encryptions are not supported.


### -field BandMetadataSize

The size, in bytes, of the per band metadata store.


## -remarks



If <b>CAPS_ACTIVATED</b> is not set in <b>Capabilities</b>, security functionality can be activated with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_activate">IOCTL_EHSTOR_BANDMGMT_ACTIVATE</a> request.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_activate">IOCTL_EHSTOR_BANDMGMT_ACTIVATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_query_capabilities">IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES</a>
 

 

