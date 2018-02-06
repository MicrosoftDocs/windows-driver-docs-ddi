---
UID: NF:ks.KsRemoveItemFromObjectBag
title: KsRemoveItemFromObjectBag function
author: windows-driver-content
description: The KsRemoveItemFromObjectBag function removes an item from an object bag.
old-location: stream\ksremoveitemfromobjectbag.htm
old-project: stream
ms.assetid: 8644b5eb-e038-4cdb-b461-d643ff929736
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsRemoveItemFromObjectBag function [Streaming Media Devices], KsRemoveItemFromObjectBag, avfunc_dbc6f0e3-7e24-4147-99d2-28e64a6a1ff9.xml, ks/KsRemoveItemFromObjectBag, stream.ksremoveitemfromobjectbag
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
-	KsRemoveItemFromObjectBag
product: Windows
targetos: Windows
req.typenames: 
---

# KsRemoveItemFromObjectBag function


## -description


The<b> KsRemoveItemFromObjectBag </b>function removes an item from an object bag.


## -syntax


````
ULONG KsRemoveItemFromObjectBag(
  _In_ KSOBJECT_BAG ObjectBag,
  _In_ PVOID        Item,
  _In_ BOOLEAN      Free
);
````


## -parameters




### -param ObjectBag [in]

This parameter specifies the KSOBJECT_BAG (equivalent to type PVOID) from which to remove <i>Item</i>. 


### -param Item [in]

A pointer to the item to remove from the requested object bag. Note that <i>Item</i> is removed from the requested object bag only. It is not removed from any other object bags that it may be in.


### -param Free [in]

This parameter specifies whether <i>Item</i> should be freed once it has been removed from the specified object bag. Only set <i>Free</i> to <b>TRUE</b> if <i>Item</i> is not contained in any other object bag.


## -returns


Returns the number of references on <i>Item</i>. A return value of zero indicates that <i>Item</i> was not in <i>ObjectBag</i> at call-time.

A return value of one indicates that <i>Item</i> was successfully removed from <i>ObjectBag</i> and that it was not in any other object bag. If a free was requested in this case, AVStream frees <i>Item</i> using either <b>ExFreePool</b> or the Free method specified at <b>KsAddItemToObjectBag</b> call-time.



A return value above one indicates that the item is present in another object bag and that there are still references on it. In this case, AVStream removed Item from <i>ObjectBag</i>, but did not free it regardless of the value of <i>Free</i>.





## -remarks


<b>KsRemoveItemFromObjectBag</b> frees <i>Item</i> only if the number of references on this item is zero and a free was requested. 

For more information about object bags, see <a href="https://msdn.microsoft.com/b7ee5756-1c79-4ead-9999-d13be9a0d3d9">Object Bags</a>.

Note that the mutex associated with the bag must be held. For more  information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.



## -see-also

<a href="..\ks\nf-ks-ksadditemtoobjectbag.md">KsAddItemToObjectBag</a>

<a href="..\ks\nf-ks-ksfreeobjectbag.md">KsFreeObjectBag</a>

<a href="..\ks\nf-ks-kscopyobjectbagitems.md">KsCopyObjectBagItems</a>

<a href="..\ks\nf-ks-ksallocateobjectbag.md">KsAllocateObjectBag</a>

<a href="..\ks\nf-ks-ksdiscard.md">KsDiscard</a>

<a href="..\ks\nf-ks-ksmergeautomationtables.md">KsMergeAutomationTables</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsRemoveItemFromObjectBag function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

