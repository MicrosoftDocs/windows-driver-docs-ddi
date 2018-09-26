---
UID: NC:d3dumddi.PFND3DDDI_QUERYDLISTFORAPPLICATION
title: PFND3DDDI_QUERYDLISTFORAPPLICATION
author: windows-driver-content
description: The PFND3DDDI_QUERYDLISTFORAPPLICATION callback function queries a DList for an application.
ms.assetid: 9debfb9c-534e-4342-8c36-64f403d03756
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3dumddi.h
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
-	UserDefined
api_location: 
-	d3dumddi.h
api_name: 
-	PFND3DDDI_QUERYDLISTFORAPPLICATION
product:
-	Windows
targetos: Windows
---

# PFND3DDDI_QUERYDLISTFORAPPLICATION callback function

## -description

The PFND3DDDI_QUERYDLISTFORAPPLICATION callback function queries a DList for an application.

## -prototype

```
//Declaration

PFND3DDDI_QUERYDLISTFORAPPLICATION Pfnd3dddiQuerydlistforapplication; 

// Definition

HRESULT Pfnd3dddiQuerydlistforapplication 
(
	BOOL *
)
{...}

```

## -parameters

### -param *

[out] Indicates whether or not there is an application in the DList.

## -returns

Returns HRESULT.