---
UID: NC:scsiwmi.PSCSIWMI_SET_DATABLOCK
title: PSCSIWMI_SET_DATABLOCK
author: windows-driver-content
description: A miniport driver's HwScsiWmiSetDataBlock routine is called to change all data items in a single instance of a data block.
old-location: storage\hwscsiwmisetdatablock.htm
tech.root: storage
ms.assetid: 5523d4d6-8eb5-48eb-a652-6612101b8422
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HwScsiWmiSetDataBlock, HwScsiWmiSetDataBlock callback function [Storage Devices], PSCSIWMI_SET_DATABLOCK, PSCSIWMI_SET_DATABLOCK callback, Scsimini_b75fb6d1-48dc-4fcb-ae05-bf278c382ecf.xml, scsiwmi/HwScsiWmiSetDataBlock, storage.hwscsiwmisetdatablock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: scsiwmi.h
req.include-header: Scsiwmi.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	scsiwmi.h
api_name:
-	HwScsiWmiSetDataBlock
product:
- Windows
targetos: Windows
req.typenames: 
---

# PSCSIWMI_SET_DATABLOCK callback function


## -description


A miniport driver's <b>HwScsiWmiSetDataBlock</b> routine is called to change all data items in a single instance of a data block. This routine is optional.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param DeviceContext [in]

Points to the miniport driver-defined context value passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff564766">ScsiPortWmiDispatchFunction</a>. 


### -param RequestContext [in]

Points to the SCSIWMI_REQUEST_CONTEXT structure that the miniport driver passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff564766">ScsiPortWmiDispatchFunction</a>. 


### -param GuidIndex [in]

Specifies the data block by its index into the list of GUIDs in the SCSI_WMILIB_CONTEXT structure that the miniport driver passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff564766">ScsiPortWmiDispatchFunction</a>. 


### -param InstanceIndex [in]

If the block specified by <i>GuidIndex</i> has multiple instances, <i>InstanceIndex</i> specifies the instance.


### -param BufferSize [in]

Specifies the size in bytes of the buffer at <i>Buffer</i>.


### -param Buffer [in]

Points to a buffer that contains new values for the instance.


## -returns



<b>HwScsiWmiSetDataBlock</b> returns SRB_STATUS_PENDING if the request is pending, or a nonzero SRB status value if the request was completed.  The SRB status value returned by this routine is the same as what was passed in to <a href="https://msdn.microsoft.com/library/windows/hardware/ff564796">ScsiPortWmiPostProcess</a>.




## -remarks



When a miniport driver receives an SRB in which the <b>Function</b> member is set to SRB_FUNCTION_WMI, it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff564766">ScsiPortWmiDispatchFunction</a> with a pointer to an initialized SCSI_WMILIB_CONTEXT structure and <i>MinorFunction</i> set to <b>Srb-&gt;WmiSubFunction</b>. The SCSI port driver calls the miniport driver's <b>HwScsiWmiSetDataBlock</b> routine if <i>MinorFunction</i> indicates a request to change an instance of a data block.

If a miniport driver does not implement a <b>HwScsiWmiSetDataBlock</b> routine, it must set <b>SetWmiDataBlock</b> to <b>NULL</b> in the SCSI_WMILIB_CONTEXT the miniport driver passes to <a href="https://msdn.microsoft.com/library/windows/hardware/ff564766">ScsiPortWmiDispatchFunction</a>. In this case, the port driver returns SRB_STATUS_ERROR to the caller.

If the miniport driver implements <b>HwScsiWmiSetDataBlock</b> it should change the instance of the data block to the new values from the buffer.

If all of the items in the data block are read-only, the miniport driver should return SRB_STATUS_ERROR. Otherwise, the miniport driver changes the items it can and returns SRB_STATUS_SUCCESS.

The miniport driver should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff564796">ScsiPortWmiPostProcess</a> with an appropriate <i>SrbStatus</i> value when the request is completed. If the request does not pend, <b>ScsiPortWmiPostProcess</b> should be called in the <b>HwScsiWmiSetDataBlock</b> callback. Otherwise, <b>ScsiPortWmiPostProcess</b> should be called when the request is actually completed.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565395">SCSI_WMILIB_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564766">ScsiPortWmiDispatchFunction</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564796">ScsiPortWmiPostProcess</a>
 

 

