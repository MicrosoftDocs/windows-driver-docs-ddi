---
UID: NS:iscsiop._ScsiInquiry_OUT
title: "_ScsiInquiry_OUT"
description: The ScsiInquiry_OUT structure holds the output data for the ScsiInquiry method.
old-location: storage\scsiinquiry_out.htm
tech.root: storage
ms.assetid: ac3ec079-61a5-42fe-a1c0-b7626e5f32d2
ms.date: 03/29/2018
ms.keywords: "*PScsiInquiry_OUT, PScsiInquiry_OUT, PScsiInquiry_OUT structure pointer [Storage Devices], ScsiInquiry_OUT, ScsiInquiry_OUT structure [Storage Devices], _ScsiInquiry_OUT, iscsiop/PScsiInquiry_OUT, iscsiop/ScsiInquiry_OUT, storage.scsiinquiry_out, structs-iSCSI_0c90b572-8a05-4a75-86ce-5b12d82a1c2f.xml"
ms.topic: struct
req.header: iscsiop.h
req.include-header: Iscsiop.h
req.target-type: Windows
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
-	HeaderDef
api_location:
-	iscsiop.h
api_name:
-	ScsiInquiry_OUT
product:
- Windows
targetos: Windows
req.typenames: ScsiInquiry_OUT, *PScsiInquiry_OUT
---

# _ScsiInquiry_OUT structure


## -description


The ScsiInquiry_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564585">ScsiInquiry</a> method.


## -struct-fields




### -field Status

The status of the <b>ScsiInquiry</b> operation. This member will contain 0 if the INQUIRY operation succeeds and ISDSC_SCSI_REQUEST_FAILED if the operation fails. If the INQUIRY operation fails, <b>ScsiStatus</b> will contain the SCSI status of the SCSI command. SCSI status qualifiers are documented in the <i>SCSI Primary Commands</i> specification. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>.


### -field ResponseBufferSize

The response buffer size, in bytes<i>.</i>


### -field ScsiStatus

The status of the SCSI INQUIRY command.


### -field SenseBuffer

A buffer that holds the SCSI sense data that the SCSI INQUIRY command received.


### -field ResponseBuffer

A buffer that holds the response data that the SCSI INQUIRY command received. 


## -remarks



You must implement this method.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564585">ScsiInquiry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564598">ScsiInquiry_IN</a>
 

 

