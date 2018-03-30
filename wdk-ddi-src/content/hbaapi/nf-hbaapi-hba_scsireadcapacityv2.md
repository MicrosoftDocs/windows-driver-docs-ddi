---
UID: NF:hbaapi.HBA_ScsiReadCapacityV2
title: HBA_ScsiReadCapacityV2 function
author: windows-driver-content
description: The HBA_ScsiReadCapacityV2 routine sends a SCSI read capacity command to the indicated remote port.
old-location: storage\hba_scsireadcapacityv2.htm
old-project: storage
ms.assetid: 8347e1ef-1285-43a9-bea7-a9a59ec0dfd0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: HBA_ScsiReadCapacityV2, HBA_ScsiReadCapacityV2 routine [Storage Devices], fibreHBA_rtns_8ac08e6d-79aa-4eee-a352-aa8ff51ec85f.xml, hbaapi/HBA_ScsiReadCapacityV2, storage.hba_scsireadcapacityv2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Hbaapi.dll
api_name:
-	HBA_ScsiReadCapacityV2
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_ScsiReadCapacityV2 function


## -description


The <b>HBA_ScsiReadCapacityV2</b> routine sends a SCSI read capacity command to the indicated remote port. 


## -parameters




### -param HbaHandle [in]

Contains a value returned by the routine <a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a> that identifies the HBA through which the SCSI read capacity command is sent.


### -param HbaPortWWN [in]

Contains a 64-bit worldwide name (WWN) that uniquely identifies the local HBA port from which the SCSI inquiry command is sent. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification. 


### -param DiscoveredPortWWN

TBD


### -param FcLUN

TBD


### -param pRespBuffer [out]

Pointer to a buffer that receives the output data of the SCSI read capacity command.


### -param pRespBufferSize [in, out]

Indicates the size, in bytes, of the buffer at <i>pRespBuffer</i>.


### -param pScsiStatus [out]

Pointer to a buffer that receives the SCSI status data. 


### -param pSenseBuffer [out]

Pointer to a buffer that receives the SCSI sense data.


### -param pSenseBufferSize [in, out]

On input, indicates the size, in bytes, of the buffer at <i>pSenseBuffer</i>. On output, this member indicates the number of bytes of sense data returned.


#### - discoveredPortWWN [in]

Contains a 64-bit WWN that uniquely identifies the remote HBA port to which the SCSI read capacity command is sent. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification. 


#### - fcLUN [in]

Indicates the fibre channel logical unit number of the logical unit to which the SCSI read capacity command will be sent. 


## -returns



The <b>HBA_ScsiReadCapacityV2</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_ScsiReadCapacityV2</b> returns one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>
</td>
<td width="60%">
Returned if the complete payload of a reply to the SCSI read capacity command was successfully retrieved. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_ILLEGAL_WWN</b></dt>
</dl>
</td>
<td width="60%">
Returned if the HBA referenced by <i>handle</i> does not contain a port with a name that matches <i>HbaPortWWN</i>. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_NOT_A_TARGET</b></dt>
</dl>
</td>
<td width="60%">
Returned if the specified remote port referenced by <i>discoveredPortWWN </i>does not have SCSI target functionality.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_TARGET_BUSY</b></dt>
</dl>
</td>
<td width="60%">
Returned if the SCSI read capacity command could not be delivered without causing a SCSI overlapped command condition.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_SCSI_CHECK_CONDITION</b></dt>
</dl>
</td>
<td width="60%">
Returned if a SCSI check condition occurred and SCSI send data is provided in the buffer at <i>pSenseBuffer</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Returned if an unspecified error occurred that prevented the execution of the SCSI inquiry command. 

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
 

 

