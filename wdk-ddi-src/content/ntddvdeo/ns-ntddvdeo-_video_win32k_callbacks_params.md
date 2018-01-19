---
UID: NS:ntddvdeo._VIDEO_WIN32K_CALLBACKS_PARAMS
title: _VIDEO_WIN32K_CALLBACKS_PARAMS
author: windows-driver-content
description: The VIDEO_WIN32K_CALLBACKS_PARAMS structure and the VIDEO_WIN32K_CALLBACKS_PARAMS_TYPE enumeration are reserved for system use.
old-location: display\video_win32k_callbacks_params.htm
old-project: display
ms.assetid: d533721f-b4c8-44f9-9c39-f312e1ec9895
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _VIDEO_WIN32K_CALLBACKS_PARAMS, VIDEO_WIN32K_CALLBACKS_PARAMS, *PVIDEO_WIN32K_CALLBACKS_PARAMS
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
req.alt-api: VIDEO_WIN32K_CALLBACKS_PARAMS
req.alt-loc: ntddvdeo.h
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
req.typenames: VIDEO_WIN32K_CALLBACKS_PARAMS, *PVIDEO_WIN32K_CALLBACKS_PARAMS
---

# _VIDEO_WIN32K_CALLBACKS_PARAMS structure



## -description
The VIDEO_WIN32K_CALLBACKS_PARAMS structure and the VIDEO_WIN32K_CALLBACKS_PARAMS_TYPE enumeration are reserved for system use.



## -syntax

````
typedef struct _VIDEO_WIN32K_CALLBACKS_PARAMS {
  VIDEO_WIN32K_CALLBACKS_PARAMS_TYPE CalloutType;
  PVOID                              PhysDisp;
  ULONG_PTR                          Param;
  LONG                               Status;
} VIDEO_WIN32K_CALLBACKS_PARAMS, *PVIDEO_WIN32K_CALLBACKS_PARAMS;
````


## -struct-fields

### -field CalloutType

Reserved for system use.


### -field PhysDisp

Reserved for system use.


### -field Param

Reserved for system use.


### -field Status

Reserved for system use.


## -remarks
