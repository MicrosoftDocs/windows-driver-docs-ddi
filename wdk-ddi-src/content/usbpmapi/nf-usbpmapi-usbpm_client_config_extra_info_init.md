---
UID: NF:usbpmapi.USBPM_CLIENT_CONFIG_EXTRA_INFO_INIT
title: USBPM_CLIENT_CONFIG_EXTRA_INFO_INIT function (usbpmapi.h)
description: Initializes a **USBPM_CLIENT_CONFIG_EXTRA_INFO** structure.
ms.assetid: 01f43080-0135-4de2-8c65-bb70a4a0e7ef
ms.date: 09/30/2018
f1_keywords:
 - "usbpmapi/USBPM_CLIENT_CONFIG_EXTRA_INFO_INIT"
ms.keywords: USBPM_CLIENT_CONFIG_EXTRA_INFO_INIT
tech.root: usbref
req.header: usbpmapi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver: 2.27
req.lib: 
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- usbpmapi.h
api_name: 
- USBPM_CLIENT_CONFIG_EXTRA_INFO_INIT
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# USBPM_CLIENT_CONFIG_EXTRA_INFO_INIT function


## -description

Initializes a [**USBPM_CLIENT_CONFIG_EXTRA_INFO**](ns-usbpmapi-_usbpm_client_config_extra_info.md) structure.

## -parameters

### -param ExtraInfo
[Out] A pointer to a [**USBPM_CLIENT_CONFIG_EXTRA_INFO**](ns-usbpmapi-_usbpm_client_config_extra_info.md) structure to initialize.

### -param WdmDeviceObject
[In] If the client is a kernel mode driver, it should set it to the kernel mode WDM device object after calling [**USBPM_CLIENT_CONFIG_INIT**](nf-usbpmapi-usbpm_client_config_init.md). In user mode, it is not used.

## -remarks

## -see-also
