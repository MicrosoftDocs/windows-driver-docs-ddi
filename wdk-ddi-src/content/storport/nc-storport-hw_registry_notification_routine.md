---
UID: NC:storport.HW_REGISTRY_NOTIFICATION_ROUTINE
tech.root: storage
title: HW_REGISTRY_NOTIFICATION_ROUTINE
ms.date: 05/24/2022
targetos: Windows
description: Learn more about the HW_REGISTRY_NOTIFICATION_ROUTINE callback.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: WIN11_NEXT
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - storport.h
api_name:
 - HW_REGISTRY_NOTIFICATION_ROUTINE
f1_keywords:
 - HW_REGISTRY_NOTIFICATION_ROUTINE
 - storport/HW_REGISTRY_NOTIFICATION_ROUTINE
dev_langs:
 - c++
helpviewer_keywords:
 - HW_REGISTRY_NOTIFICATION_ROUTINE
---

## -description

Storport calls a miniport's **HW_REGISTRY_NOTIFICATION_ROUTINE** callback when a change occurs under the HKLM\System\CurrentControlSet\Services\<*serviceName*>\Parameters\Device registry key.

## -parameters

### -param HwDeviceExtension

[in] Pointer to the hardware device extension for the host bus adapter (HBA). The miniport provided this value to Storport in a prior call to [**StorPortEnableRegistryKeyNotification**](nf-storport-storportenableregistrykeynotification.md).

## -remarks

If a miniport has [enabled registry change notification](nf-storport-storportenableregistrykeynotification.md), Storport will call the miniport's **HW_REGISTRY_NOTIFICATION_ROUTINE** callback routine with the device extension when a change occurs under the HKLM\System\CurrentControlSet\Services\<*serviceName*>\Parameters\Device registry key.

**HW_REGISTRY_NOTIFICATION_ROUTINE** should call [**StorPortRegistryRead**](nf-storport-storportregistryread.md) for each value name, setting the **Global** parameter as 1.

## -see-also

[**StorPortEnableRegistryKeyNotification**](nf-storport-storportenableregistrykeynotification.md)

[**StorPortRegistryRead**](nf-storport-storportregistryread.md)
