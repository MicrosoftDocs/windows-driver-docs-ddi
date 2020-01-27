---
UID: NF:ks.KsFreeObjectCreateItemsByContext
title: KsFreeObjectCreateItemsByContext function (ks.h)
description: Frees all create items with a specific context.
old-location: stream\ksfreeobjectcreateitemsbycontext.htm
tech.root: stream
ms.assetid: 70c2942d-1225-4a50-b734-27995b4481d1
ms.date: 04/23/2018
ms.keywords: KsFreeObjectCreateItemsByContext, KsFreeObjectCreateItemsByContext function [Streaming Media Devices], ks/KsFreeObjectCreateItemsByContext, ksfunc_0ad51072-eff4-4be3-95f4-b54c9267a4a9.xml, stream.ksfreeobjectcreateitemsbycontext
f1_keywords:
 - "ks/KsFreeObjectCreateItemsByContext"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsFreeObjectCreateItemsByContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsFreeObjectCreateItemsByContext function


## -description


Frees all create items with a specific context.


## -parameters




### -param Header [in]

Points to the device header on which the create items are attached.


### -param Context [in]

Contains the context of the create items to free. All create items with this context value will be freed.


## -returns



Returns STATUS_SUCCESS if the item was freed, else STATUS_OBJECT_NAME_NOT_FOUND.




## -remarks



Instead of freeing create items by name as <b>KsFreeObjectCreateItems</b> does, this function will free all create items with a specific context.  For example, all create items associated with a filter factory will have the factory as context and can be freed simultaneously with this call instead of one at a time. Note that this function does not assume that the caller is serializing multiple changes to the create entry list.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfreeobjectcreateitem">KsFreeObjectCreateItem</a>
 

 

