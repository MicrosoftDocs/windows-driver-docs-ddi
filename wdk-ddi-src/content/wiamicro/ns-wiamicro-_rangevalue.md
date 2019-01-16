---
UID: NS:wiamicro._RANGEVALUE
title: "_RANGEVALUE"
description: The RANGEVALUE structure is used by a microdriver to communicate to the WIA Flatbed driver the legal values for a microdriver function parameter.
old-location: image\rangevalue.htm
tech.root: image
ms.assetid: 18322d1f-9fc9-43f0-925e-616731845792
ms.date: 05/03/2018
ms.keywords: "*PRANGEVALUE, MicroDrv_8569166c-7a4e-47eb-beed-57c715102258.xml, PRANGEVALUE, PRANGEVALUE structure pointer [Imaging Devices], RANGEVALUE, RANGEVALUE structure [Imaging Devices], _RANGEVALUE, image.rangevalue, wiamicro/PRANGEVALUE, wiamicro/RANGEVALUE"
ms.topic: struct
req.header: wiamicro.h
req.include-header: Wiamicro.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later versions of the Windows operating systems.
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
-	wiamicro.h
api_name:
-	RANGEVALUE
product:
- Windows
targetos: Windows
req.typenames: RANGEVALUE, *PRANGEVALUE
---

# _RANGEVALUE structure


## -description


The RANGEVALUE structure is used by a microdriver to communicate to the WIA Flatbed driver the legal values for a microdriver function parameter.


## -struct-fields




### -field lMin

Specifies the minimum value for a parameter.


### -field lMax

Specifies the maximum value for a parameter.


### -field lStep

Specifies the step value for a parameter.

