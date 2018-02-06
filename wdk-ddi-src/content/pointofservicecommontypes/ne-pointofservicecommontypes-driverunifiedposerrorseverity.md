---
UID: NE:pointofservicecommontypes.DriverUnifiedPosErrorSeverity
title: DriverUnifiedPosErrorSeverity
author: windows-driver-content
description: This enumeration indicates the severity of the error.
old-location: pos\unifiedposerrorseverity.htm
old-project: pos
ms.assetid: a8c592fa-2736-49e4-8d4d-8729baef9c49
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: Unrecoverable, Recoverable, pointofservicecommontypes/UnknownErrorSeverity, pos.unifiedposerrorseverity, DriverUnifiedPosErrorSeverity, UnknownErrorSeverity, pointofservicecommontypes/ AssistanceRequired, pointofservicecommontypes/Warning, Warning, Fatal, pointofservicecommontypes/Fatal, pointofservicecommontypes/Unrecoverable, pointofservicecommontypes/Recoverable, pointofservicecommontypes/DriverUnifiedPosErrorSeverity, DriverUnifiedPosErrorSeverity enumeration, AssistanceRequired
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
-	DriverUnifiedPosErrorSeverity
product: Windows
targetos: Windows
req.typenames: DriverUnifiedPosErrorSeverity
---

# DriverUnifiedPosErrorSeverity enumeration


## -description


This enumeration indicates the severity of the error.


## -syntax


````
typedef enum _DriverUnifiedPosErrorSeverity { 
  UnknownErrorSeverity  = 0,
  Warning               = 1,
  Recoverable           = 2,
  Unrecoverable         = 3,
   AssistanceRequired   = 4,
  Fatal                 = 5
} DriverUnifiedPosErrorSeverity;
````


## -enum-fields




### -field UnknownErrorSeverity

The severity of the error is not known.


### -field Warning

The error or warning is informational.


### -field Recoverable

The device can recover from the error without closing the application or rebooting.


### -field Unrecoverable

The device is still working, but it must close the application to recover from the error.


### -field AssistanceRequired

Intervention is needed to respond to the error.


### -field Fatal

The error requires that the device be rebooted.

