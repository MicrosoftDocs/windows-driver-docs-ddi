---
UID: NS:ehstorbandmgmt._ERASE_BAND_PARAMETERS
title: "_ERASE_BAND_PARAMETERS"
author: windows-driver-content
description: The ERASE_BAND_PARAMETERS structure contains the selection criteria for a band to erase. Additionally, a new authentication key can be set. This structure is input for an IOCTL_EHSTOR_BANDMGMT_ERASE_BAND request.
old-location: storage\erase_band_parameters.htm
old-project: storage
ms.assetid: CD7388DD-84CD-4158-91F3-9DB0559DFC2F
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PERASE_BAND_PARAMETERS, *PERASE_BAND_PARAMETERS, ehstorbandmgmt/PERASE_BAND_PARAMETERS, PERASE_BAND_PARAMETERS structure pointer [Storage Devices], ehstorbandmgmt/ERASE_BAND_PARAMETERS, storage.erase_band_parameters, ERASEBAND_AUTHKEY_CACHING_ENABLED, ERASE_BAND_PARAMETERS structure [Storage Devices], _ERASE_BAND_PARAMETERS, ERASE_BAND_PARAMETERS
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
-	ERASE_BAND_PARAMETERS
product: Windows
targetos: Windows
req.typenames: "*PERASE_BAND_PARAMETERS, ERASE_BAND_PARAMETERS"
---

# _ERASE_BAND_PARAMETERS structure


## -description


The <b>ERASE_BAND_PARAMETERS</b> structure contains the selection criteria for a band to erase. Additionally, a new authentication key can be set. This structure is input for an <a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_erase_band.md"> IOCTL_EHSTOR_BANDMGMT_ERASE_BAND</a> request.


## -syntax


````
typedef struct _ERASE_BAND_PARAMETERS {
  ULONG         StructSize;
  ULONG         Flags;
  ULONG         Reserved;
  ULONG         BandId;
  LARGE_INTEGER BandStart;
  ULONG         NewAuthKeyOffset;
} ERASE_BAND_PARAMETERS, *PERASE_BAND_PARAMETERS;
````


## -struct-fields




### -field StructSize

The size of this structure in bytes. Set to <b>sizeof</b>(ERASE_BAND_PARAMETERS).


### -field Flags

Delete operation flags. This value is a bitwise OR combination of the following.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="ERASEBAND_AUTHKEY_CACHING_ENABLED"></a><a id="eraseband_authkey_caching_enabled"></a><dl>
<dt><b>ERASEBAND_AUTHKEY_CACHING_ENABLED</b></dt>
</dl>
</td>
<td width="60%">
The new authentication key for this band is cached allowing for automation of later operations.

</td>
</tr>
</table>
 


### -field Reserved

Reserved.


### -field BandId

The identifier of a single band to return information for. <b>BandSize</b> must be 0 when a single band is selected  with <b>BandId.</b> To use <b>BandStart</b> and <b>BandSize</b> instead of <b>BandId</b> to select a band, set <b>BandId</b> = (ULONG) –1.


### -field BandStart

The starting byte location on the storage device to begin a band search. An attempt is made to match a band at or after <b>BandStart</b>.


### -field NewAuthKeyOffset

The offset, in bytes, of an  <b> AUTH_KEY</b> structure containing the new authorization key for the band. The offset is from the beginning of <b>ERASE_BAND_PARAMETERS</b>. <b>AUTH_KEY</b> is declared in <i>ehstorbandmgmt.h</i> as the following.

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

To specify a default authentication key to the band, set   <b>NewAuthKeyOffset</b> = <b>EHSTOR_BANDMGR_NO_KEY</b>.


## -remarks



 Precedence is given to <b>BandID</b> for band selection.  If <b>BandID</b>  is greater than   0 and  <b>BandID</b>  is less than the  <b>MaxBandCount</b> member of <a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_management_capabilities.md">BAND_MANAGEMENT_CAPABILITIES</a>, then   <b>BandID</b> is used as the only selection criteria for a band match. If  <b>BandID</b> == –1, then <b>BandStart</b> is used as  the match criteria to select a band. If no band matches either selection criteria, then STATUS_INVALID_PARAMETER is returned in the <i>IoStatus</i> block for <a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_erase_band.md">IOCTL_EHSTOR_BANDMGMT_ERASE_BAND</a>.

.




## -see-also

<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_management_capabilities.md">BAND_MANAGEMENT_CAPABILITIES</a>



<a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_erase_band.md">IOCTL_EHSTOR_BANDMGMT_ERASE_BAND</a>



<a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_delete_band.md">IOCTL_EHSTOR_BANDMGMT_DELETE_BAND</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ERASE_BAND_PARAMETERS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

