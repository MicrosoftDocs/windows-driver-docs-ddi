---
UID: NS:wdm._PCW_MASK_INFORMATION
title: _PCW_MASK_INFORMATION (wdm.h)
description: The PCW_MASK_INFORMATION structure supplies details about the notification to send to the provider. This information is passed as part of the Info parameter to the PcwCallback function. This mask information is included in PCW_CALLBACK_INFORMATION.
old-location: devtest\pcw_mask_information.htm
tech.root: devtest
ms.assetid: 5519aec9-9a02-4571-8809-fa8273269ea5
ms.date: 07/28/2020
keywords: ["_PCW_MASK_INFORMATION structure"]
ms.keywords: "*PPCW_MASK_INFORMATION, PCW_MASK_INFORMATION, PCW_MASK_INFORMATION structure [Driver Development Tools], PPCW_MASK_INFORMATION, PPCW_MASK_INFORMATION structure pointer [Driver Development Tools], _PCW_MASK_INFORMATION, devtest.pcw_mask_information, km_pcw_44887cd4-4c18-4c6e-9168-5e89f37e970a.xml, wdm/PCW_MASK_INFORMATION, wdm/PPCW_MASK_INFORMATION"
f1_keywords:
 - "wdm/PCW_MASK_INFORMATION"
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
- PCW_MASK_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: PCW_MASK_INFORMATION, *PPCW_MASK_INFORMATION
---

# _PCW_MASK_INFORMATION structure

## -description

The `PCW_MASK_INFORMATION` structure is the type of the `EnumerateInstances` and `CollectData` members of the [_PCW_CALLBACK_INFORMATION](ns-wdm-_pcw_callback_information.md) union. It contains details of a notification sent by the system to a provider-defined [PCW_CALLBACK](nc-wdm-pcw_callback.md) function.

## -struct-fields

### -field CounterMask

A bitmask. If the `x`-th bit is set, the counter with ID `x` is included in the query.

### -field InstanceMask

A Unicode string that contains a wildcard specification of instance names to be matched in the query. If all instance names should match the query, the `InstanceMask` field will be `"*"`. Otherwise, `"*"` and `"?"` have the usual wildcard meaning of "zero-or-more-characters" and "any-character" respectively. Note that instance name matching is not case-sensitive.

### -field InstanceId

The numeric value that identifies the ID of the instance(s) to be collected. If the value is `PCW_ANY_INSTANCE_ID` (0xFFFFFFFF), all instance IDs should match the query.

### -field CollectMultiple

The BOOLEAN value that indicates whether the consumer will accept more than one instance in the results of the query. This will be FALSE if the counterset is being treated as a single-instance counterset. This will be TRUE if the counterset is being treated as a multi-instance counterset.

This value can be used to optimize data collection. If `CollectMultiple` is false then the data collection callback can return after adding one instance since additional instances will be ignored by the consumer.

### -field Buffer

A handle to the system-managed buffer to which the instance(s) of the counter set will be added. This handle should be used when calling `PcwAddInstance` (or when calling the CTRPP-generated Add\*\*\* function, which wraps the call to `PcwAddInstance`).

### -field CancelEvent

If this field is non-NULL, it is an initialized event object that will be signaled if the request is canceled.

## -see-also

[PCW_CALLBACK callback function](nc-wdm-pcw_callback.md)

[_PCW_CALLBACK_INFORMATION structure](ns-wdm-_pcw_callback_information.md)
