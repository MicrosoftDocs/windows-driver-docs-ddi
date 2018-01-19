---
UID: NE:wdftypes._WDF_TRI_STATE
title: _WDF_TRI_STATE
author: windows-driver-content
description: The WDF_TRI_STATE enumeration type defines three values that the framework uses for some structure members and function parameters.
old-location: wdf\wdf_tri_state.htm
old-project: wdf
ms.assetid: 8ea6e373-225d-4fcd-abcf-c19b07f9f5d8
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WDF_TRI_STATE, WDF_TRI_STATE, *PWDF_TRI_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdftypes.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 1.11
req.alt-api: WDF_TRI_STATE
req.alt-loc: wdftypes.h,wudfddi_types.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
req.typenames: WDF_TRI_STATE, *PWDF_TRI_STATE
req.product: Windows 10 or later.
---

# _WDF_TRI_STATE enumeration



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The WDF_TRI_STATE enumeration type defines three values that the framework uses for some structure members and function parameters.



## -syntax

````
typedef enum _WDF_TRI_STATE { 
  WdfFalse       = FALSE,
  WdfTrue        = TRUE,
  WdfUseDefault  = 2
} WDF_TRI_STATE, *PWDF_TRI_STATE;
````


## -enum-fields

### -field WdfFalse

The meaning of this enumerator is specific to its use as a structure member or function parameter.


### -field WdfTrue

The meaning of this enumerator is specific to its use as a structure member or function parameter.


### -field WdfUseDefault

The meaning of this enumerator is specific to its use as a structure member or function parameter.


## -remarks
The WDF_TRI_STATE enumeration type is available in version 1.0 and later versions of KMDF.</p>