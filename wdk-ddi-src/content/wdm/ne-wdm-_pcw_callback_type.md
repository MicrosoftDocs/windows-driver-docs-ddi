---
UID: NE:wdm._PCW_CALLBACK_TYPE
title: _PCW_CALLBACK_TYPE (wdm.h)
description: The PCW_CALLBACK_TYPE enumeration defines the notification type to send to the registered provider of the counterset. A provider passes a pointer to this enumeration as a parameter to the PcwCallback function.
old-location: devtest\pcw_callback_type.htm
tech.root: devtest
ms.assetid: 92f7a980-509a-44af-b480-fa8c212f4ac6
ms.date: 07/28/2020
keywords: ["PCW_CALLBACK_TYPE enumeration"]
ms.keywords: "*PPCW_CALLBACK_TYPE, PCW_CALLBACK_TYPE, PCW_CALLBACK_TYPE enumeration [Driver Development Tools], PPCW_CALLBACK_TYPE, PPCW_CALLBACK_TYPE enumeration pointer [Driver Development Tools], PcwCallbackAddCounter, PcwCallbackCollectData, PcwCallbackEnumerateInstances, PcwCallbackRemoveCounter, _PCW_CALLBACK_TYPE, devtest.pcw_callback_type, km_pcw_39199484-e1fb-4d3b-9bab-27d8d880a9bf.xml, wdm/PCW_CALLBACK_TYPE, wdm/PPCW_CALLBACK_TYPE, wdm/PcwCallbackAddCounter, wdm/PcwCallbackCollectData, wdm/PcwCallbackEnumerateInstances, wdm/PcwCallbackRemoveCounter"
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
req.typenames: PCW_CALLBACK_TYPE, *PPCW_CALLBACK_TYPE
f1_keywords:
 - _PCW_CALLBACK_TYPE
 - wdm/_PCW_CALLBACK_TYPE
 - PPCW_CALLBACK_TYPE
 - wdm/PPCW_CALLBACK_TYPE
 - PCW_CALLBACK_TYPE
 - wdm/PCW_CALLBACK_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - PCW_CALLBACK_TYPE
---

# PCW_CALLBACK_TYPE enumeration


## -description

The `PCW_CALLBACK_TYPE` enumeration defines the type of the notification sent by the system to the provider-defined [PCW_CALLBACK](nc-wdm-pcw_callback.md) function. The system passes a value of this enumeration in the `Type` parameter of the callback.

## -enum-fields

### -field PcwCallbackAddCounter

The system invokes the provider's callback with this `Type` value to notify the provider that a consumer has added an instance filter to a query involving this counterset.

Most providers will ignore notifications with this `Type`, but some might use this notification to optimize their data collection. For example, a provider might `InterlockedIncrement` a global counter for each AddCounter notification and only track performance data when the global counter is non-zero.

### -field PcwCallbackRemoveCounter

The system invokes the provider's callback with this `Type` value to notify the provider that a consumer has removed an instance filter from a query involving this counterset.

Most providers will ignore notifications with this `Type`, but some might use this notification to optimize their data collection. For example, a provider might `InterlockedDecrement` a global counter for each RemoveCounter notification and only track performance data when the global counter is non-zero.

### -field PcwCallbackEnumerateInstances

The system invokes the provider's callback with this `Type` value to request the provider to provide the Name and Id values for the instances of the counterset.

Most providers will use the same implementation for PcwCallbackEnumerateInstances and PcwCallbackCollectData notifications, but some might optimize data collection by skipping collection of counter data values when responding to a PcwCallbackEnumerateInstances callback.

### -field PcwCallbackCollectData

The system invokes the provider's callback with this `Type` value to request the provider to provide the Name, Id, and counter data values for the instances of the counterset.

Refer to the documentation for the [PCW_CALLBACK](nc-wdm-pcw_callback.md) function for details and examples of handling this notification.

## -see-also

[PCW_CALLBACK callback function](nc-wdm-pcw_callback.md)

