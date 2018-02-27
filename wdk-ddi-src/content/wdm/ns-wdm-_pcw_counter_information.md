---
UID: NS:wdm._PCW_COUNTER_INFORMATION
title: "_PCW_COUNTER_INFORMATION"
author: windows-driver-content
description: The PCW_COUNTER_INFORMATION structure describes attributes that identify a specific instance of a counter set.
old-location: devtest\pcw_counter_information.htm
old-project: devtest
ms.assetid: fe4d8df4-0e15-49fb-a5ec-40aa8acf3675
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PPCW_COUNTER_INFORMATION, PCW_COUNTER_INFORMATION, PCW_COUNTER_INFORMATION structure [Driver Development Tools], PPCW_COUNTER_INFORMATION, PPCW_COUNTER_INFORMATION structure pointer [Driver Development Tools], _PCW_COUNTER_INFORMATION, devtest.pcw_counter_information, km_pcw_b89088c5-c9df-4ca9-86b1-8fdb558216c5.xml, wdm/PCW_COUNTER_INFORMATION, wdm/PPCW_COUNTER_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	PCW_COUNTER_INFORMATION
product: Windows
targetos: Windows
req.typenames: PCW_COUNTER_INFORMATION, *PPCW_COUNTER_INFORMATION
req.product: Windows 10 or later.
---

# _PCW_COUNTER_INFORMATION structure


## -description


The PCW_COUNTER_INFORMATION structure describes attributes that identify a specific instance of a counter set. 


## -syntax


````
typedef struct _PCW_COUNTER_INFORMATION {
  ULONG64          CounterMask;
  PCUNICODE_STRING InstanceMask;
} PCW_COUNTER_INFORMATION, *PPCW_COUNTER_INFORMATION;
````


## -struct-fields




### -field CounterMask

A bitmask. If the <i>x</i>-th bit is set, counter <i>x</i>^2 is included in the query. The value assigned to identify the counters exposed in a registration.


### -field InstanceMask

A Unicode string that contains a wildcard specification of the instance. That is, "*" and "?" have the usual meaning of zero-or-more-characters and any-character respectively. The <b>InstanceMask</b> identifies and maps the counter set to a specific instance. 

