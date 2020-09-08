---
UID: NE:usbpmapi._USBPM_ACCESS_TYPE
title: _USBPM_ACCESS_TYPE (usbpmapi.h)
description: Defines the access types for calling Policy Manager functions.
ms.assetid: 16469a5c-1c6a-4fa3-9189-17ba7d51291d
ms.date: 09/30/2018
keywords: ["USBPM_ACCESS_TYPE enumeration"]
ms.keywords: _USBPM_ACCESS_TYPE, USBPM_ACCESS_TYPE, *PUSBPM_ACCESS_TYPE,
tech.root: usbref
req.header: usbpmapi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 1.27
req.umdf-ver: 2.27
req.ddi-compliance: 
req.max-support: 
req.typenames: USBPM_ACCESS_TYPE, *PUSBPM_ACCESS_TYPE
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _USBPM_ACCESS_TYPE
 - usbpmapi/_USBPM_ACCESS_TYPE
 - PUSBPM_ACCESS_TYPE
 - usbpmapi/PUSBPM_ACCESS_TYPE
 - USBPM_ACCESS_TYPE
 - usbpmapi/USBPM_ACCESS_TYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - usbpmapi.h
api_name:
 - USBPM_ACCESS_TYPE
---

# _USBPM_ACCESS_TYPE enumeration


## -description

Defines the access types that the client driver can specify in [**USBPM_CLIENT_CONFIG**](ns-usbpmapi-_usbpm_client_config.md) when calling [**UsbPm_Register**](nf-usbpmapi-usbpm_register.md).

## -enum-fields

### -field UsbPmAccessQuery 

Access for calling **UsbPm_Retrieve*** functions.

### -field UsbPmAccessAssignConnectorPowerLevel 

Access for calling [**UsbPm_AssignConnectorPowerLevelAsync**](nf-usbpmapi-usbpm_assignconnectorpowerlevel.md).

### -field UsbPmAccessAll 

Access to all functions.

## -remarks

## -see-also

