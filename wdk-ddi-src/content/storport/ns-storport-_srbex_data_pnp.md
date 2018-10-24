---
UID: NS:storport._SRBEX_DATA_PNP
title: "_SRBEX_DATA_PNP"
author: windows-driver-content
description: The SRBEX_DATA_PNP structure contains the request data for an extended plug and play (PNP) SRB.
old-location: storage\srbex_data_pnp.htm
tech.root: storage
ms.assetid: CB64AF68-C40D-44F0-8F52-6BF05E23E5E1
ms.date: 03/29/2018
ms.keywords: "*PSRBEX_DATA_PNP, PSRBEX_DATA_PNP, PSRBEX_DATA_PNP structure pointer [Storage Devices], SRBEX_DATA_PNP, SRBEX_DATA_PNP structure [Storage Devices], StorFilterResourceRequirements, StorQueryCapabilities, StorQueryResourceRequirements, StorRemoveDevice, StorStartDevice, StorStopDevice, StorSupriseRemoval, _SRBEX_DATA_PNP, storage.srbex_data_pnp, storport/PSRBEX_DATA_PNP, storport/SRBEX_DATA_PNP"
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h, Srb.h, Minitape.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
-	Storport.h
api_name:
-	SRBEX_DATA_PNP
product:
- Windows
targetos: Windows
req.typenames: SRBEX_DATA_PNP, *PSRBEX_DATA_PNP
---

# _SRBEX_DATA_PNP structure


## -description


The <b>SRBEX_DATA_PNP</b> structure contains the request data for an extended plug and play (PNP) SRB.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -struct-fields




### -field Type

Data type indicator for the bidirectional extended SRB data structure. Set to <b>SrbExDataTypePnp</b>.


### -field Length

Length of the data in this structure starting with the <b>PnPSubFunction</b> member. Set to SRBEX_DATA_PNP_LENGTH.


### -field PnPSubFunction

This member is not currently used. Set to 0.


### -field Reserved

This member is reserved. Set to 0.


### -field PnPAction

The plug and play action to perform. This member can have one of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="StorStartDevice"></a><a id="storstartdevice"></a><a id="STORSTARTDEVICE"></a><dl>
<dt><b>StorStartDevice</b></dt>
<dt>0x00</dt>
</dl>
</td>
<td width="60%">
Start the device.

</td>
</tr>
<tr>
<td width="40%"><a id="StorRemoveDevice"></a><a id="storremovedevice"></a><a id="STORREMOVEDEVICE"></a><dl>
<dt><b>StorRemoveDevice</b></dt>
<dt>0x02</dt>
</dl>
</td>
<td width="60%">
Remove the device.

</td>
</tr>
<tr>
<td width="40%"><a id="StorStopDevice"></a><a id="storstopdevice"></a><a id="STORSTOPDEVICE"></a><dl>
<dt><b>StorStopDevice</b></dt>
<dt>0x04</dt>
</dl>
</td>
<td width="60%">
Stop the device.

</td>
</tr>
<tr>
<td width="40%"><a id="StorQueryCapabilities"></a><a id="storquerycapabilities"></a><a id="STORQUERYCAPABILITIES"></a><dl>
<dt><b>StorQueryCapabilities</b></dt>
<dt>0x09</dt>
</dl>
</td>
<td width="60%">
Query the capabilities of the device.

</td>
</tr>
<tr>
<td width="40%"><a id="StorQueryResourceRequirements"></a><a id="storqueryresourcerequirements"></a><a id="STORQUERYRESOURCEREQUIREMENTS"></a><dl>
<dt><b>StorQueryResourceRequirements</b></dt>
<dt>0x0B</dt>
</dl>
</td>
<td width="60%">
Query the resource requirements for the device.

</td>
</tr>
<tr>
<td width="40%"><a id="StorFilterResourceRequirements"></a><a id="storfilterresourcerequirements"></a><a id="STORFILTERRESOURCEREQUIREMENTS"></a><dl>
<dt><b>StorFilterResourceRequirements</b></dt>
<dt>0x0D</dt>
</dl>
</td>
<td width="60%">
Filter the resource requirements for the device. 

</td>
</tr>
<tr>
<td width="40%"><a id="StorSupriseRemoval"></a><a id="storsupriseremoval"></a><a id="STORSUPRISEREMOVAL"></a><dl>
<dt><b>StorSupriseRemoval</b></dt>
<dt>0x17</dt>
</dl>
</td>
<td width="60%">
Surprise Removal of the device. This value is available starting with Windows 7.

</td>
</tr>
</table>
 


### -field SrbPnPFlags

Indicates that the PNP request is for the adapter if SRB_PNP_FLAGS_ADAPTER_REQUEST is set and that storage device address is reserved. Otherwise, <i>SrbPnPFlags</i> will be <b>NULL</b>, indicating that the request is for the storage device specified by an address at <b>AddressOffset</b> in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451474">STORAGE_REQUEST_BLOCK</a> structure.


### -field Reserved1

This member is reserved. Set to 0.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451474">STORAGE_REQUEST_BLOCK</a>
 

 

