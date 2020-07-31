---
UID: NF:ks.KsGenerateThermalEvent
title: KsGenerateThermalEvent function (ks.h)
description: This function is used by clients (miniport drivers) that do not want to subscribe to the thermal manager, but want to do their own thermal management.
old-location: stream\ksgeneratethermalevent.htm
tech.root: stream
ms.assetid: CE450017-1792-4B69-8289-902396D0D7B1
ms.date: 04/23/2018
keywords: ["KsGenerateThermalEvent function"]
ms.keywords: KsGenerateThermalEvent, KsGenerateThermalEvent function [Streaming Media Devices], ks/KsGenerateThermalEvent, stream.ksgeneratethermalevent
f1_keywords:
 - "ks/KsGenerateThermalEvent"
 - "KsGenerateThermalEvent"
req.header: ks.h
req.include-header: 
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ks.lib
- ks.dll
api_name:
- KsGenerateThermalEvent
targetos: Windows
req.typenames: 
---

# KsGenerateThermalEvent function


## -description


This function is used by clients (miniport drivers) that do not want to subscribe to the thermal manager, but want to do their own thermal management. 

There is a check that verifies whether the miniport driver has the query interface support for a thermal manager (for example, the device is actively managed by a thermal manager). In cases of devices managed by a thermal manager, this call is rejected.


## -parameters




### -param Object [in]

Can be  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a>. Depending on the object passed, the thermal notification is sent device-wide, filter-wide, or to the pin.


### -param Value [in]

KSDEVICE_THERMAL_STATE_LOW or KSDEVICE_THERMAL_STATE_HIGH


## -returns



 Returns STATUS_SUCCESS for success and STATUS_INVALID_DEVICE_REQUEST if the parameters are incorrect.



