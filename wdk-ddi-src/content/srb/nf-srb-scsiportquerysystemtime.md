---
UID: NF:srb.ScsiPortQuerySystemTime
title: ScsiPortQuerySystemTime function (srb.h)
description: The ScsiPortQuerySystemTime routine obtains the current system time.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportquerysystemtime.htm
tech.root: storage
ms.assetid: 6f6afe6d-8f57-4c08-97ea-b327622a4e39
ms.date: 03/29/2018
keywords: ["ScsiPortQuerySystemTime function"]
ms.keywords: ScsiPortQuerySystemTime, ScsiPortQuerySystemTime routine [Storage Devices], scsiprt_033d0cc3-e930-448b-a13e-b140829d2b7d.xml, srb/ScsiPortQuerySystemTime, storage.scsiportquerysystemtime
f1_keywords:
 - "srb/ScsiPortQuerySystemTime"
req.header: srb.h
req.include-header: 
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
req.lib: Scsiport.lib
req.dll: 
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Scsiport.lib
- Scsiport.dll
api_name:
- ScsiPortQuerySystemTime
product:
- Windows
targetos: Windows
req.typenames: 
---

# ScsiPortQuerySystemTime function


## -description


The <b>ScsiPortQuerySystemTime</b> routine obtains the current system time.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param CurrentTime [out]

Pointer to the current time, on return. 


## -returns



None 




## -remarks



The system time returned in <i>CurrentTime</i> is the number of 100-nanosecond intervals that have elapsed since January 1, 1601. System time is typically updated approximately every ten milliseconds. This value is computed for the GMT time zone. 



