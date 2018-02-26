---
UID: NS:ehstorbandmgmt._SET_BAND_SECURITY_PARAMETERS
title: "_SET_BAND_SECURITY_PARAMETERS"
author: windows-driver-content
description: The parameters to set security properties for a band on a storage device for a IOCTL_EHSTOR_BANDMGMT_SET_BAND_SECURITY request are specified in a SET_BAND_SECURITY_PARAMETERS structure.
old-location: storage\set_band_security_parameters.htm
old-project: storage
ms.assetid: D1703D6F-A453-4E3E-8705-344469D61412
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PSET_BAND_SECURITY_PARAMETERS, ,, A, B, C, D, E, I, M, N, P, PSET_BAND_SECURITY_PARAMETERS, PSET_BAND_SECURITY_PARAMETERS structure pointer [Storage Devices], R, S, SETBANDSEC_AUTHKEY_CACHING_ENABLED, SET_BAND_SECURITY_PARAMETERS, SET_BAND_SECURITY_PARAMETERS structure [Storage Devices], T, U, Y, _, _SET_BAND_SECURITY_PARAMETERS, ehstorbandmgmt/PSET_BAND_SECURITY_PARAMETERS, ehstorbandmgmt/SET_BAND_SECURITY_PARAMETERS, storage.set_band_security_parameters"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	EhStorBandMgmt.h
apiname:
-	SET_BAND_SECURITY_PARAMETERS
product: Windows
targetos: Windows
req.typenames: SET_BAND_SECURITY_PARAMETERS, *PSET_BAND_SECURITY_PARAMETERS
---

# _SET_BAND_SECURITY_PARAMETERS structure


## -description


The parameters to set security properties for a band on a storage device for a <a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_set_band_security.md">IOCTL_EHSTOR_BANDMGMT_SET_BAND_SECURITY</a> request are specified in a <b>SET_BAND_SECURITY_PARAMETERS</b> structure.


## -syntax


````
typedef struct _SET_BAND_SECURITY_PARAMETERS {
  ULONG         StructSize;
  ULONG         Flags;
  ULONG         BandId;
  LARGE_INTEGER BandStart;
  ULONG         CurrentAuthKeyOffset;
  ULONG         NewAuthKeyOffset;
                BandSecurityInfoOffset;
} SET_BAND_SECURITY_PARAMETERS, *PSET_BAND_SECURITY_PARAMETERS;
````


## -struct-fields




### -field StructSize

The size of this structure in bytes. Set to <b>sizeof</b>(SET_BAND_SECURITY_PARAMETERS).


### -field Flags

Security parameter flags. This value is a bitwise OR combination of the following.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="SETBANDSEC_AUTHKEY_CACHING_ENABLED"></a><a id="setbandsec_authkey_caching_enabled"></a><dl>
<dt><b>SETBANDSEC_AUTHKEY_CACHING_ENABLED</b></dt>
</dl>
</td>
<td width="60%">
The new authentication key can be cached to automate some band operations.

</td>
</tr>
</table>
 


### -field Reserved

 


### -field BandId

The identifier of a single band to return information for. <b>BandSize</b> must be 0 when a single band is selected  with <b>BandId.</b> To use <b>BandStart</b> and <b>BandSize</b> instead of <b>BandId</b> to select a band, set <b>BandId</b> = (ULONG) –1.


### -field BandStart

The starting byte location on the storage device to begin a band search. An attempt is made to match a band at or after <b>BandStart</b>.


### -field CurrentAuthKeyOffset

The offset, in bytes, of an  <b> AUTH_KEY</b> structure containing the current authentication key for the band. This authentication key is required and must be present following this structure. The offset is from the beginning of <b>SET_BAND_SECURITY_PARAMETERS</b>. <b>AUTH_KEY</b> is declared in <i>ehstorbandmgmt.h</i> as the following.

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

A variable-length byte array containing the key data.

To specify a default authentication key to the band, set   <b>AuthKeyOffset</b> = <b>EHSTOR_BANDMGR_NO_KEY</b>.


### -field NewAuthKeyOffset

The offset, in bytes, of an  <b> AUTH_KEY</b> structure containing the new authentication key for the band.  The offset is from the beginning of <b>SET_BAND_SECURITY_PARAMETERS</b>. <b>AUTH_KEY</b> is declared in <i>ehstorbandmgmt.h</i> as the following.

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

A variable-length byte array that contains the key data.

To assign a default authentication key to the band, set   <b>AuthKeyOffset</b> = <b>EHSTOR_BANDMGR_NO_KEY</b>. If <b>NewAuthKeyOffset</b> == <b>CurrentAuthKeyOffset</b>, the authentication key for the band is left unchanged.


### -field BandSecurityInfoOffset

The offset, in bytes, of a <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_security_info.md">BAND_SECURITY_INFO</a> structure. The offset is from the beginning of <b>SET_BAND_SECURITY_PARAMETERS</b>.


## -remarks



 Precedence is given to <b>BandID</b> for band selection.  If <b>BandID</b>  is greater than   0 and  <b>BandID</b>  is less than the  <b>MaxBandCount</b> member of <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_management_capabilities.md">BAND_MANAGEMENT_CAPABILITIES</a>, then   <b>BandID</b> is used as the only selection criteria for a band match. If  <b>BandID</b> == –1, then <b>BandStart</b> is used as  the match criteria to select a band. If no band matches either selection criteria, then STATUS_INVALID_PARAMETER is returned in the <i>IoStatus</i> block for <a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_set_band_security.md">IOCTL_EHSTOR_BANDMGMT_SET_BAND_SECURITY</a>.

If <b>BandID</b> and <b>BandStart</b> are both set to –1,  then the <a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_set_band_security.md">IOCTL_EHSTOR_BANDMGMT_SET_BAND_SECURITY</a> request will change the properties of the global band.

<b>NewAuthKeyOffset</b> and <b>BandSecurityInfoOffset</b> are optional depending on the requirements of the operation. If only the authentication key is changed, then <b>NewAuthKeyOffset</b> is set to the location of the <b>AUTH_KEY</b> structure for the new key and <b>BandSecurityInfoOffset</b> is set to zero. Similarly, if only security properties are changed, <b>BandSecurityInfoOffset</b> is set to the location of <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_security_info.md">BAND_SECURITY_INFO</a> and <b>NewAuthKeyOffset</b> is set to 0.

The <b>CryptoAlgoIdType</b> and <b>CryptoAlgoOidString</b> members of the <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_security_info.md">BAND_SECURITY_INFO</a> structure at <b>BandSecurityInfoOffset</b> are not used in a band creation request and must be set to 0.




## -see-also

<a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_set_band_location.md">IOCTL_EHSTOR_BANDMGMT_SET_BAND_LOCATION</a>



<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_location_info.md">BAND_LOCATION_INFO</a>



<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_management_capabilities.md">BAND_MANAGEMENT_CAPABILITIES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SET_BAND_SECURITY_PARAMETERS structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

