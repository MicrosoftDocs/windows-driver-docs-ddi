---
UID: NC:scsiwmi.PSCSIWMI_SET_DATABLOCK
title: PSCSIWMI_SET_DATABLOCK
author: windows-driver-content
description: A miniport driver's HwScsiWmiSetDataBlock routine is called to change all data items in a single instance of a data block.
old-location: storage\hwscsiwmisetdatablock.htm
old-project: storage
ms.assetid: 5523d4d6-8eb5-48eb-a652-6612101b8422
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storage.hwscsiwmisetdatablock, HwScsiWmiSetDataBlock, HwScsiWmiSetDataBlock callback function [Storage Devices], HwScsiWmiSetDataBlock, PSCSIWMI_SET_DATABLOCK, PSCSIWMI_SET_DATABLOCK, scsiwmi/HwScsiWmiSetDataBlock, Scsimini_b75fb6d1-48dc-4fcb-ae05-bf278c382ecf.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	scsiwmi.h
apiname:
-	HwScsiWmiSetDataBlock
product: Windows
targetos: Windows
req.typenames: "*PSCSISCAN_INFO, SCSISCAN_INFO"
req.product: Windows 10 or later.
---

# PSCSIWMI_SET_DATABLOCK callback


## -description


A miniport driver's <b>HwScsiWmiSetDataBlock</b> routine is called to change all data items in a single instance of a data block. This routine is optional.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -prototype


````
BOOLEAN HwScsiWmiSetDataBlock(
  _In_ PVOID                    DeviceContext,
  _In_ PSCSIWMI_REQUEST_CONTEXT RequestContext,
  _In_ ULONG                    GuidIndex,
  _In_ ULONG                    InstanceIndex,
  _In_ ULONG                    BufferSize,
  _In_ PUCHAR                   Buffer
);
````


## -parameters




### -param DeviceContext [in]

Points to the miniport driver-defined context value passed to <a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a>. 


### -param RequestContext [in]

Points to the SCSIWMI_REQUEST_CONTEXT structure that the miniport driver passed to <a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a>. 


### -param GuidIndex [in]

Specifies the data block by its index into the list of GUIDs in the SCSI_WMILIB_CONTEXT structure that the miniport driver passed to <a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a>. 


### -param InstanceIndex [in]

If the block specified by <i>GuidIndex</i> has multiple instances, <i>InstanceIndex</i> specifies the instance.


### -param BufferSize [in]

Specifies the size in bytes of the buffer at <i>Buffer</i>.


### -param Buffer [in]

Points to a buffer that contains new values for the instance.


## -returns



<b>HwScsiWmiSetDataBlock</b> returns SRB_STATUS_PENDING if the request is pending, or a nonzero SRB status value if the request was completed.  The SRB status value returned by this routine is the same as what was passed in to <a href="..\scsiwmi\nf-scsiwmi-scsiportwmipostprocess.md">ScsiPortWmiPostProcess</a>.




## -remarks



When a miniport driver receives an SRB in which the <b>Function</b> member is set to SRB_FUNCTION_WMI, it calls <a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a> with a pointer to an initialized SCSI_WMILIB_CONTEXT structure and <i>MinorFunction</i> set to <b>Srb-&gt;WmiSubFunction</b>. The SCSI port driver calls the miniport driver's <b>HwScsiWmiSetDataBlock</b> routine if <i>MinorFunction</i> indicates a request to change an instance of a data block.

If a miniport driver does not implement a <b>HwScsiWmiSetDataBlock</b> routine, it must set <b>SetWmiDataBlock</b> to <b>NULL</b> in the SCSI_WMILIB_CONTEXT the miniport driver passes to <a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a>. In this case, the port driver returns SRB_STATUS_ERROR to the caller.

If the miniport driver implements <b>HwScsiWmiSetDataBlock</b> it should change the instance of the data block to the new values from the buffer.

If all of the items in the data block are read-only, the miniport driver should return SRB_STATUS_ERROR. Otherwise, the miniport driver changes the items it can and returns SRB_STATUS_SUCCESS.

The miniport driver should call <a href="..\scsiwmi\nf-scsiwmi-scsiportwmipostprocess.md">ScsiPortWmiPostProcess</a> with an appropriate <i>SrbStatus</i> value when the request is completed. If the request does not pend, <b>ScsiPortWmiPostProcess</b> should be called in the <b>HwScsiWmiSetDataBlock</b> callback. Otherwise, <b>ScsiPortWmiPostProcess</b> should be called when the request is actually completed.




## -see-also

<a href="..\scsiwmi\nf-scsiwmi-scsiportwmipostprocess.md">ScsiPortWmiPostProcess</a>



<a href="..\scsiwmi\ns-scsiwmi-_scsiwmilib_context.md">SCSI_WMILIB_CONTEXT</a>



<a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20PSCSIWMI_SET_DATABLOCK callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

