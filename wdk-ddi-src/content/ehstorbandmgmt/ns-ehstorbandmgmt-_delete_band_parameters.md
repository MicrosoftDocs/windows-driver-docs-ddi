---
UID: NS:ehstorbandmgmt._DELETE_BAND_PARAMETERS
title: "_DELETE_BAND_PARAMETERS"
author: windows-driver-content
description: A configured band is deleted according to the parameters in a DELETE_BAND_PARAMETERS structure. This structure is input for an IOCTL_EHSTOR_BANDMGMT_DELETE_BAND request.
old-location: storage\delete_band_parameters.htm
old-project: storage
ms.assetid: 6C96CF49-A7B2-4A99-8C7A-FC1C8C389C18
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PDELETE_BAND_PARAMETERS, DELBAND_ERASE_BEFORE_DELETE, DELETE_BAND_PARAMETERS, DELETE_BAND_PARAMETERS structure [Storage Devices], PDELETE_BAND_PARAMETERS, PDELETE_BAND_PARAMETERS structure pointer [Storage Devices], _DELETE_BAND_PARAMETERS, ehstorbandmgmt/DELETE_BAND_PARAMETERS, ehstorbandmgmt/PDELETE_BAND_PARAMETERS, storage.delete_band_parameters"
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
-	DELETE_BAND_PARAMETERS
product: Windows
targetos: Windows
req.typenames: DELETE_BAND_PARAMETERS, *PDELETE_BAND_PARAMETERS
---

# _DELETE_BAND_PARAMETERS structure


## -description


A configured band is deleted according to the parameters in a <b>DELETE_BAND_PARAMETERS</b> structure. This structure is input for an <a href="https://msdn.microsoft.com/CA0002E6-D9E7-417B-AD48-32E25E24EC32"> IOCTL_EHSTOR_BANDMGMT_DELETE_BAND</a> request.


## -struct-fields




### -field StructSize

The size of this structure in bytes. Set to <b>sizeof</b>(DELETE_BAND_PARAMETERS).


### -field Flags

Delete operation flags. This value is a bitwise OR combination of the following.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="DELBAND_ERASE_BEFORE_DELETE"></a><a id="delband_erase_before_delete"></a><dl>
<dt><b>DELBAND_ERASE_BEFORE_DELETE</b></dt>
</dl>
</td>
<td width="60%">
Perform a cryptographic erase of the band property data before delete.

</td>
</tr>
</table>
 


### -field Reserved

Reserved.


### -field BandId

The identifier of a single band to return information for. <b>BandSize</b> must be 0 when a single band is selected  with <b>BandId</b>. To use <b>BandStart</b> and <b>BandSize</b> instead of <b>BandId</b> to select a band, set <b>BandId</b> = (ULONG) –1.


### -field BandStart

The starting byte location on the storage device to begin a band search. An attempt is made to match a band at or after <b>BandStart</b>.


### -field AuthKeyOffset

The offset, in bytes, of an  <b> AUTH_KEY</b> structure containing the authorization key for the band. The offset is from the beginning of <b>DELETE_BAND_PARAMETERS</b>. <b>AUTH_KEY</b> is declared in <i>ehstorbandmgmt.h</i> as the following.

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

To specify a default authentication key to the band, set   <b>AuthKeyOffset</b> = <b>EHSTOR_BANDMGR_NO_KEY</b>. If <b>Flags</b> contains <b>DELBAND_ERASE_BEFORE_DELETE</b>, <b>AuthKeyOffset</b> must be set to <b>EHSTOR_BANDMGR_NO_KEY</b>.


## -remarks



 Precedence is given to <b>BandID</b> for band selection. If <b>BandID</b>  is greater than   0 and  <b>BandID</b>  is less than the  <b>MaxBandCount</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/hh439563">BAND_MANAGEMENT_CAPABILITIES</a>, then   <b>BandID</b> is used as the only selection criteria for a band match. If  <b>BandID</b> == –1, then <b>BandStart</b> is used as  the match criteria to select a band. If no band matches either selection criteria, then STATUS_INVALID_PARAMETER is returned in the <i>IoStatus</i> block for <a href="https://msdn.microsoft.com/library/windows/hardware/hh451376">IOCTL_EHSTOR_BANDMGMT_DELETE_BAND</a>.

If <b>DELBAND_ERASE_BEFORE_DELETE</b> is set in <b>Flags</b>, then an authentication key is not needed to delete the band. If this flag is not set, the current authentication key must be included at <b>AuthKeyOffset</b>.

.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439563">BAND_MANAGEMENT_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451376">IOCTL_EHSTOR_BANDMGMT_DELETE_BAND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451383">IOCTL_EHSTOR_BANDMGMT_ERASE_BAND</a>
 

 

