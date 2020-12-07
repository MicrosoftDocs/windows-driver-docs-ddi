---
UID: NF:storport.StorPortQueryConfiguration
title: StorPortQueryConfiguration function
description: A miniport can call StorPortQueryConfiguration to get the specific configuration of the platform.
tech.root: storage
ms.date: 03/06/2019
keywords: ["StorPortQueryConfiguration function"]
ms.keywords: StorPortQueryConfiguration
req.header: storport.h
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
ms.custom: 19H1
f1_keywords:
 - StorPortQueryConfiguration
 - storport/StorPortQueryConfiguration
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - storport.h
api_name:
 - StorPortQueryConfiguration
product:
 - Windows
dev_langs:
 - c++
---

# StorPortQueryConfiguration function


## -description

A miniport can call **StorPortQueryConfiguration** to query for the specific configuration of the platform.

## -parameters

### -param HwDeviceExtension

Pointer to the hardware device extension for the host bus adapter (HBA).

### -param Type

A [STORPORT_QUERY_CONFIGURATION_TYPE](ne-storport-storport_query_configuration_type.md) enum value that indicates the type of configuration to query.

### -param Enabled

Pointer to a **BOOLEAN** value in which the Storport driver will return one of the following values.

| Value | Description |
| ----- | ----------- |
| **TRUE** | The configuration specified by *Type* is enabled. |
| **FALSE** | The configuration specified by *Type* is not enabled. |

## -returns

**StorPortQueryConfiguration** returns one of the following status codes:

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_INVALID_PARAMETER | *Enabled* is **NULL** or the value specified in *Type* is invalid. |
| STOR_STATUS_NOT_IMPLEMENTED | This function is not implemented on the active operating system. |
| STOR_STATUS_SUCCESS | The query completed successfully. |

## -remarks

## -see-also

[STORPORT_QUERY_CONFIGURATION_TYPE](ne-storport-storport_query_configuration_type.md)

