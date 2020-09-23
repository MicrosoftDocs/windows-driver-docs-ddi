---
UID: NS:iscsiop._ScsiInquiry_IN
title: _ScsiInquiry_IN (iscsiop.h)
description: The ScsiInquiry_IN structure holds the input data for the ScsiInquiry method, which is used to send a SCSI inquiry command.
old-location: storage\scsiinquiry_in.htm
tech.root: storage
ms.assetid: b1a73ef7-c13a-4627-8eb0-b9285567caec
ms.date: 03/29/2018
keywords: ["ScsiInquiry_IN structure"]
ms.keywords: "*PScsiInquiry_IN, PScsiInquiry_IN, PScsiInquiry_IN structure pointer [Storage Devices], ScsiInquiry_IN, ScsiInquiry_IN structure [Storage Devices], _ScsiInquiry_IN, iscsiop/PScsiInquiry_IN, iscsiop/ScsiInquiry_IN, storage.scsiinquiry_in, structs-iSCSI_2129d82b-f03d-49f2-bf1d-8716840d086c.xml"
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
targetos: Windows
req.typenames: ScsiInquiry_IN, *PScsiInquiry_IN
f1_keywords:
 - _ScsiInquiry_IN
 - iscsiop/_ScsiInquiry_IN
 - PScsiInquiry_IN
 - iscsiop/PScsiInquiry_IN
 - ScsiInquiry_IN
 - iscsiop/ScsiInquiry_IN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsiop.h
api_name:
 - ScsiInquiry_IN
---

# _ScsiInquiry_IN structure (iscsiop.h)


## -description

The ScsiInquiry_IN structure holds the input data for the <a href="/windows-hardware/drivers/storage/scsiinquiry">ScsiInquiry</a> method, which is used to send a SCSI inquiry command.

## -struct-fields

### -field UniqueSessionId

A 64-bit integer that uniquely identifies the session. The <a href="/windows-hardware/drivers/storage/logintotarget">LoginToTarget</a> and <a href="/windows-hardware/drivers/storage/addconnectiontosession">AddConnectionToSession</a> methods both return this value in the <i>UniqueSessionId</i> parameter. Do not confuse this value with the values in the ISID and TSID members.

### -field Lun

A 64-bit number that, together with the name of the target, uniquely identifies the logical unit.

### -field InquiryFlags

The inquiry flags to set in the SCSI inquiry command. A value of 1 in the lowest order bit (0x01) indicates that the enable vital product data (EVPD) bit will be set in the inquiry command and the device server will return the optional vital product data that the page code field specifies in the inquiry command. A value of 1 in the second bit (0x02) indicates that the command support data bit will be set in the inquiry command and the device server will return the optional command support data that the operation code field specifies in the inquiry command.

### -field PageCode

The page code field in the SCSI inquiry command.

## -remarks

You must implement this method.

## -see-also

<a href="/windows-hardware/drivers/storage/addconnectiontosession">AddConnectionToSession</a>



<a href="/windows-hardware/drivers/storage/logintotarget">LoginToTarget</a>



<a href="/windows-hardware/drivers/storage/scsiinquiry">ScsiInquiry</a>



<a href="/windows-hardware/drivers/ddi/iscsiop/ns-iscsiop-_scsiinquiry_out">ScsiInquiry_OUT</a>