---
UID: NE:dot11wificxtypes._WDI_IHV_TASK_PRIORITY
tech.root: netvista
title: WDI_IHV_TASK_PRIORITY (dot11wificxtypes.h)
ms.date: 09/15/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_IHV_TASK_PRIORITY enum defines IHV task priorities.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dot11wificxtypes.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dot11wificxtypes.h
api_name:
 - _WDI_IHV_TASK_PRIORITY
 - WDI_IHV_TASK_PRIORITY
f1_keywords:
 - _WDI_IHV_TASK_PRIORITY
 - dot11wificxtypes/_WDI_IHV_TASK_PRIORITY
 - WDI_IHV_TASK_PRIORITY
 - dot11wificxtypes/WDI_IHV_TASK_PRIORITY
dev_langs:
 - c++
---

## -description

> [!IMPORTANT]
> This topic is part of the [WiFiCx driver model](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx.md). WiFiCx is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features. The previous Wi-Fi driver model [WDI](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide.md) is in maintenance mode and will only receive high priority fixes.

The **WDI_IHV_TASK_PRIORITY** enumeration defines IHV task priorities.

## -enum-fields

### -field WDI_IHV_TASK_PRIORITY_HIGH:1

High priority.

### -field WDI_IHV_TASK_PRIORITY_MEDIUM:2

Medium priority.

### -field WDI_IHV_TASK_PRIORITY_LOW:3

Low priority.

## -remarks

The **WDI_IHV_TASK_PRIORITY** enum is a value in the [**WDI_TLV_ASSOCIATION_RESULT_PARAMETERS**](/windows-hardware/drivers/netcx/wdi-tlv-ihv-task-request-parameters) TLV.

## -see-also

[**WDI_TLV_ASSOCIATION_RESULT_PARAMETERS**](/windows-hardware/drivers/netcx/wdi-tlv-ihv-task-request-parameters)
