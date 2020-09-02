---
UID: NS:wdm._PCW_CALLBACK_INFORMATION
title: _PCW_CALLBACK_INFORMATION (wdm.h)
description: The PCW_CALLBACK_INFORMATION union supplies details about the notification to send. A provider passes a pointer to this union as a parameter to the PcwCallback function.
old-location: devtest\pcw_callback_information.htm
tech.root: devtest
ms.assetid: cc1882a9-eba7-494c-9047-5c97b1e3c19b
ms.date: 07/28/2020
keywords: ["PCW_CALLBACK_INFORMATION structure"]
ms.keywords: "*PPCW_CALLBACK_INFORMATION, PCW_CALLBACK_INFORMATION, PCW_CALLBACK_INFORMATION union [Driver Development Tools], PPCW_CALLBACK_INFORMATION, PPCW_CALLBACK_INFORMATION union pointer [Driver Development Tools], _PCW_CALLBACK_INFORMATION, devtest.pcw_callback_information, km_pcw_d44ee92a-c8a0-4da9-8739-cf5443ee2d85.xml, wdm/PCW_CALLBACK_INFORMATION, wdm/PPCW_CALLBACK_INFORMATION"
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
targetos: Windows
req.typenames: PCW_CALLBACK_INFORMATION, *PPCW_CALLBACK_INFORMATION
f1_keywords:
 - _PCW_CALLBACK_INFORMATION
 - wdm/_PCW_CALLBACK_INFORMATION
 - PPCW_CALLBACK_INFORMATION
 - wdm/PPCW_CALLBACK_INFORMATION
 - PCW_CALLBACK_INFORMATION
 - wdm/PCW_CALLBACK_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - PCW_CALLBACK_INFORMATION
---

# PCW_CALLBACK_INFORMATION structure


## -description

The `PCW_CALLBACK_INFORMATION` union contains details for a notification sent by the system to a provider-defined [PCW_CALLBACK](nc-wdm-pcw_callback.md) function. The system passes a pointer to this union in the `Info` parameter of the callback. The active field of the union is determined by the value of the `Type` parameter of the callback.

## -struct-fields

### -field AddCounter

A [PCW_COUNTER_INFORMATION](ns-wdm-_pcw_counter_information.md) structure that contains details for a `PcwCallbackAddCounter` notification.

### -field RemoveCounter

A [PCW_COUNTER_INFORMATION](ns-wdm-_pcw_counter_information.md) structure that contains details for a `PcwCallbackRemoveCounter` notification.

### -field EnumerateInstances

A [PCW_MASK_INFORMATION](ns-wdm-_pcw_mask_information.md) structure that contains details for a `PcwCallbackEnumerateInstances` notification.

### -field CollectData

A [PCW_MASK_INFORMATION](ns-wdm-_pcw_mask_information.md) structure that contains details for a `PcwCallbackCollectData` notification.

## -see-also

[PCW_CALLBACK callback function](nc-wdm-pcw_callback.md)

[_PCW_COUNTER_INFORMATION structure](ns-wdm-_pcw_counter_information.md)

[_PCW_MASK_INFORMATION structure](ns-wdm-_pcw_mask_information.md)

