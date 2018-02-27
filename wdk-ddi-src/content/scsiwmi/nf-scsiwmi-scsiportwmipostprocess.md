---
UID: NF:scsiwmi.ScsiPortWmiPostProcess
title: ScsiPortWmiPostProcess function
author: windows-driver-content
description: The ScsiPortWmiPostProcess routine updates a request context for a WMI SRB.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportwmipostprocess.htm
old-project: storage
ms.assetid: da1770bc-2233-47ef-afab-cfcb34edb4b9
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ScsiPortWmiPostProcess, ScsiPortWmiPostProcess routine [Storage Devices], scsiprt_e10d02e1-18d2-4152-ac11-83bdcbb2ce49.xml, scsiwmi/ScsiPortWmiPostProcess, storage.scsiportwmipostprocess
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: scsiwmi.h
req.include-header: Miniport.h, Scsi.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	scsiwmi.h
apiname:
-	ScsiPortWmiPostProcess
product: Windows
targetos: Windows
req.typenames: SCSIWMI_ENABLE_DISABLE_CONTROL
req.product: Windows 10 or later.
---

# ScsiPortWmiPostProcess function


## -description


The <b>ScsiPortWmiPostProcess</b> routine updates a request context for a WMI SRB.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
VOID ScsiPortWmiPostProcess(
  _In_ PSCSIWMI_REQUEST_CONTEXT RequestContext,
  _In_ UCHAR                    SrbStatus,
  _In_ ULONG                    BufferUsed
);
````


## -parameters




### -param RequestContext [in]

A pointer to the request context for this SRB.


### -param SrbStatus [in]

Specifies any valid SRB status. If the output buffer passed to the miniport driver was too small to contain all of the data from a request, the miniport driver sets <i>SrbStatus</i> to SRB_STATUS_DATA_OVERRUN.


### -param BufferUsed [in]

If <i>SrbStatus</i> indicates success, the miniport driver sets <i>BufferUsed</i> to the number of bytes of data written to the buffer. If <i>SrbStatus</i> is SRB_STATUS_DATA_OVERRUN, the miniport driver sets <i>BufferUsed</i> to the number of bytes required to complete the SRB successfully.


## -returns



None




## -remarks



A miniport driver must call <b>ScsiPortWmiPostProcess</b> after the WMI SRB request has been processed and is ready to be completed.

For synchronous SRBs, <b>ScsiPortWmiPostProcess</b> is called in the callback routine.

For pending SRBs, <b>ScsiPortWmiPostProcess</b> is called after the SRB has been processed, and before it is completed.

If a miniport driver sets <i>SrbStatus</i> to SRB_STATUS_DATA_OVERRUN and sets <i>BufferUsed</i>, successive identical WMI SRBs with an allocated buffer equal to or greater than <i>BufferUsed</i> bytes should succeed. This should be achieved if the driver sets the exact value for <i>BufferUsed</i> that is needed to complete the request when calling <b>ScsiPortWmiPostProcess</b> with <i>SrbStatus</i> equal to SRB_STATUS_DATA_OVERRUN. For a variable-sized output structure, the input data buffer of the SRB should have enough information to determine the exact <i>BufferUsed</i> value. If the input data buffer does not contain enough information, the driver should never fail the same SRB two times with SRB_STATUS_DATA_OVERRUN. Instead, the driver should set SRB_STATUS_DATA_OVERRUN and request the minimum size necessary for the output buffer first, and then set SRB_STATUS_SUCCESS and indicate the failure in the contents of the output buffer.




## -see-also

<a href="..\scsiwmi\nf-scsiwmi-scsiportwmigetreturnsize.md">ScsiPortWmiGetReturnSize</a>



<a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a>



<a href="..\scsiwmi\nf-scsiwmi-scsiportwmigetreturnstatus.md">ScsiPortWmiGetReturnStatus</a>



<a href="..\scsiwmi\ns-scsiwmi-scsiwmi_request_context.md">SCSIWMI_REQUEST_CONTEXT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiPortWmiPostProcess routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

