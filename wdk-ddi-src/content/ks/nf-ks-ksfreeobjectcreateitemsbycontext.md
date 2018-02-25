---
UID: NF:ks.KsFreeObjectCreateItemsByContext
title: KsFreeObjectCreateItemsByContext function
author: windows-driver-content
description: Frees all create items with a specific context.
old-location: stream\ksfreeobjectcreateitemsbycontext.htm
old-project: stream
ms.assetid: 70c2942d-1225-4a50-b734-27995b4481d1
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , B, C, F, I, K, KsFreeObjectCreateItemsByContext, KsFreeObjectCreateItemsByContext function [Streaming Media Devices], O, a, b, c, e, j, ks/KsFreeObjectCreateItemsByContext, ksfunc_0ad51072-eff4-4be3-95f4-b54c9267a4a9.xml, m, n, o, r, s, stream.ksfreeobjectcreateitemsbycontext, t, x, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsFreeObjectCreateItemsByContext
product: Windows
targetos: Windows
req.typenames: 
---

# KsFreeObjectCreateItemsByContext function


## -description


Frees all create items with a specific context.


## -syntax


````
NTSTATUS KsFreeObjectCreateItemsByContext(
  _In_ KSDEVICE_HEADER Header,
  _In_ PVOID           Context
);
````


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

<a href="..\ks\nf-ks-ksfreeobjectcreateitem.md">KsFreeObjectCreateItem</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFreeObjectCreateItemsByContext function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

