---
UID: NE:ks.KSPIN_MDL_CACHING_EVENT
title: KSPIN_MDL_CACHING_EVENT
author: windows-driver-content
description: This enumeration is used internally by the operating system.
old-location: stream\kspin_mdl_caching_event.htm
old-project: stream
ms.assetid: 74A7C2C8-F12B-4753-8E1F-C425B0B56788
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: KSPIN_MDL_CACHING_NOTIFY_ADDSAMPLE, KSPIN_MDL_CACHING_EVENT enumeration [Streaming Media Devices], ks/KSPIN_MDL_CACHING_NOTIFY_CLEANALL_WAIT, KSPIN_MDL_CACHING_NOTIFY_CLEANALL_WAIT, ks/KSPIN_MDL_CACHING_NOTIFY_CLEANALL_NOWAIT, KSPIN_MDL_CACHING_NOTIFY_CLEANALL_NOWAIT, KSPIN_MDL_CACHING_NOTIFY_CLEANUP, KSPIN_MDL_CACHING_EVENT, ks/KSPIN_MDL_CACHING_NOTIFY_CLEANUP, ks/KSPIN_MDL_CACHING_NOTIFY_ADDSAMPLE, stream.kspin_mdl_caching_event, ks/KSPIN_MDL_CACHING_EVENT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ks.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KSPIN_MDL_CACHING_EVENT
product: Windows
targetos: Windows
req.typenames: KSPIN_MDL_CACHING_EVENT
---

# KSPIN_MDL_CACHING_EVENT enumeration


## -description


This enumeration is used internally by the operating system.


## -syntax


````
typedef enum  { 
  KSPIN_MDL_CACHING_NOTIFY_CLEANUP,
  KSPIN_MDL_CACHING_NOTIFY_CLEANALL_WAIT,
  KSPIN_MDL_CACHING_NOTIFY_CLEANALL_NOWAIT,
  KSPIN_MDL_CACHING_NOTIFY_ADDSAMPLE
} KSPIN_MDL_CACHING_EVENT;
````


## -enum-fields




### -field KSPIN_MDL_CACHING_NOTIFY_CLEANUP

This value is used internally by the operating system.


### -field KSPIN_MDL_CACHING_NOTIFY_CLEANALL_WAIT

This value is used internally by the operating system.


### -field KSPIN_MDL_CACHING_NOTIFY_CLEANALL_NOWAIT

This value is used internally by the operating system.


### -field KSPIN_MDL_CACHING_NOTIFY_ADDSAMPLE

This value is used internally by the operating system.

