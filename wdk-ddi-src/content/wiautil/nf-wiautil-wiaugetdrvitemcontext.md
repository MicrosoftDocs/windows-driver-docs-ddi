---
UID: NF:wiautil.wiauGetDrvItemContext
title: wiauGetDrvItemContext function
description: The wiauGetDrvItemContext function gets the driver item context, and optionally, the driver item.
old-location: image\wiaugetdrvitemcontext.htm
tech.root: image
ms.assetid: 6d4b7a25-436f-4547-8969-66dd45fa46fd
ms.date: 05/03/2018
ms.keywords: image.wiaugetdrvitemcontext, wiauFncs_3928edcb-8885-456a-a27d-62612fcb2d1a.xml, wiauGetDrvItemContext, wiauGetDrvItemContext function [Imaging Devices], wiautil/wiauGetDrvItemContext
ms.topic: function
req.header: wiautil.h
req.include-header: Wiautil.h
req.target-type: Desktop
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wiautil.h
api_name:
-	wiauGetDrvItemContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# wiauGetDrvItemContext function


## -description


The <b>wiauGetDrvItemContext</b> function gets the driver item context, and optionally, the driver item.


## -parameters




### -param pWiasContext [in]

Pointer to a WIA item context.


### -param ppItemCtx [in, out]

Pointer to a memory location that receives a pointer to the driver item context.


### -param ppDrvItem [in, out]

<i>Optional</i>. Pointer to a memory location that receives a pointer to a driver item. The default value of this parameter is <b>NULL</b>, which means that when this function returns, no change is made to this parameter.


## -returns



On success, the function returns S_OK. If the function fails, it returns a standard COM error.



