---
UID: NF:usbpmapi.USBPM_CONNECTOR_PROPERTIES_INIT
title: USBPM_CONNECTOR_PROPERTIES_INIT function (usbpmapi.h)
description: Initializes a **USBPM_CONNECTOR_PROPERTIES** structure.
ms.date: 09/30/2018
keywords: ["USBPM_CONNECTOR_PROPERTIES_INIT function"]
ms.keywords: USBPM_CONNECTOR_PROPERTIES_INIT
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
targetos: Windows
ms.custom: RS5
f1_keywords:
 - USBPM_CONNECTOR_PROPERTIES_INIT
 - usbpmapi/USBPM_CONNECTOR_PROPERTIES_INIT
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - usbpmapi.h
api_name:
 - USBPM_CONNECTOR_PROPERTIES_INIT
---

# USBPM_CONNECTOR_PROPERTIES_INIT function


## -description

Initializes a [**USBPM_CONNECTOR_PROPERTIES**](ns-usbpmapi-_usbpm_connector_properties.md) structure. The client driver must call this function before calling [**UsbPm_RetrieveCoonnectorProperties**](nf-usbpmapi-usbpm_retrieveconnectorproperties.md).

## -parameters

### -param Properties

[Out] A pointer to a [**USBPM_CONNECTOR_PROPERTIES**](ns-usbpmapi-_usbpm_connector_properties.md) to initialize.

## -remarks

## -see-also

