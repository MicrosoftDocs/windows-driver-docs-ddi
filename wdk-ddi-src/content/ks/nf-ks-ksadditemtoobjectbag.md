---
UID: NF:ks.KsAddItemToObjectBag
title: KsAddItemToObjectBag function
author: windows-driver-content
description: The KsAddItemToObjectBag function adds an object or block of memory to the given object bag.
old-location: stream\ksadditemtoobjectbag.htm
old-project: stream
ms.assetid: 4c8b6252-8438-4cd1-81e0-02c260da0daf
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsAddItemToObjectBag, KsAddItemToObjectBag function [Streaming Media Devices], avfunc_c7496331-05a5-4336-9c62-144e2db6e218.xml, ks/KsAddItemToObjectBag, stream.ksadditemtoobjectbag
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsAddItemToObjectBag
product: Windows
targetos: Windows
req.typenames: 
---

# KsAddItemToObjectBag function


## -description


The<b> KsAddItemToObjectBag</b> function adds an object or block of memory to the given object bag. 


## -syntax


````
NTSTATUS KsAddItemToObjectBag(
  _In_     KSOBJECT_BAG ObjectBag,
  _In_     PVOID        Item,
  _In_opt_ PFNKSFREE    Free
);
````


## -parameters




### -param ObjectBag [in]

The KSOBJECT_BAG (equivalent to type PVOID) to which to add the requested item. Every AVStream object (for example, <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> and <a href="..\ks\ns-ks-_kspin.md">KSPIN</a>) contains a member called <i>Bag</i>. Pass that member in this parameter.


### -param Item [in]

A pointer to the item to add to the object bag.


### -param Free [in, optional]

A function that is called when the item is removed from the object bag or when the object bag is deleted. This function typically is used to free any dynamic memory associated with <i>Item</i>. The function should be prototyped as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>void Free (IN PVOID Data);</pre>
</td>
</tr>
</table></span></div>
If the caller does not specify this optional parameter, <i>Item</i> is freed with <a href="..\wdm\nf-wdm-exfreepool.md">ExFreePool</a> when removed from the object bag or when the object bag is deleted.


## -returns



Either returns STATUS_SUCCESS indicating that the addition went normally or STATUS_INSUFFICIENT_RESOURCES indicating that there are insufficient system resources for the operation to proceed.




## -remarks



Before calling <b>KsAddItemToObjectBag</b>, the minidriver must acquire the mutex associated with the specific object bag. If <i>ObjectBag</i> is a member of a <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a> or <a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a>, acquire the device mutex. If the bag is a member of a <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a>, acquire the filter control mutex. If the bag is a member of a <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> object, acquire the parent KSFILTER's filter control mutex.

For more information, see <a href="https://msdn.microsoft.com/b7ee5756-1c79-4ead-9999-d13be9a0d3d9">Object Bags</a> and <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.




## -see-also

<a href="..\ks\nf-ks-ksallocateobjectbag.md">KsAllocateObjectBag</a>



<a href="..\ks\nf-ks-ksfreeobjectbag.md">KsFreeObjectBag</a>



<a href="..\wdm\nf-wdm-exfreepool.md">ExFreePool</a>



<a href="..\ks\nf-ks-_ksedit.md">_KsEdit</a>



<a href="..\ks\nf-ks-kscopyobjectbagitems.md">KsCopyObjectBagItems</a>



<a href="..\ks\nf-ks-ksremoveitemfromobjectbag.md">KsRemoveItemFromObjectBag</a>



<a href="..\ks\nf-ks-ksdiscard.md">KsDiscard</a>



 

 


