---
UID: NS:d3dkmddi._DXGKARG_QUERYCONNECTIONCHANGE
title: "_DXGKARG_QUERYCONNECTIONCHANGE"
author: windows-driver-content
description: Used to hold the arguments for DXGKDDI_QUERYCONNECTIONCHANGE.
old-location: display\dxgkarg_queryconnectionchange.htm
old-project: display
ms.assetid: 6B91F3F0-B02D-46F3-9086-EA32F043FC16
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*IN_PDXGKARG_QUERYCONNECTIONCHANGE, DXGKARG_QUERYCONNECTIONCHANGE, DXGKARG_QUERYCONNECTIONCHANGE structure [Display Devices], _DXGKARG_QUERYCONNECTIONCHANGE, d3dkmddi/DXGKARG_QUERYCONNECTIONCHANGE, display.dxgkarg_queryconnectionchange"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGKARG_QUERYCONNECTIONCHANGE
product: Windows
targetos: Windows
req.typenames: DXGKARG_QUERYCONNECTIONCHANGE
---

# _DXGKARG_QUERYCONNECTIONCHANGE structure


## -description


Used to hold the arguments for <a href="https://msdn.microsoft.com/8C09B692-3439-4ACD-942D-F7A107E2B4DA">DXGKDDI_QUERYCONNECTIONCHANGE</a>.


## -struct-fields




### -field ConnectionChange

[out] Buffer into which the oldest available change is copied by driver.

