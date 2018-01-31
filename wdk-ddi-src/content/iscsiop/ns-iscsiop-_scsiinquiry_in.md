---
UID: NS:iscsiop._ScsiInquiry_IN
title: "_ScsiInquiry_IN"
author: windows-driver-content
description: The ScsiInquiry_IN structure holds the input data for the ScsiInquiry method, which is used to send a SCSI inquiry command.
old-location: storage\scsiinquiry_in.htm
old-project: storage
ms.assetid: b1a73ef7-c13a-4627-8eb0-b9285567caec
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.scsiinquiry_in, _ScsiInquiry_IN, structs-iSCSI_2129d82b-f03d-49f2-bf1d-8716840d086c.xml, iscsiop/PScsiInquiry_IN, *PScsiInquiry_IN, ScsiInquiry_IN, ScsiInquiry_IN structure [Storage Devices], PScsiInquiry_IN structure pointer [Storage Devices], PScsiInquiry_IN, iscsiop/ScsiInquiry_IN
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	iscsiop.h
apiname:
-	ScsiInquiry_IN
product: Windows
targetos: Windows
req.typenames: ScsiInquiry_IN, *PScsiInquiry_IN
---

# _ScsiInquiry_IN structure


## -description


The ScsiInquiry_IN structure holds the input data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564585">ScsiInquiry</a> method, which is used to send a SCSI inquiry command.


## -syntax


````
typedef struct _ScsiInquiry_IN {
  ULONGLONG UniqueSessionId;
  ULONGLONG Lun;
  UCHAR     InquiryFlags;
  UCHAR     PageCode;
} ScsiInquiry_IN, *PScsiInquiry_IN;
````


## -struct-fields




#### - UniqueSessionId

A 64-bit integer that uniquely identifies the session. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a> methods both return this value in the <i>UniqueSessionId</i> parameter. Do not confuse this value with the values in the ISID and TSID members.


#### - Lun

A 64-bit number that, together with the name of the target, uniquely identifies the logical unit.


#### - InquiryFlags

The inquiry flags to set in the SCSI inquiry command. A value of 1 in the lowest order bit (0x01) indicates that the enable vital product data (EVPD) bit will be set in the inquiry command and the device server will return the optional vital product data that the page code field specifies in the inquiry command. A value of 1 in the second bit (0x02) indicates that the command support data bit will be set in the inquiry command and the device server will return the optional command support data that the operation code field specifies in the inquiry command.


#### - PageCode

The page code field in the SCSI inquiry command.


## -remarks


You must implement this method.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564585">ScsiInquiry</a>

<a href="..\hbapiwmi\ns-hbapiwmi-_scsiinquiry_out.md">ScsiInquiry_OUT</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiInquiry_IN structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

