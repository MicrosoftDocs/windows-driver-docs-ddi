---
UID: NS:d3dkmddi._DXGKARG_CREATEPERIODICFRAMENOTIFICATION
title: "_DXGKARG_CREATEPERIODICFRAMENOTIFICATION"
author: windows-driver-content
description: The arguments needed to create a periodic frame notification.
old-location: display\dxgkarg_createperiodicframenotification.htm
old-project: display
ms.assetid: 455C3FBD-2E0D-4CD7-B753-E53ED58A7F6F
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_DXGKARG_CREATEPERIODICFRAMENOTIFICATION, *INOUT_PDXGKARG_CREATEPERIODICFRAMENOTIFICATION, display.dxgkarg_createperiodicframenotification, DXGKARG_CREATEPERIODICFRAMENOTIFICATION structure [Display Devices], DXGKARG_CREATEPERIODICFRAMENOTIFICATION, d3dkmddi/DXGKARG_CREATEPERIODICFRAMENOTIFICATION"
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
-	DXGKARG_CREATEPERIODICFRAMENOTIFICATION
product: Windows
targetos: Windows
req.typenames: DXGKARG_CREATEPERIODICFRAMENOTIFICATION
---

# _DXGKARG_CREATEPERIODICFRAMENOTIFICATION structure


## -description


The arguments needed to create a periodic frame notification.


## -syntax


````
typedef struct _DXGKARG_CREATEPERIODICFRAMENOTIFICATION {
  HANDLE                         hAdapter;
  D3DDDI_VIDEO_PRESENT_TARGET_ID VidPnTargetID;
  UINT64                         Time;
  UINT                           NotificationID;
  HANDLE                         hNotification;
} DXGKARG_CREATEPERIODICFRAMENOTIFICATION;
````


## -struct-fields




### -field hAdapter

A handle to the adapter associated with VidPnSourceID.


### -field VidPnTargetId

 


### -field Time

Represents an offset before the VSync. The Time value may not be longer than a VSync interval while in VSync mode. In units of 100ns.


### -field NotificationID

Represents an ID for the notification that will be used to track which interrupt has fired from the GPU.


### -field hNotification

A Handle to the notification object, later used to destroy the object.


#### - VidPnTargetID

The output that the compositor wishes to receive notifications for.

