---
UID: NS:wdm._PCW_MASK_INFORMATION
title: "_PCW_MASK_INFORMATION" (wdm.h)
description: The PCW_MASK_INFORMATION structure supplies details about the notification to send to the provider. This information is passed as part of the Info parameter to the PcwCallback function. This mask information is included in PCW_CALLBACK_INFORMATION.
old-location: devtest\pcw_mask_information.htm
tech.root: devtest
ms.assetid: 5519aec9-9a02-4571-8809-fa8273269ea5
ms.date: 02/23/2018
ms.keywords: "*PPCW_MASK_INFORMATION, PCW_MASK_INFORMATION, PCW_MASK_INFORMATION structure [Driver Development Tools], PPCW_MASK_INFORMATION, PPCW_MASK_INFORMATION structure pointer [Driver Development Tools], _PCW_MASK_INFORMATION, devtest.pcw_mask_information, km_pcw_44887cd4-4c18-4c6e-9168-5e89f37e970a.xml, wdm/PCW_MASK_INFORMATION, wdm/PPCW_MASK_INFORMATION"
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
-	PCW_MASK_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: PCW_MASK_INFORMATION, *PPCW_MASK_INFORMATION
---

# _PCW_MASK_INFORMATION structure


## -description


The PCW_MASK_INFORMATION structure supplies details about the notification to send to the provider. This information is passed as part of the <i>Info</i> parameter to the <a href="https://msdn.microsoft.com/5058fc17-1016-45bc-a6ea-5e2458824e7b">PcwCallback</a> function. This mask information is included in PCW_CALLBACK_INFORMATION.


## -struct-fields




### -field CounterMask

A bitmask. If the <i>x</i>-th bit is set, counter <i>x</i>^2 is included in the query. The <b>CounterMask</b> is assigned to identify the counters that are exposed in a registration.


### -field InstanceMask

A Unicode string that contains a wildcard specification of the instance. That is, "*" and "?" have the usual meaning of zero-or-more-characters and any-character respectively. The <b>InstanceMask</b> identifies the name of the instance (or wildcard) that is used to filter the instances that will be collected.


### -field InstanceId

The numeric value that identifies the instance(s) to be collected. If the value is PCW_ANY_INSTANCE_ID, no specific instance identifier is required.


### -field CollectMultiple

The BOOLEAN value that indicates whether multiple instances should be collected or just one. 


### -field Buffer

A pointer to the consumer buffer to which the instance of the counter set will be added. Depending on the purpose of the buffer, the function either adds an instance or collects data.


### -field CancelEvent

A pointer to an initialized event object that indicates whether the request (either to collect data or enumerate instances) was canceled. 

