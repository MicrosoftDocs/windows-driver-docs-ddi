---
UID: NS:d3dkmddi._DXGKARG_DESTROYPERIODICFRAMENOTIFICATION
title: "_DXGKARG_DESTROYPERIODICFRAMENOTIFICATION"
author: windows-driver-content
description: The arguments used to destroy a periodic frame notification.
old-location: display\dxgkarg_destroyperiodicframenotification.htm
old-project: display
ms.assetid: 94797515-3440-46A9-ACBD-09D005A33CE3
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmddi/DXGKARG_DESTROYPERIODICFRAMENOTIFICATION, DXGKARG_DESTROYPERIODICFRAMENOTIFICATION structure [Display Devices], _DXGKARG_DESTROYPERIODICFRAMENOTIFICATION, display.dxgkarg_destroyperiodicframenotification, DXGKARG_DESTROYPERIODICFRAMENOTIFICATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGKARG_DESTROYPERIODICFRAMENOTIFICATION
product: Windows
targetos: Windows
req.typenames: DXGKARG_DESTROYPERIODICFRAMENOTIFICATION
---

# _DXGKARG_DESTROYPERIODICFRAMENOTIFICATION structure


## -description


The arguments used to destroy a periodic frame notification.


## -syntax


````
typedef struct _DXGKARG_DESTROYPERIODICFRAMENOTIFICATION {
  HANDLE hNotification;
  HANDLE hAdapter;
} DXGKARG_DESTROYPERIODICFRAMENOTIFICATION;
````


## -struct-fields




### -field hNotification

A handle to the notification object created by the KMD.


### -field hAdapter

A handle to the adapter that the notification object was created for.

