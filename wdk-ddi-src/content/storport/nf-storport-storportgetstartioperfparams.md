---
UID: NF:storport.StorPortGetStartIoPerfParams
title: StorPortGetStartIoPerfParams function (storport.h)
description: The StorPortGetStartIoPerfParams routine places the performance parameters for a given I/O request in a STARTIO_PERFORMANCE_PARAMETERS structure.
old-location: storage\storportgetstartioperfparams.htm
tech.root: storage
ms.assetid: c3314ac6-2b46-417f-a87b-64e27df9686d
ms.date: 03/29/2018
ms.keywords: StorPortGetStartIoPerfParams, StorPortGetStartIoPerfParams routine [Storage Devices], storage.storportgetstartioperfparams, storport/StorPortGetStartIoPerfParams, storprt_ad7184c9-2f69-4571-ba56-28b5a3b353d7.xml
f1_keywords:
 - "storport/StorPortGetStartIoPerfParams"
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
- StorPortGetStartIoPerfParams
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortGetStartIoPerfParams function


## -description


The <b>StorPortGetStartIoPerfParams</b> routine places the performance parameters for a given I/O request in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_startio_performance_parameters">STARTIO_PERFORMANCE_PARAMETERS</a> structure.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Srb [in]

The SRB pointer that was passed in to the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_startio">HwStorStartIo</a> routine that was supplied by the miniport driver. This parameter must not be <b>NULL</b>.


### -param StartIoPerfParams [in, out]

A pointer to a STARTIO_PERFORMANCE_PARAMETERS structure that the miniport driver supplies.  The miniport driver needs to set only the size of the allocated structure, as Storport will set the other members. This parameter must not be <b>NULL</b>.


## -returns



StorPortGetStartIoPerfParams returns one of the following status values:

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
Indicates that the performance parameters have been stored in <i>StartIoPerfParams</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Either the <i>Srb</i> parameter or the <i>StartIoPerfParams</i> parameter is <b>NULL</b>.

-or-

The <i>HwDeviceExtension</i> parameter is NULL or not valid.

-or-

The <i>Srb</i> parameter is not pointing to an SRB sent by Storport

-or-

The structure pointed to by <i>StartIoPerfParams</i> is not valid because the value of its <b>Size</b> member indicates that structure is too small to contain the returned data.

</td>
</tr>
</table>
 




## -remarks



Starting in Windows 8, the <i>Srb</i> parameter may point to either <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_storage_request_block">STORAGE_REQUEST_BLOCK</a>. If the function identifier in the <b>Function</b> field of <i>Srb</i> is <b>SRB_FUNCTION_STORAGE_REQUEST_BLOCK</b>, the SRB is a <b>STORAGE_REQUEST_BLOCK</b> request structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_startio_performance_parameters">STARTIO_PERFORMANCE_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_storage_request_block">STORAGE_REQUEST_BLOCK</a>
 

 

