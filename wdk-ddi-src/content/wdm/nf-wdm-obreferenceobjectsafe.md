---
UID: NF:wdm.ObReferenceObjectSafe
title: ObReferenceObjectSafe function (wdm.h)
description: The ObReferenceObjectSafe function increments the reference count for an object and determines if it is safe to use the object. It returns FALSE if the object is being deleted or TRUE if it's safe to use the object further.
ms.assetid: a87d4714-9ecf-453c-a689-7eec6ac9ac10
ms.date: 10/19/2018
ms.topic: function
f1_keywords:
 - "wdm/ObReferenceObjectSafe"
ms.keywords: ObReferenceObjectSafe
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: "<= DISPATCH_LEVEL"
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- DllExport
api_location: 
- NtosKrnl.exe
api_name: 
- ObReferenceObjectSafe
product:
- Windows
targetos: Windows

ms.custom: RS5
---

# ObReferenceObjectSafe function


## -description

The ObReferenceObjectSafe function increments the reference count for an object and determines if it is safe to use the object. It returns FALSE if the object is being deleted or TRUE if it's safe to use the object further.

## -parameters

### -param Object
Supplies a pointer to the object whose reference count is incremented.

## -returns

ObReferenceObjectSafe returns one of the following values:

Return Value|Meaning
---|--
TRUE  |The object was successfuly referenced and safe to use.
FALSE |The object is being deleted.


## -remarks

## -see-also
- [ObReferenceObject](nf-wdm-obreferenceobject.md)
- [ObReferenceObjectWithTag](nf-wdm-obreferenceobjectwithtag.md)
- [ObReferenceObjectByPointerWithTag](nf-wdm-obreferenceobjectbypointerwithtag.md)
- [ObReferenceObjectByPointer](nf-wdm-obreferenceobjectbypointer.md)
