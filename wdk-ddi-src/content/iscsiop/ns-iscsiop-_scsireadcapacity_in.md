---
UID: NS:iscsiop._ScsiReadCapacity_IN
title: _ScsiReadCapacity_IN (iscsiop.h)
description: The ScsiReadCapacity_IN structure holds the input data for the ScsiReadCapacity method, which is used to send a SCSI read Ccapacity command.
old-location: storage\scsireadcapacity_in.htm
tech.root: storage
ms.assetid: 7a9d6f43-88f7-490e-9446-e707b6497a38
ms.date: 03/29/2018
ms.keywords: "*PScsiReadCapacity_IN, PScsiReadCapacity_IN, PScsiReadCapacity_IN structure pointer [Storage Devices], ScsiReadCapacity_IN, ScsiReadCapacity_IN structure [Storage Devices], _ScsiReadCapacity_IN, iscsiop/PScsiReadCapacity_IN, iscsiop/ScsiReadCapacity_IN, storage.scsireadcapacity_in, structs-iSCSI_6363c086-0475-4bd2-bc15-5e49091e710b.xml"
f1_keywords:
 - "iscsiop/ScsiReadCapacity_IN"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- iscsiop.h
api_name:
- ScsiReadCapacity_IN
product:
- Windows
targetos: Windows
req.typenames: ScsiReadCapacity_IN, *PScsiReadCapacity_IN
---

# _ScsiReadCapacity_IN structure


## -description


The ScsiReadCapacity_IN structure holds the input data for the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/scsireadcapacity6">ScsiReadCapacity</a> method, which is used to send a SCSI read Ccapacity command.


## -struct-fields




### -field UniqueSessionId

A 64-bit integer that uniquely identifies the session. The <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/logintotarget">LoginToTarget</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/addconnectiontosession">AddConnectionToSession</a> methods both return this value in the <i>UniqueSessionId</i> parameter. Do not confuse this value with the values in the ISID and TSID members.


### -field Lun

A 64-bit number that, together with the name of the target, uniquely identifies the logical unit.


## -remarks



You must implement this method.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/addconnectiontosession">AddConnectionToSession</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/logintotarget">LoginToTarget</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/scsireadcapacity6">ScsiReadCapacity</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsiop/ns-iscsiop-_scsireadcapacity_out">ScsiReadCapacity_OUT</a>
 

 

