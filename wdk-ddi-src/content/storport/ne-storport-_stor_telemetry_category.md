---
UID: NE:storport._STOR_TELEMETRY_CATEGORY
title: STOR_TELEMETRY_CATEGORY
author: windows-driver-content
description: The STOR_TELEMETRY_CATEGORY enumerator indicates the category of the telemetry event being logged in StorPortLogTelemetryEx.
tech.root: storage
ms.assetid: ad3a4a08-b060-4979-86ca-35d8b868b7f2
ms.author: windowsdriverdev
ms.date: 03/06/2019
keywords: ["STOR_TELEMETRY_CATEGORY enumeration"]
f1_keywords:
 - "storport/STOR_TELEMETRY_CATEGORY"
 - "STOR_TELEMETRY_CATEGORY"
ms.keywords: STOR_TELEMETRY_CATEGORY, STOR_TELEMETRY_CATEGORY, *PSTOR_TELEMETRY_CATEGORY, StorPortLogTelemetryEx, STORPORT_TELEMETRY_EVENT
req.header: storport.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: STOR_TELEMETRY_CATEGORY, *PSTOR_TELEMETRY_CATEGORY
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - storport.h
api_name: 
 - STOR_TELEMETRY_CATEGORY
product: 
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# STOR_TELEMETRY_CATEGORY enumeration

## -description

The STOR_TELEMETRY_CATEGORY enumerator indicates the category of the telemetry event being logged in [StorPortLogTelemetryEx](nf-storport-storportlogtelemetryex.md).

## -enum-fields

### -field StorTelemetryCategory

Indicates that the telemetry event can be used for general purpose telemetry and diagnostics. This category maps to the MICROSOFT_KEYWORD_TELEMETRY category defined in *MicrosoftTelemetry.h*.

### -field StorMeasuresCategory

Indicates that the telemetry event can be used to feed into quality measures. This category maps to the MICROSOFT_KEYWORD_MEASURES category defined in *MicrosoftTelemetry.h*.

## -remarks

## -see-also

[StorPortLogTelemetryEx](nf-storport-storportlogtelemetryex.md)
