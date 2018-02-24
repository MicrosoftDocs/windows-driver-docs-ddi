---
UID: NF:ks.KsGenerateThermalEvent
title: KsGenerateThermalEvent function
author: windows-driver-content
description: This function is used by clients (miniport drivers) that do not want to subscribe to the thermal manager, but want to do their own thermal management.
old-location: stream\ksgeneratethermalevent.htm
old-project: stream
ms.assetid: CE450017-1792-4B69-8289-902396D0D7B1
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ks/KsGenerateThermalEvent, KsGenerateThermalEvent function [Streaming Media Devices], KsGenerateThermalEvent, stream.ksgeneratethermalevent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ks.lib
-	ks.dll
apiname:
-	KsGenerateThermalEvent
product: Windows
targetos: Windows
req.typenames: 
---

# KsGenerateThermalEvent function


## -description


This function is used by clients (miniport drivers) that do not want to subscribe to the thermal manager, but want to do their own thermal management. 

There is a check that verifies whether the miniport driver has the query interface support for a thermal manager (for example, the device is actively managed by a thermal manager). In cases of devices managed by a thermal manager, this call is rejected.


## -syntax


````
void KSDDKAPI NTSTATUS NTAPI KsGenerateThermalEvent(
  _In_ PVOID                  Object,
  _In_ KSDEVICE_THERMAL_STATE Value
);
````


## -parameters




### -param Object [in]

Can be  <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a>, <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a>, or <a href="..\ks\ns-ks-_kspin.md">KSPIN</a>. Depending on the object passed, the thermal notification is sent device-wide, filter-wide, or to the pin.


### -param Value [in]

KSDEVICE_THERMAL_STATE_LOW or KSDEVICE_THERMAL_STATE_HIGH


## -returns



 Returns STATUS_SUCCESS for success and STATUS_INVALID_DEVICE_REQUEST if the parameters are incorrect.



