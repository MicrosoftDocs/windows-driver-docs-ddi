---
UID: NS:iscsiop._ScsiReportLuns_OUT
title: "_ScsiReportLuns_OUT"
author: windows-driver-content
description: The ScsiReportLuns_OUT structure holds the output data for the ScsiReportLuns method.
old-location: storage\scsireportluns_out.htm
tech.root: storage
ms.assetid: 6335705d-a900-456a-a882-f7f11bb485af
ms.date: 03/29/2018
ms.keywords: "*PScsiReportLuns_OUT, PScsiReportLuns_OUT, PScsiReportLuns_OUT structure pointer [Storage Devices], ScsiReportLuns_OUT, ScsiReportLuns_OUT structure [Storage Devices], _ScsiReportLuns_OUT, iscsiop/PScsiReportLuns_OUT, iscsiop/ScsiReportLuns_OUT, storage.scsireportluns_out, structs-iSCSI_8f759a2a-f588-48c7-a777-1a0a7eb6604b.xml"
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
-	ScsiReportLuns_OUT
product:
- Windows
targetos: Windows
req.typenames: ScsiReportLuns_OUT, *PScsiReportLuns_OUT
---

# _ScsiReportLuns_OUT structure


## -description


The ScsiReportLuns_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564918">ScsiReportLuns</a> method.


## -struct-fields




### -field Status

The status of the <b>ScsiReportLuns</b> method. This member will contain 0 if the REPORT LUNS operation succeeds and ISDSC_SCSI_REQUEST_FAILED if the operation fails. If the REPORT LUNS operation fails, <b>ScsiStatus</b> will contain the SCSI status of the SCSI command. SCSI status qualifiers are documented in the <i>SCSI Primary Commands</i> specification. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>.  


### -field ResponseBufferSize

The size, in bytes, of the buffer at <b>ResponseBuffer</b><i>.</i>


### -field ScsiStatus

The status of the SCSI REPORT LUNS command. 


### -field SenseBuffer

A buffer that holds the SCSI sense data that the SCSI REPORT LUNS command received. 


### -field ResponseBuffer

A buffer that holds the response data that the SCSI REPORT LUNS command received. 


## -remarks



You must implement this method.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564918">ScsiReportLuns</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564925">ScsiReportLuns_IN</a>
 

 

