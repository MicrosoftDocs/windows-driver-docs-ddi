---
UID: NS:dispmprt._DXGK_DIAGTYPE_NOTIFICATIONS
title: _DXGK_DIAGTYPE_NOTIFICATIONS (dispmprt.h)
description: A structure used to identify one or more diagnostic types in the Notifications category.
ms.assetid: cfebcf14-30cd-4577-a25d-98eea944834e
ms.date: 10/19/2018
ms.topic: struct
f1_keywords:
 - "dispmprt/_DXGK_DIAGTYPE_NOTIFICATIONS"
ms.keywords: _DXGK_DIAGTYPE_NOTIFICATIONS, DXGK_DIAGTYPE_NOTIFICATIONS,
req.header: dispmprt.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGK_DIAGTYPE_NOTIFICATIONS
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- dispmprt.h
api_name:
- _DXGK_DIAGTYPE_NOTIFICATIONS
product: 
- Windows
targetos: Windows
tech.root: display
---

# _DXGK_DIAGTYPE_NOTIFICATIONS structure

## -description

A structure used to identify one or more diagnostic types in the Notifications category.

## -struct-fields

### -field PanelSelfRefreshSoftware

Indicates a diagnostic reported by the driver when the driver expects that panel self-refresh is being enabled or disabled.  This should be a light-weight diagnostic, so reported in the NoninvasiveTypes in a call to DxgkDdiQueryDiagnosticTypesSupported, which would be sent during a DDI call from the OS which causes the state to change or in a normal code path where the state change would naturally be acted upon.

### -field PanelSelfRefreshHardware

Indicates a diagnostic reported by the driver when the driver receives a notification from the hardware or when the driver queries hardware to find that panel self-refresh has been enabled or disabled.  This diagnostic is intended to be used for detailed investigation so accuracy in the reporting of PSR state changes is more important that efficiency however if hardware supports efficient notification, that is ideal.

### -field Reserved

Reserved.

### -field Value

The value of the notification.

