---
UID: NS:wdm._PCW_COUNTER_DESCRIPTOR
title: "_PCW_COUNTER_DESCRIPTOR"
description: The PCW_COUNTER_DESCRIPTOR structure supplies details about the notification to send.
old-location: devtest\pcw_counter_descriptor.htm
tech.root: devtest
ms.assetid: 0b099aec-f254-4cfb-87cb-2f8965d5faae
ms.date: 02/23/2018
ms.keywords: "*PPCW_COUNTER_DESCRIPTOR, PCW_COUNTER_DESCRIPTOR, PCW_COUNTER_DESCRIPTOR structure [Driver Development Tools], PPCW_COUNTER_DESCRIPTOR, PPCW_COUNTER_DESCRIPTOR structure pointer [Driver Development Tools], _PCW_COUNTER_DESCRIPTOR, devtest.pcw_counter_descriptor, km_pcw_8507bc5e-60f4-4b71-bb2f-d62360076e2c.xml, wdm/PCW_COUNTER_DESCRIPTOR, wdm/PPCW_COUNTER_DESCRIPTOR"
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
-	wdm.h
api_name:
-	PCW_COUNTER_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: PCW_COUNTER_DESCRIPTOR, *PPCW_COUNTER_DESCRIPTOR
---

# _PCW_COUNTER_DESCRIPTOR structure


## -description


The PCW_COUNTER_DESCRIPTOR structure supplies details about the notification to send.


## -struct-fields




### -field Id

A numeric value that specifies the <b>Id</b> (identifier) associated with the instance of the counter set.


### -field StructIndex

A numeric value that specifies the index into the array of structures that describe the counter set. 


### -field Offset

A numeric value that indicates the end of the instance list for the counter set. The value is used to ensure that a new instance will always be added to the end of the list. 


### -field Size

A numeric value that specifies the size, in bytes, associated with the instance of the counter set.

