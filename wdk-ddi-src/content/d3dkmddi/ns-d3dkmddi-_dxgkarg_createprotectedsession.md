---
UID: NS:d3dkmddi._DXGKARG_CREATEPROTECTEDSESSION
title: "_DXGKARG_CREATEPROTECTEDSESSION"
author: windows-driver-content
description: Used to create a protected session.
old-location: display\dxgkarg_createprotectedsession.htm
old-project: display
ms.assetid: 37A9A957-344F-48F6-93DE-D81DE5C20076
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGKARG_CREATEPROTECTEDSESSION structure [Display Devices], _DXGKARG_CREATEPROTECTEDSESSION, display.dxgkarg_createprotectedsession, DXGKARG_CREATEPROTECTEDSESSION, d3dkmddi/DXGKARG_CREATEPROTECTEDSESSION, *INOUT_PDXGKARG_CREATEPROTECTEDSESSION
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
-	DXGKARG_CREATEPROTECTEDSESSION
product: Windows
targetos: Windows
req.typenames: DXGKARG_CREATEPROTECTEDSESSION
---

# _DXGKARG_CREATEPROTECTEDSESSION structure


## -description


Used to create a protected session.


## -syntax


````
typedef struct _DXGKARG_CREATEPROTECTEDSESSION {
  HANDLE hProtectedSession;
  PVOID  pPrivateDriverData;
  UINT   PrivateDriverDataSize;
} DXGKARG_CREATEPROTECTEDSESSION;
````


## -struct-fields




### -field hProtectedSession

An assigned value for the protected session that was passed to DxgkDdiCreateProtectedSession.



### -field pPrivateDriverData

A pointer to the driver data.


### -field PrivateDriverDataSize

The size of the data.

