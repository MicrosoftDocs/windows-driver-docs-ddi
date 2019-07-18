---
UID: NF:storport.StorPortGetOriginalMdl
title: StorPortGetOriginalMdl function (storport.h)
description: The StorPortGetOriginalMdl routine returns the MDL associated with the given SRB.
old-location: storage\storportgetoriginalmdl.htm
tech.root: storage
ms.assetid: 48042e9d-ed83-4326-931d-ded753deb1a7
ms.date: 03/29/2018
ms.keywords: StorPortGetOriginalMdl, StorPortGetOriginalMdl routine [Storage Devices], storage.storportgetoriginalmdl, storport/StorPortGetOriginalMdl, storprt_4617200d-18b4-4ee2-aa43-92fc5f3a7b66.xml
ms.topic: function
f1_keywords:
 - "storport/StorPortGetOriginalMdl"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- storport.h
api_name:
- StorPortGetOriginalMdl
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortGetOriginalMdl function


## -description


The <b>StorPortGetOriginalMdl</b> routine returns the MDL associated with the given SRB.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Srb [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a> structure.


### -param Mdl [out]

A pointer to receive the MDL.


## -returns



StorPortGetOriginalMdl returns one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This function is not implemented on the active operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the MDL was obtained successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The pointer in <i>Mdl</i> receiving the SRB's MDL  is <b>NULL</b>.

</td>
</tr>
</table>
 




## -remarks



Starting in Windows 8, the <i>Srb</i> parameter may point to either <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_storage_request_block">STORAGE_REQUEST_BLOCK</a>. If the function identifier in the <b>Function</b> field of <i>Srb</i> is <b>SRB_FUNCTION_STORAGE_REQUEST_BLOCK</b>, the SRB is a <b>STORAGE_REQUEST_BLOCK</b> request structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_storage_request_block">STORAGE_REQUEST_BLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportgetsystemaddress">StorPortGetSystemAddress</a>
 

 

