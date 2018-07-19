---
UID: NF:dbgmodel.BindReadOnlyProperty~r1
title: BindReadOnlyProperty function
author: windows-driver-content
description: TBD
ms.assetid: c59ee365-d2da-4352-8311-a4a1d27fabdc
ms.author: windowsdriverdev
ms.date: 
ms.topic: function
ms.keywords: BindReadOnlyProperty
req.header: dbgmodel.h
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
-	
api_location: 
-	
api_name: 
-	BindReadOnlyProperty
product: Windows
targetos: Windows


---

# BindReadOnlyProperty function


## -description

A binder which converts one instance method on a class to a read-only property accessor.  The class must be IUnknown derived.

The returned binder will hold reference on the class object.

A binder which converts one lambda to a read-only property accessor.  The lambda must hold reference on outer objects through  a by value capture.

Usage: BindProperty(get_lambda)

## -parameters

### -param getFunctor
TBD

### -param 
TBD

## -returns
This function returns Microsoft::WRL::ComPtr<IModelPropertyAccessor>.
## -remarks

## -see-also