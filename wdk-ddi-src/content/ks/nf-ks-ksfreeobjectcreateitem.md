---
UID: NF:ks.KsFreeObjectCreateItem
title: KsFreeObjectCreateItem function
author: windows-driver-content
description: Frees the slot for the specified create item.
old-location: stream\ksfreeobjectcreateitem.htm
old-project: stream
ms.assetid: 66f62a55-0bed-48ed-ae79-042bffe75b70
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: KsFreeObjectCreateItem, KsFreeObjectCreateItem function [Streaming Media Devices], ks/KsFreeObjectCreateItem, ksfunc_e91e49bc-521e-486e-a67b-33b16b7caa68.xml, stream.ksfreeobjectcreateitem
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsFreeObjectCreateItem
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsFreeObjectCreateItem function


## -description


Frees the slot for the specified create item.


## -parameters




### -param Header [in]

Points to the device header on which the create item is attached.


### -param CreateItem [in]

Contains the name of the create item to free.


## -returns



Returns STATUS_SUCCESS if the item was freed, else STATUS_OBJECT_NAME_NOT_FOUND.




## -remarks



This function does not assume that the caller is serializing multiple changes to the create entry list.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562564">KsFreeObjectCreateItemsByContext</a>
 

 

