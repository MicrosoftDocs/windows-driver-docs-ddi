---
UID: NF:ks.KsFreeObjectBag
title: KsFreeObjectBag function (ks.h)
description: The KsFreeObjectBag function empties and frees an object bag.
old-location: stream\ksfreeobjectbag.htm
tech.root: stream
ms.assetid: d0bc4e8b-b173-4568-8c0f-7b87fd84e2cf
ms.date: 04/23/2018
keywords: ["KsFreeObjectBag function"]
ms.keywords: KsFreeObjectBag, KsFreeObjectBag function [Streaming Media Devices], avfunc_f91aca67-5d6c-42f7-9e24-3b15b54c2b69.xml, ks/KsFreeObjectBag, stream.ksfreeobjectbag
f1_keywords:
 - "ks/KsFreeObjectBag"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsFreeObjectBag
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsFreeObjectBag function


## -description


The<b> KsFreeObjectBag</b> function empties and frees an object bag.


## -parameters




### -param ObjectBag [in]

The KSOBJECT_BAG (equivalent to type PVOID) to be emptied and then freed.


## -remarks



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/object-bags">Object Bags</a>.

<b>KsFreeObjectBag</b> removes any items present in <i>ObjectBag</i>. In addition, if the reference count for a given object is zero (that is, the object is not present in any other object bag associated with the same device as <i>ObjectBag</i>), then that item is freed. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksadditemtoobjectbag">KsAddItemToObjectBag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksallocateobjectbag">KsAllocateObjectBag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kscopyobjectbagitems">KsCopyObjectBagItems</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksdiscard">KsDiscard</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksremoveitemfromobjectbag">KsRemoveItemFromObjectBag</a>
 

 

