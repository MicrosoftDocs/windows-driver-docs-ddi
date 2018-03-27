---
UID: NS:ehstorbandmgmt._SET_BAND_LOCATION_PARAMETERS
title: "_SET_BAND_LOCATION_PARAMETERS"
author: windows-driver-content
description: The SET_BAND_LOCATION_PARAMETERS structure specifies the parameters to set location properties for a band on a storage device for a IOCTL_EHSTOR_BANDMGMT_SET_BAND_LOCATION request.
old-location: storage\set_band_location_parameters.htm
old-project: storage
ms.assetid: 43F60B45-A587-49FE-BB59-DC1215A46F04
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSET_BAND_LOCATION_PARAMETERS, PSET_BAND_LOCATION_PARAMETERS, PSET_BAND_LOCATION_PARAMETERS structure pointer [Storage Devices], SET_BAND_LOCATION_PARAMETERS, SET_BAND_LOCATION_PARAMETERS structure [Storage Devices], _SET_BAND_LOCATION_PARAMETERS, ehstorbandmgmt/PSET_BAND_LOCATION_PARAMETERS, ehstorbandmgmt/SET_BAND_LOCATION_PARAMETERS, storage.set_band_location_parameters"
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
-	SET_BAND_LOCATION_PARAMETERS
product: Windows
targetos: Windows
req.typenames: SET_BAND_LOCATION_PARAMETERS, *PSET_BAND_LOCATION_PARAMETERS
---

# _SET_BAND_LOCATION_PARAMETERS structure


## -description


The <a href="https://msdn.microsoft.com/library/windows/hardware/hh464113">SET_BAND_LOCATION_PARAMETERS</a> structure specifies the parameters to set location properties for a band on a storage device for a <a href="https://msdn.microsoft.com/library/windows/hardware/hh451397">IOCTL_EHSTOR_BANDMGMT_SET_BAND_LOCATION</a> request.


## -struct-fields




### -field StructSize

The size of this structure in bytes. Set to <b>sizeof</b>(SET_BAND_LOCATION_PARAMETERS).


### -field BandId

The identifier of a single band to return information for. <b>BandSize</b> must be 0 when a single band is selected  with <b>BandId.</b> To use <b>BandStart</b> and <b>BandSize</b> instead of <b>BandId</b> to select a band, set <b>BandId</b> = (ULONG) –1.


### -field BandStart

The starting byte location on the storage device to begin a band search. An attempt is made to match a band at or after <b>BandStart</b>.


### -field AuthKeyOffset

The offset, in bytes, of an  <b> AUTH_KEY</b> structure containing the authorization key for the band. The offset is from the beginning of <a href="https://msdn.microsoft.com/library/windows/hardware/hh464113">SET_BAND_LOCATION_PARAMETERS</a>. <b>AUTH_KEY</b> is declared in <i>ehstorbandmgmt.h</i> as the following.

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

To specify a default authorization key to the band, set   <b>AuthKeyOffset</b> = <b>EHSTOR_BANDMGR_NO_KEY</b>.


### -field BandLocationInfoOffset

The offset, in bytes, of a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439557">BAND_LOCATION_INFO</a> structure. The offset is from the beginning of <a href="https://msdn.microsoft.com/library/windows/hardware/hh464113">SET_BAND_LOCATION_PARAMETERS</a>.


## -remarks



 Precedence is given to <b>BandID</b> for band selection. If <b>BandID</b>  is greater than   0 and  <b>BandID</b>  is less than the  <b>MaxBandCount</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/hh439563">BAND_MANAGEMENT_CAPABILITIES</a>, then   <b>BandID</b> is used as the only selection criteria for a band match. If  <b>BandID</b> == –1, then <b>BandStart</b> is used as  the match criteria to select a band. If no band matches either selection criteria, then STATUS_INVALID_PARAMETER is returned in the <i>IoStatus</i> block for <a href="https://msdn.microsoft.com/library/windows/hardware/hh451397">IOCTL_EHSTOR_BANDMGMT_SET_BAND_LOCATION</a>.

If <b>BandID</b> and <b>BandStart </b> are both set to –1,  then the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451397">IOCTL_EHSTOR_BANDMGMT_SET_BAND_LOCATION</a> request will change the properties of the global band.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439557">BAND_LOCATION_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439563">BAND_MANAGEMENT_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451397">IOCTL_EHSTOR_BANDMGMT_SET_BAND_LOCATION</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SET_BAND_LOCATION_PARAMETERS structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

