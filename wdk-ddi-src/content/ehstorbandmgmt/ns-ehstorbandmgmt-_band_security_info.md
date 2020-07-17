---
UID: NS:ehstorbandmgmt._BAND_SECURITY_INFO
title: _BAND_SECURITY_INFO (ehstorbandmgmt.h)
description: The BAND_SECURITY_INFO structure specifies the security information for a band table entry query.
old-location: storage\band_security_info.htm
tech.root: storage
ms.assetid: 310F996F-F350-4F25-BC8A-386513908557
ms.date: 03/29/2018
keywords: ["_BAND_SECURITY_INFO structure"]
ms.keywords: "*PBAND_SECURITY_INFO, BAND_LOCATION_INFO, BAND_LOCATION_INFO structure [Storage Devices], BAND_SECURITY_INFO, BAND_SECURITY_INFO structure [Storage Devices], PBAND_LOCATION_INFO, PBAND_LOCATION_INFO structure pointer [Storage Devices], _BAND_SECURITY_INFO, ehstorbandmgmt/BAND_SECURITY_INFO, ehstorbandmgmt/PBAND_LOCATION_INFO, storage.band_security_info"
f1_keywords:
 - "ehstorbandmgmt/BAND_LOCATION_INFO"
 - "BAND_LOCATION_INFO"
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
- BAND_LOCATION_INFO
product:
- Windows
targetos: Windows
req.typenames: BAND_SECURITY_INFO, *PBAND_SECURITY_INFO
---

# _BAND_SECURITY_INFO structure


## -description


The <b>BAND_SECURITY_INFO</b> structure specifies the security information for a band table entry query.


## -struct-fields




### -field StructSize

The size of the structure in bytes. Set to <b>sizeof</b>(BAND_SECURITY_INFO).


### -field ReadLock

Whether the band is accessible for reading and how a read lock is affected by a power reset.


### -field WriteLock

Whether the band is accessible for writing and how a write lock is affected by a power reset.


### -field CryptoAlgoIdType

The type of encryption algorithm identifier used. This must be set to <b>AlgoIdTypeOidString</b>.


### -field CryptoAlgoOidString

The encryption algorithm used to protect the data in the band.


### -field CryptoAlgoOidString.Offset

The offset from the beginning of this structure where the encryption algorithm OID string begins.


### -field CryptoAlgoOidString.Length

The length of the OID string identifying the encryption algorithm. This is a byte-length value including a NULL terminator for the OID string.


### -field CryptoAlgoNumericId

Reserved.


### -field Metadata

A metadata field available for use by a key manager.


## -remarks



Both <b>Readlock</b> and <b>Writelock</b> are <b>LOCKSTATE</b> values and indicate locking state and lock persistence. Their values are one of the following.

<table>
<tr>
<th>Lock State</th>
<th>Description</th>
</tr>
<tr>
<td>INVALID_LOCK_STATE</td>
<td>The lock state is not valid.</td>
</tr>
<tr>
<td>PERSISTENT_UNLOCK</td>
<td>The device is unlocked and remains unlocked during power reset.</td>
</tr>
<tr>
<td>NONPERSISTENT_UNLOCK</td>
<td>The device is unlocked but becomes locked during power reset.</td>
</tr>
<tr>
<td>PERSISTENT_LOCK</td>
<td>The device is locked and remains locked during power reset.</td>
</tr>
</table>
 

<b>CryptoAlgoOidString</b>  specifies the data encryption algorithm only if <b>ENUMBANDS_REPORT_CRYPTO_ALGO</b> is set in the <b>Flags</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_enumerate_bands_parameters">ENUMERATE_BANDS_PARAMETERS</a> in an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_enumerate_bands">IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS</a> request. Otherwise, both <b>CryptoAlgoOidString.Offset</b> and <b>CryptoAlgoOidString.Length</b> are set to 0. The following are possible encryption algorithm OID strings returned for <b>CryptoAlgoOidString</b>.

<table>
<tr>
<th>Algorithm</th>
<th>OID</th>
</tr>
<tr>
<td>IAES128-ECB</td>
<td>2.16.840.1.101.3.4.1.1</td>
</tr>
<tr>
<td>AES128-CBC</td>
<td>2.16.840.1.101.3.4.1.2.</td>
</tr>
<tr>
<td>AES128-OFB</td>
<td>2.16.840.1.101.3.4.1.3</td>
</tr>
<tr>
<td>AES128-CFB</td>
<td>2.16.840.1.101.3.4.1.4</td>
</tr>
<tr>
<td>AES128-XTS</td>
<td>1.3.111.2.1619.0.1.1</td>
</tr>
<tr>
<td>AES256-ECB</td>
<td>2.16.840.1.101.3.4.1.41</td>
</tr>
<tr>
<td>AES256-CBC</td>
<td>2.16.840.1.101.3.4.1.42</td>
</tr>
<tr>
<td>AES256-OFB</td>
<td>2.16.840.1.101.3.4.1.43</td>
</tr>
<tr>
<td>AES256-CFB</td>
<td>2.16.840.1.101.3.4.1.44</td>
</tr>
<tr>
<td>AES256-XTS</td>
<td>1.3.111.2.1619.0.1.2</td>
</tr>
</table>
 

When <b>BAND_SECURITY_INFO</b> is used in an input parameter set, <b>CryptoAlgoIdType</b> and <b>CryptoAlgoOidString</b> are not used and must be set to 0.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_band_table_entry">BAND_TABLE_ENTRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ns-ehstorbandmgmt-_enumerate_bands_parameters">ENUMERATE_BANDS_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_create_band">IOCTL_EHSTOR_BANDMGMT_CREATE_BAND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorbandmgmt/ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_enumerate_bands">IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS</a>
 

 

