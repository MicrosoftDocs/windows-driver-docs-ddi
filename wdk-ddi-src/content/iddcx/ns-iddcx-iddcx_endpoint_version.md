---
UID: NS:iddcx.IDDCX_ENDPOINT_VERSION
title: IDDCX_ENDPOINT_VERSION (iddcx.h)
description: Gives version information about the video data endpoint.
old-location: display\iddcx_endpoint_version.htm
tech.root: display
ms.date: 08/08/2022
keywords: ["IDDCX_ENDPOINT_VERSION structure"]
ms.keywords: IDDCX_ENDPOINT_VERSION, IDDCX_ENDPOINT_VERSION structure [Display Devices], display.iddcx_endpoint_version, iddcx/IDDCX_ENDPOINT_VERSION
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
req.typenames: 
f1_keywords:
 - IDDCX_ENDPOINT_VERSION
 - iddcx/IDDCX_ENDPOINT_VERSION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_ENDPOINT_VERSION
---

# IDDCX_ENDPOINT_VERSION structure

## -description

A **IDDCX_ENDPOINT_VERSION** structure provides version information about the video data endpoint.

## -struct-fields

### -field Size

Total size of this structure, in bytes.

### -field MajorVer

The major version number. This value is defined by the driver.

### -field MinorVer

The minor version number. This value is defined by the driver.

### -field Build

The build number. This value is defined by the driver.

### -field SKU

The SKU type. This value is defined by the driver.

## -see-also

[**IDDCX_ENDPOINT_DIAGNOSTIC_INFO**](ns-iddcx-iddcx_endpoint_diagnostic_info.md)
