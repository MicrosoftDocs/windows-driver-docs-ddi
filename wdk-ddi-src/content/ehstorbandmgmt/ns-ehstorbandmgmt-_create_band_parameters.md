---
UID: NS:ehstorbandmgmt._CREATE_BAND_PARAMETERS
title: "_CREATE_BAND_PARAMETERS"
author: windows-driver-content
description: The parameters to create a band on a storage device for an IOCTL_EHSTOR_BANDMGMT_CREATE_BAND request are specified in a CREATE_BAND_PARAMETERS structure.
old-location: storage\create_band_parameters.htm
old-project: storage
ms.assetid: DFDD92F8-95B7-40F7-950C-A105F035B2E9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PCREATE_BAND_PARAMETERS, CREATEBAND_AUTHKEY_CACHING_ENABLED, CREATE_BAND_PARAMETERS, CREATE_BAND_PARAMETERS structure [Storage Devices], PCREATE_BAND_PARAMETERS, PCREATE_BAND_PARAMETERS structure pointer [Storage Devices], _CREATE_BAND_PARAMETERS, ehstorbandmgmt/CREATE_BAND_PARAMETERS, ehstorbandmgmt/PCREATE_BAND_PARAMETERS, storage.create_band_parameters"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	CREATE_BAND_PARAMETERS
product: Windows
targetos: Windows
req.typenames: CREATE_BAND_PARAMETERS, *PCREATE_BAND_PARAMETERS
---

# _CREATE_BAND_PARAMETERS structure


## -description


The parameters to create a band on a storage device for an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451372">IOCTL_EHSTOR_BANDMGMT_CREATE_BAND</a> request are specified in a <b>CREATE_BAND_PARAMETERS</b> structure.


## -struct-fields




### -field StructSize

The size of this structure in bytes. Set to <b>sizeof</b>(CREATE_BAND_PARAMETERS).


### -field Flags

Band creation flags. This value is a bitwise OR combination of the following.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="CREATEBAND_AUTHKEY_CACHING_ENABLED"></a><a id="createband_authkey_caching_enabled"></a><dl>
<dt><b>CREATEBAND_AUTHKEY_CACHING_ENABLED</b></dt>
</dl>
</td>
<td width="60%">
The authentication key for this band is cached, which allows automation of later operations. The authentication key is cached when this flag is set and the band is not locked for both reading and writing.

</td>
</tr>
</table>
 


### -field BandLocationInfoOffset

The offset, in bytes, of a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439557">BAND_LOCATION_INFO</a> structure. The offset is from the beginning of <b>CREATE_BAND_PARAMETERS</b>.


### -field BandSecurityInfoOffset

The offset, in bytes, of a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439568">BAND_SECURITY_INFO</a> structure. The offset is from the beginning of <b>CREATE_BAND_PARAMETERS</b>. If this value is 0, meaning band security info is not present, key manager metadata for the band is set to all zeros. Also, when this member is 0, the read and write lock states default to PERSISTANT_UNLOCK.


### -field AuthKeyOffset

The offset, in bytes, of an  <b> AUTH_KEY</b> structure that contains the authorization key for the new band. The offset is from the beginning of <b>CREATE_BAND_PARAMETERS</b>. <b>AUTH_KEY</b> is declared in <i>ehstorbandmgmt.h</i> as the following.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _AUTH_KEY
{
    ULONG   KeySize;
    UCHAR   Key[ANYSIZE_ARRAY];
} AUTH_KEY;</pre>
</td>
</tr>
</table></span></div>




#### KeySize

The size of the key, in bytes, of the key data at <b>Key</b>. If <b>KeySize</b> is set to 0, a default key is used.



#### Key

A variable length byte array that contains the key data.

To assign a default authorization key to the band, set   <b>AuthKeyOffset</b> = <b>EHSTOR_BANDMGR_NO_KEY</b>.


## -remarks



The <b>CryptoAlgoIdType</b> and <b>CryptoAlgoOidString</b> members of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439568">BAND_SECURITY_INFO</a> structure at <b>BandSecurityInfoOffset</b> are not used in a band creation request and must be set to 0.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439557">BAND_LOCATION_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439568">BAND_SECURITY_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451372">IOCTL_EHSTOR_BANDMGMT_CREATE_BAND</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CREATE_BAND_PARAMETERS structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

