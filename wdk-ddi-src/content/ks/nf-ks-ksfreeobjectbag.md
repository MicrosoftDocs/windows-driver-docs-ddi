---
UID: NF:ks.KsFreeObjectBag
title: KsFreeObjectBag function
author: windows-driver-content
description: The KsFreeObjectBag function empties and frees an object bag.
old-location: stream\ksfreeobjectbag.htm
old-project: stream
ms.assetid: d0bc4e8b-b173-4568-8c0f-7b87fd84e2cf
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: avfunc_f91aca67-5d6c-42f7-9e24-3b15b54c2b69.xml, KsFreeObjectBag function [Streaming Media Devices], ks/KsFreeObjectBag, stream.ksfreeobjectbag, KsFreeObjectBag
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsFreeObjectBag
product: Windows
targetos: Windows
req.typenames: 
---

# KsFreeObjectBag function


## -description


The<b> KsFreeObjectBag</b> function empties and frees an object bag.


## -syntax


````
void KsFreeObjectBag(
  _In_ KSOBJECT_BAG ObjectBag
);
````


## -parameters




### -param ObjectBag [in]

The KSOBJECT_BAG (equivalent to type PVOID) to be emptied and then freed.


## -returns


None



## -remarks


For more information, see <a href="https://msdn.microsoft.com/b7ee5756-1c79-4ead-9999-d13be9a0d3d9">Object Bags</a>.

<b>KsFreeObjectBag</b> removes any items present in <i>ObjectBag</i>. In addition, if the reference count for a given object is zero (that is, the object is not present in any other object bag associated with the same device as <i>ObjectBag</i>), then that item is freed. 



## -see-also

<a href="..\ks\nf-ks-ksadditemtoobjectbag.md">KsAddItemToObjectBag</a>

<a href="..\ks\nf-ks-kscopyobjectbagitems.md">KsCopyObjectBagItems</a>

<a href="..\ks\nf-ks-ksremoveitemfromobjectbag.md">KsRemoveItemFromObjectBag</a>

<a href="..\ks\nf-ks-ksallocateobjectbag.md">KsAllocateObjectBag</a>

<a href="..\ks\nf-ks-ksdiscard.md">KsDiscard</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFreeObjectBag function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

