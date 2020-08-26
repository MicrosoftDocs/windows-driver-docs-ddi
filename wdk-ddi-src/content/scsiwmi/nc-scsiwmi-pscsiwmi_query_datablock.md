---
UID: NC:scsiwmi.PSCSIWMI_QUERY_DATABLOCK
title: PSCSIWMI_QUERY_DATABLOCK (scsiwmi.h)
description: A miniport driver's HwScsiWmiQueryDataBlock routine is called to obtain either a single instance or all instances of a data block.
old-location: storage\hwscsiwmiquerydatablock.htm
tech.root: storage
ms.assetid: a2e588b8-50d6-4bed-b50c-c42be24955f1
ms.date: 03/29/2018
keywords: ["PSCSIWMI_QUERY_DATABLOCK callback function"]
ms.keywords: HwScsiWmiQueryDataBlock, HwScsiWmiQueryDataBlock callback function [Storage Devices], PSCSIWMI_QUERY_DATABLOCK, PSCSIWMI_QUERY_DATABLOCK callback, Scsimini_1405dcfc-840b-4cc6-bd4c-63d071aa993e.xml, scsiwmi/HwScsiWmiQueryDataBlock, storage.hwscsiwmiquerydatablock
f1_keywords:
 - "scsiwmi/HwScsiWmiQueryDataBlock"
 - "HwScsiWmiQueryDataBlock"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- scsiwmi.h
api_name:
- HwScsiWmiQueryDataBlock
targetos: Windows
req.typenames: 
---

# PSCSIWMI_QUERY_DATABLOCK callback function


## -description


A miniport driver's <b>HwScsiWmiQueryDataBlock</b> routine is called to obtain either a single instance or all instances of a data block. This routine is required.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Context 
[in]
Points to the miniport driver-defined context value passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmidispatchfunction">ScsiPortWmiDispatchFunction</a>. 


### -param DispatchContext 
[in]
Points to the SCSIWMI_REQUEST_CONTEXT structure that the miniport driver passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmidispatchfunction">ScsiPortWmiDispatchFunction</a>. 


### -param GuidIndex 
[in]
Specifies the data block by its index into the list of GUIDs in the SCSI_WMILIB_CONTEXT structure that the miniport driver passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmidispatchfunction">ScsiPortWmiDispatchFunction</a>. 


### -param InstanceIndex 
[in]
If <b>HwScsiWmiQueryDataBlock</b> is called in response to an IRP_MN_QUERY_SINGLE_INSTANCE request, <i>InstanceIndex</i> specifies the instance to be queried. If <b>HwScsiWmiQueryDataBlock</b> is called in response to an IRP_MN_QUERY_ALL_DATA REQUEST, <i>InstanceIndex</i> is zero.


### -param InstanceCount 
[in]
If <b>HwScsiWmiQueryDataBlock</b> is called in response to an IRP_MN_QUERY_SINGLE_INSTANCE request, <i>InstanceCount</i> is 1. If <b>HwScsiWmiQueryDataBlock</b> is called in response to an IRP_MN_QUERY_ALL_DATA REQUEST, <i>InstanceCount</i> is the number of instances to be returned.


### -param InstanceLengthArray 
[in, out]
Points to an array of ULONGs that indicate the length of each instance of the data block to be returned. This array has <i>InstanceCount</i> elements. This value may be <b>NULL</b> when there is not enough space in the output buffer to fulfill the request. 


### -param BufferAvail 
[in]
Specifies the maximum number of bytes available to receive data in the buffer at <i>Buffer</i>.


### -param Buffer 
[out]
Points to the buffer to receive instance data. If the buffer is large enough to receive all of the data, the miniport driver writes instance data to the buffer with each instance aligned on an 8-byte boundary. If the buffer is too small to receive all of the data, the miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmipostprocess">ScsiPortWmiPostProcess</a> with a status of SRB_STATUS_DATA_OVERRUN and sets <i>BufferUsed</i>  to the size of the output buffer needed to fulfill the request.


## -returns



<b>HwScsiWmiQueryDataBlock</b> returns SRB_STATUS_PENDING if the request is pending or a nonzero SRB status value if the request was completed.  The SRB status value returned by this routine is the same as what was passed in to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmipostprocess">ScsiPortWmiPostProcess</a>. Although the return value data type is BOOLEAN, the <b>HwScsiWmiQueryDataBlock</b> routine actually returns an SRB status value.




## -remarks



When a miniport driver receives an SRB in which the <b>Function</b> member is set to SRB_FUNCTION_WMI, it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmidispatchfunction">ScsiPortWmiDispatchFunction</a> with a pointer to an initialized SCSI_WMILIB_CONTEXT structure and <i>MinorFunction</i> set to <b>Srb->WmiSubFunction</b>. The SCSI port driver calls the miniport driver's <b>HwScsiWmiQueryDataBlock</b> routine if <i>MinorFunction</i> indicates a request to obtain a single instance or all instances of a data block.

The miniport driver writes instance data to the buffer. For requests that do not pend, the miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmipostprocess">ScsiPortWmiPostProcess</a> with an appropriate <i>SrbStatus</i> value before returning from <b>HwScsiWmiQueryDataBlock</b>. If the request pends, the miniport driver calls <b>ScsiPortWmiPostProcess</b> when the request is complete.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/ns-scsiwmi-_scsiwmilib_context">SCSI_WMILIB_CONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmidispatchfunction">ScsiPortWmiDispatchFunction</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmipostprocess">ScsiPortWmiPostProcess</a>
 

 

