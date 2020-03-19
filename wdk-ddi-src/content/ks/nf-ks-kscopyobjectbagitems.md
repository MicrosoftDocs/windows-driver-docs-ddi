---
UID: NF:ks.KsCopyObjectBagItems
title: KsCopyObjectBagItems function (ks.h)
description: The KsCopyObjectBagItems function copies all items from one object bag into another.
old-location: stream\kscopyobjectbagitems.htm
tech.root: stream
ms.assetid: 5b3ee4f1-5c5a-413f-b927-96293cc87e98
ms.date: 04/23/2018
keywords: ["KsCopyObjectBagItems function"]
ms.keywords: KsCopyObjectBagItems, KsCopyObjectBagItems function [Streaming Media Devices], avfunc_26fe6218-6e9e-4a1a-93c6-f8f2ca10abbb.xml, ks/KsCopyObjectBagItems, stream.kscopyobjectbagitems
f1_keywords:
 - "ks/KsCopyObjectBagItems"
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
- KsCopyObjectBagItems
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsCopyObjectBagItems function


## -description


The<b> KsCopyObjectBagItems </b>function copies all items from one object bag into another.


## -parameters




### -param ObjectBagDestination [in]

The KSOBJECT_BAG (equivalent to type PVOID) into which to copy items.


### -param ObjectBagSource [in]

The KSOBJECT_BAG from which items are copied to <i>ObjectBagDestination.</i>


## -returns



Returns STATUS_SUCCESS if the copy is successful. Otherwise, it returns an error code. Most often, this is STATUS_INSUFFICIENT_RESOURCES indicating insufficient system resources to complete the copy operation. If STATUS_INSUFFICIENT_RESOURCES is returned, it is quite possible that some, but not all, of the items have been copied from <i>ObjectBagSource</i> to <i>ObjectBagDestination</i>.




## -remarks



Note that mutexes for both bags should be held. If the object bag in question is associated with a filter or a pin, acquire the filter control mutex. If the object bag belongs to a filter factory or the device, acquire the device mutex. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/object-bags">Object Bags</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/mutexes-in-avstream">Mutexes in AVStream</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksadditemtoobjectbag">KsAddItemToObjectBag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksallocateobjectbag">KsAllocateObjectBag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksdiscard">KsDiscard</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfreeobjectbag">KsFreeObjectBag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspingetconnectedfilterinterface">KsPinGetConnectedFilterInterface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspingetconnectedpininterface">KsPinGetConnectedPinInterface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspingetreferenceclockinterface">KsPinGetReferenceClockInterface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspinsetpinclocktime">KsPinSetPinClockTime</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksremoveitemfromobjectbag">KsRemoveItemFromObjectBag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-_ksedit">_KsEdit</a>
 

 

