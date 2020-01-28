---
UID: NF:poscx.PosCxIsPosApp
title: PosCxIsPosApp function (poscx.h)
description: PosCxIsPosApp checks if the open instance is associated with a point-of-service application.
old-location: pos\poscxisposapp.htm
tech.root: pos
ms.assetid: 890A0ACB-9717-4BF8-87B5-A6C1FAD661C2
ms.date: 02/23/2018
ms.keywords: PosCxIsPosApp, PosCxIsPosApp function, pos.poscxisposapp, poscx/PosCxIsPosApp
f1_keywords:
 - "poscx/PosCxIsPosApp"
req.header: poscx.h
req.include-header: Poscx.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- poscx.h
api_name:
- PosCxIsPosApp
product:
- Windows
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# PosCxIsPosApp function


## -description


PosCxIsPosApp checks if the open instance is associated with a point-of-service application.


## -parameters




### -param device [in]

A handle to a framework device object that represents the device.


### -param fileObject [in]

A handle to a framework file object that identifies the caller, usually acquired with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestgetfileobject">WdfRequestGetFileObject</a>.


## -returns



Returns TRUE if <i>fileObject</i> is associated with a point-of-service application. Otherwise, returns FALSE.



