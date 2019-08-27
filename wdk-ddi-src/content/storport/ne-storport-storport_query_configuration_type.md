---
UID: NE:storport._STORPORT_QUERY_CONFIGURATION_TYPE
title: STORPORT_QUERY_CONFIGURATION_TYPE
author: windows-driver-content
description: The STORPORT_QUERY_CONFIGURATION_TYPE enumerator identifies the configuration being queried in StorPortQueryConfiguration.
tech.root: storage
ms.assetid: c91774dc-a244-46e7-a5bb-ef7b8493184f
ms.author: windowsdriverdev
ms.date: 03/20/2019
ms.topic: enum
f1_keywords:
 - "storport/STORPORT_QUERY_CONFIGURATION_TYPE"
ms.keywords: STORPORT_QUERY_CONFIGURATION_TYPE, STORPORT_QUERY_CONFIGURATION_TYPE, *PSTORPORT_QUERY_CONFIGURATION_TYPE, 
req.header: storport.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: STORPORT_QUERY_CONFIGURATION_TYPE, *PSTORPORT_QUERY_CONFIGURATION_TYPE
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - storport.h
api_name: 
 - STORPORT_QUERY_CONFIGURATION_TYPE
product:
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# STORPORT_QUERY_CONFIGURATION_TYPE enumeration

## -description

The **STORPORT_QUERY_CONFIGURATION_TYPE** enumerator identifies the configuration type being queried in [StorPortQueryConfiguration](nf-storport-storportqueryconfiguration.md).

## -enum-fields

### -field StorportQueryConfigurationD3

Query whether the device has a D3 configuration.

### -field StorportQueryConfigurationMax

First illegal configuration value; do not use.

## -remarks

## -see-also

[StorPortQueryConfiguration](nf-storport-storportqueryconfiguration.md)
