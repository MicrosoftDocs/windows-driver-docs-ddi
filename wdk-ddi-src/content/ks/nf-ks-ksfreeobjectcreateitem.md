---
UID: NF:ks.KsFreeObjectCreateItem
title: KsFreeObjectCreateItem function
author: windows-driver-content
description: Frees the slot for the specified create item.
old-location: stream\ksfreeobjectcreateitem.htm
old-project: stream
ms.assetid: 66f62a55-0bed-48ed-ae79-042bffe75b70
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsFreeObjectCreateItem, stream.ksfreeobjectcreateitem, ksfunc_e91e49bc-521e-486e-a67b-33b16b7caa68.xml, KsFreeObjectCreateItem function [Streaming Media Devices], ks/KsFreeObjectCreateItem
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
-	KsFreeObjectCreateItem
product: Windows
targetos: Windows
req.typenames: 
---

# KsFreeObjectCreateItem function


## -description


Frees the slot for the specified create item.


## -syntax


````
NTSTATUS KsFreeObjectCreateItem(
  _In_ KSDEVICE_HEADER Header,
  _In_ PUNICODE_STRING CreateItem
);
````


## -parameters




#### - Header [in]

Points to the device header on which the create item is attached.


#### - CreateItem [in]

Contains the name of the create item to free.


## -returns


Returns STATUS_SUCCESS if the item was freed, else STATUS_OBJECT_NAME_NOT_FOUND.



## -remarks


This function does not assume that the caller is serializing multiple changes to the create entry list.



## -see-also

<a href="..\ks\nf-ks-ksfreeobjectcreateitemsbycontext.md">KsFreeObjectCreateItemsByContext</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFreeObjectCreateItem function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

