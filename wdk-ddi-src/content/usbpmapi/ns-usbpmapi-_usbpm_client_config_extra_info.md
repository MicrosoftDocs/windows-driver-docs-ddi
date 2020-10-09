---
UID: NS:usbpmapi._USBPM_CLIENT_CONFIG_EXTRA_INFO
title: _USBPM_CLIENT_CONFIG_EXTRA_INFO (usbpmapi.h)
description: Contains optional information used to configure the client driver's registration.
ms.assetid: 919040a7-21d8-4fc4-9539-fdc7fff53b40
ms.date: 09/30/2018
keywords: ["USBPM_CLIENT_CONFIG_EXTRA_INFO structure"]
tech.root: usbref
ms.keywords: _USBPM_CLIENT_CONFIG_EXTRA_INFO, USBPM_CLIENT_CONFIG_EXTRA_INFO, *PUSBPM_CLIENT_CONFIG_EXTRA_INFO,
req.header: usbpmapi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 1.27
req.umdf-ver: 2.27
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: USBPM_CLIENT_CONFIG_EXTRA_INFO, *PUSBPM_CLIENT_CONFIG_EXTRA_INFO
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _USBPM_CLIENT_CONFIG_EXTRA_INFO
 - usbpmapi/_USBPM_CLIENT_CONFIG_EXTRA_INFO
 - PUSBPM_CLIENT_CONFIG_EXTRA_INFO
 - usbpmapi/PUSBPM_CLIENT_CONFIG_EXTRA_INFO
 - USBPM_CLIENT_CONFIG_EXTRA_INFO
 - usbpmapi/USBPM_CLIENT_CONFIG_EXTRA_INFO
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - usbpmapi.h
api_name:
 - _USBPM_CLIENT_CONFIG_EXTRA_INFO
---

# _USBPM_CLIENT_CONFIG_EXTRA_INFO structure


## -description

Contains optional information used to configure the client driver's registration.

## -struct-fields

### -field Size

Size of this structure.

### -field WdmDeviceObject

If the client is a kernel mode driver, this is the kernel mode WDM device for the client driver. In user mode, it is not used.

## -remarks

## -see-also

