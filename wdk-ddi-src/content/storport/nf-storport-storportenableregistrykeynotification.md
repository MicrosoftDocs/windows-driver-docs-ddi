---
UID: NF:storport.StorPortEnableRegistryKeyNotification
tech.root: storage
title: StorPortEnableRegistryKeyNotification
ms.date: 05/24/2022
targetos: Windows
description: Learn more about the StorPortEnableRegistryKeyNotification function.
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
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortEnableRegistryKeyNotification
f1_keywords:
 - StorPortEnableRegistryKeyNotification
 - storport/StorPortEnableRegistryKeyNotification
dev_langs:
 - c++
helpviewer_keywords:
 - StorPortEnableRegistryKeyNotification
---

## -description

A miniport calls **StorPortEnableRegistryKeyNotification** to enable registry change notifications for a device under the path HKLM\System\CurrentControlSet\Services\<*serviceName*>\Parameters\Device.

## -parameters

### -param HwDeviceExtension

[in] Pointer to the hardware device extension for the host bus adapter (HBA).

### -param NotificationCallback

[in] Pointer to the miniport's [**HW_REGISTRY_NOTIFICATION_ROUTINE**](nc-storport-hw_registry_notification_routine.md) callback routine.

## -returns

**StorPortEnableRegistryKeyNotification** returns STOR_STATUS_SUCCESS if the node affinity was queried successfully. Possible error return values include the following.

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_INSUFFICIENT_RESOURCES | There was not enough memory to complete the operation. |
| STOR_STATUS_INVALID_PARAMETER      | There is an invalid parameter, such as a null **NotificationCallback** pointer. |
| STOR_STATUS_UNSUCCESSFUL           | An error occurred for internal reasons. |

## -remarks

 When a change occurs under the HKLM\System\CurrentControlSet\Services\<*serviceName*>\Parameters\Device registry key, Storport will call the miniport's [**HW_REGISTRY_NOTIFICATION_ROUTINE**](nc-storport-hw_registry_notification_routine.md) callback routine with the device extension.

## -see-also

[**HW_REGISTRY_NOTIFICATION_ROUTINE**](nc-storport-hw_registry_notification_routine.md)
