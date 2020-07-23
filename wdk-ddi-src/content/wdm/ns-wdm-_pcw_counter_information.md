---
UID: NS:wdm._PCW_COUNTER_INFORMATION
title: _PCW_COUNTER_INFORMATION (wdm.h)
description: The PCW_COUNTER_INFORMATION structure describes attributes that identify a specific instance of a counter set.
old-location: devtest\pcw_counter_information.htm
tech.root: devtest
ms.assetid: fe4d8df4-0e15-49fb-a5ec-40aa8acf3675
ms.date: 02/23/2018
keywords: ["_PCW_COUNTER_INFORMATION structure"]
ms.keywords: "*PPCW_COUNTER_INFORMATION, PCW_COUNTER_INFORMATION, PCW_COUNTER_INFORMATION structure [Driver Development Tools], PPCW_COUNTER_INFORMATION, PPCW_COUNTER_INFORMATION structure pointer [Driver Development Tools], _PCW_COUNTER_INFORMATION, devtest.pcw_counter_information, km_pcw_b89088c5-c9df-4ca9-86b1-8fdb558216c5.xml, wdm/PCW_COUNTER_INFORMATION, wdm/PPCW_COUNTER_INFORMATION"
f1_keywords:
 - "wdm/PCW_COUNTER_INFORMATION"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdm.h
api_name:
- PCW_COUNTER_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: PCW_COUNTER_INFORMATION, *PPCW_COUNTER_INFORMATION
---

# _PCW_COUNTER_INFORMATION structure

## -description

The `PCW_COUNTER_INFORMATION` structure is a member of the [PCW_CALLBACK_INFORMATION](ns-wdm-_pcw_callback_information.md) union, which contains details of a notification sent by the system to a provider-defined [PCW_CALLBACK](nc-wdm-pcw_callback.md) function.

## -struct-fields

### -field CounterMask

A bitmask. If the `x`-th bit is set, counter with id `x` is included in the query.

### -field InstanceMask

A Unicode string that contains a wildcard specification of instance names to be matched in the query. If all instance names should match the query, the `InstanceMask` field will be `"*"`. Otherwise, `"*"` and `"?"` have the usual wildcard meaning of zero-or-more-characters and any-character respectively. Note that instance name matching is not case-sensitive.

## -see-also

[PCW_CALLBACK callback function](nc-wdm-pcw_callback.md)

[_PCW_CALLBACK_INFORMATION structure](ns-wdm-_pcw_callback_information.md)
