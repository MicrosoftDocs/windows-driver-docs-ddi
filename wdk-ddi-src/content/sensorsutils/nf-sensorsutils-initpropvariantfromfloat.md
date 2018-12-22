---
UID: NF:sensorsutils.InitPropVariantFromFloat
title: InitPropVariantFromFloat function
description: This routine initializes a PROPVARIANT with the given float.
ms.assetid: 585790f6-563a-41a6-a500-01d1cfac6a78
ms.date: 08/08/2018
tech.root: sensors
ms.topic: function
ms.keywords: InitPropVariantFromFloat
req.header: sensorsutils.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	LibDef
api_location: 
-	sensorsutils.h
api_name: 
-	InitPropVariantFromFloat
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# InitPropVariantFromFloat function


## -description

This routine initializes a PROPVARIANT with the given float.



## -parameters

### -param fltVal

[in] Float value to initialize to.

### -param ppropvar

[out] Pointer to a PROPVARIANT to be initialized.

## -returns

This function returns S_OK if the PROPVARIANT was properly initialized, and E_FAIL if *ppropvar* is null.

## -remarks

## -see-also
