---
UID: NE:pointofservicecommontypes.DriverUnifiedPosHealthCheckLevel
title: DriverUnifiedPosHealthCheckLevel
author: windows-driver-content
description: This enumeration indicates the type of health check to be performed when CheckHealthAsync is called on a POS device.
old-location: pos\unifiedposhealthchecklevel.htm
old-project: pos
ms.assetid: 101a74c8-a0c2-4820-b9a1-41e39ee4cf11
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: pointofservicecommontypes/Interactive, pointofservicecommontypes/UnknownHealthCheckLevel, pointofservicecommontypes/DriverUnifiedPosHealthCheckLevel, pointofservicecommontypes/POSInternal, External, pointofservicecommontypes/External, Interactive, DriverUnifiedPosHealthCheckLevel enumeration, pos.unifiedposhealthchecklevel, DriverUnifiedPosHealthCheckLevel, UnknownHealthCheckLevel, POSInternal
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: pointofservicecommontypes.h
req.include-header: Pointofservicecommontypes.h
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
req.irql: Called at PASSIVE_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pointofservicecommontypes.h
apiname:
-	DriverUnifiedPosHealthCheckLevel
product: Windows
targetos: Windows
req.typenames: DriverUnifiedPosHealthCheckLevel
---

# DriverUnifiedPosHealthCheckLevel enumeration


## -description


This enumeration indicates the type of health check to be performed when CheckHealthAsync is called on a POS device.


## -syntax


````
typedef enum _DriverUnifiedPosHealthCheckLevel { 
  UnknownHealthCheckLevel  = 0,
  POSInternal              = 1,
  External                 = 2,
  Interactive              = 3
} DriverUnifiedPosHealthCheckLevel;
````


## -enum-fields




#### - UnknownHealthCheckLevel

The type of health check is not known.


#### - POSInternal

Performs a health check without altering the device. The device is tested by internal tests as far as possible.


#### - External

Performs a more thorough test which may affect the device. For example, a printer may produce some output.


#### - Interactive

May display a dialog box that displays test options and results so that you can test the device interactively. 

