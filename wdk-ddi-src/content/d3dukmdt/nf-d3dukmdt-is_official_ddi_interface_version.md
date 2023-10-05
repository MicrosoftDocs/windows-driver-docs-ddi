---
UID: NF:d3dukmdt.IS_OFFICIAL_DDI_INTERFACE_VERSION
title: IS_OFFICIAL_DDI_INTERFACE_VERSION macro (d3dukmdt.h)
description: Learn more about the IS_OFFICIAL_DDI_INTERFACE_VERSION macro.
ms.date: 10/04/2023
keywords: ["IS_OFFICIAL_DDI_INTERFACE_VERSION macro"]
ms.keywords: IS_OFFICIAL_DDI_INTERFACE_VERSION
req.header: d3dukmdt.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
tech.root: display
f1_keywords:
 - IS_OFFICIAL_DDI_INTERFACE_VERSION
 - d3dukmdt/IS_OFFICIAL_DDI_INTERFACE_VERSION
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - IS_OFFICIAL_DDI_INTERFACE_VERSION
dev_langs:
 - c++
---

# IS_OFFICIAL_DDI_INTERFACE_VERSION macro

## -description

The **IS_OFFICIAL_DDI_INTERFACE_VERSION** macro indicates whether the specified interface version is an official DXGK interface version.

## -parameters

### -param version

The version to test. See **IS_OFFICIAL_DDI_INTERFACE_VERSION**'s definition in *d3dukmdt.h* for a list of valid values.

## -remarks

**IS_OFFICIAL_DDI_INTERFACE_VERSION** returns TRUE if **version** is set to an official DXGK interface version. Otherwise, it returns FALSE.
