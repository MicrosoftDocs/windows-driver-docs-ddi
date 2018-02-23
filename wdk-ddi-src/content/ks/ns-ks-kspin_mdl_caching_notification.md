---
UID: NS:ks.KSPIN_MDL_CACHING_NOTIFICATION
title: KSPIN_MDL_CACHING_NOTIFICATION
author: windows-driver-content
description: This structure is used internally by the operating system.
old-location: stream\kspin_mdl_caching_notification.htm
old-project: stream
ms.assetid: 93BAAF88-3F82-4E32-B403-4028ECF21F9A
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: stream.kspin_mdl_caching_notification, PKSPIN_MDL_CACHING_NOTIFICATION structure pointer [Streaming Media Devices], KSPIN_MDL_CACHING_NOTIFICATION structure [Streaming Media Devices], PKSPIN_MDL_CACHING_NOTIFICATION, ks/KSPIN_MDL_CACHING_NOTIFICATION, KSPIN_MDL_CACHING_NOTIFICATION, ks/PKSPIN_MDL_CACHING_NOTIFICATION, *PKSPIN_MDL_CACHING_NOTIFICATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KSPIN_MDL_CACHING_NOTIFICATION
product: Windows
targetos: Windows
req.typenames: "*PKSPIN_MDL_CACHING_NOTIFICATION, KSPIN_MDL_CACHING_NOTIFICATION"
---

# KSPIN_MDL_CACHING_NOTIFICATION structure


## -description


This structure is used internally by the operating system.


## -syntax


````
typedef struct {
  KSPIN_MDL_CACHING_EVENT Event;
  PVOID                   Buffer;
} KSPIN_MDL_CACHING_NOTIFICATION, *PKSPIN_MDL_CACHING_NOTIFICATION;
````


## -struct-fields




### -field Event

This member is used internally by the operating system.


### -field Buffer

This member is used internally by the operating system.

