---
UID: NS:ntddvdeo._VIDEO_WIN32K_CALLBACKS
title: "_VIDEO_WIN32K_CALLBACKS"
author: windows-driver-content
description: The VIDEO_WIN32K_CALLBACKS structure is reserved for system use.
old-location: display\video_win32k_callbacks.htm
old-project: display
ms.assetid: dec6c610-811c-40cb-a099-1a35b91d2ee8
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PVIDEO_WIN32K_CALLBACKS, ,, 2, 3, A, B, C, D, E, I, K, L, N, O, P, PVIDEO_WIN32K_CALLBACKS, PVIDEO_WIN32K_CALLBACKS structure pointer [Display Devices], S, V, VIDEO_WIN32K_CALLBACKS, VIDEO_WIN32K_CALLBACKS structure [Display Devices], Video_Structs_3c169102-2431-4217-b9e2-80ef23ee8096.xml, W, _, _VIDEO_WIN32K_CALLBACKS, display.video_win32k_callbacks, ntddvdeo/PVIDEO_WIN32K_CALLBACKS, ntddvdeo/VIDEO_WIN32K_CALLBACKS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddvdeo.h
req.include-header: Ntddvdeo.h
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
-	ntddvdeo.h
apiname:
-	VIDEO_WIN32K_CALLBACKS
product: Windows
targetos: Windows
req.typenames: VIDEO_WIN32K_CALLBACKS, *PVIDEO_WIN32K_CALLBACKS
---

# _VIDEO_WIN32K_CALLBACKS structure


## -description


The VIDEO_WIN32K_CALLBACKS structure is reserved for system use.


## -syntax


````
typedef struct _VIDEO_WIN32K_CALLBACKS {
  PVOID                 PhysDisp;
  PVIDEO_WIN32K_CALLOUT Callout;
  ULONG                 bACPI;
  HANDLE                pPhysDeviceObject;
  ULONG                 DualviewFlags;
} VIDEO_WIN32K_CALLBACKS, *PVIDEO_WIN32K_CALLBACKS;
````


## -struct-fields




### -field PhysDisp

Reserved for system use.


### -field Callout

Reserved for system use.


### -field bACPI

Reserved for system use.


### -field pPhysDeviceObject

Reserved for system use.


### -field DualviewFlags

Reserved for system use.

