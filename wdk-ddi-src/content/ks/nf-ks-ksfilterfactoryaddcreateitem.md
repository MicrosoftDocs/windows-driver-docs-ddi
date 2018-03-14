---
UID: NF:ks.KsFilterFactoryAddCreateItem
title: KsFilterFactoryAddCreateItem function
author: windows-driver-content
description: The KsFilterFactoryAddCreateItem function adds a new create item for the specified filter factory.
old-location: stream\ksfilterfactoryaddcreateitem.htm
old-project: stream
ms.assetid: c09840fb-8195-4ac5-a164-ba4d82615344
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsFilterFactoryAddCreateItem, KsFilterFactoryAddCreateItem function [Streaming Media Devices], avfunc_f4a42084-1d8f-49f8-a6d3-d09304e11049.xml, ks/KsFilterFactoryAddCreateItem, stream.ksfilterfactoryaddcreateitem
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
-	KsFilterFactoryAddCreateItem
product: Windows
targetos: Windows
req.typenames: 
---

# KsFilterFactoryAddCreateItem function


## -description


The<b> KsFilterFactoryAddCreateItem</b> function adds a new create item for the specified filter factory.


## -syntax


````
NTSTATUS KsFilterFactoryAddCreateItem(
  _In_     PKSFILTERFACTORY     FilterFactory,
  _In_     PWSTR                RefString,
  _In_opt_ PSECURITY_DESCRIPTOR SecurityDescriptor,
  _In_     ULONG                CreateItemFlags
);
````


## -parameters




### -param FilterFactory [in]

A pointer to a <a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a> structure representing the filter factory to which to add a new create item.


### -param RefString [in]

A pointer to a Unicode text string that identifies the create item.


### -param SecurityDescriptor [in, optional]

This parameter optionally contains a pointer to a SECURITY_DESCRIPTOR structure for this type of object. See the Microsoft Windows SDK For information about this structure. For related information, see <a href="..\ks\ns-ks-ksobject_create_item.md">KSOBJECT_CREATE_ITEM</a>. If <b>NULL</b>, no descriptor is assigned.


### -param CreateItemFlags [in]

See the table for the <b>Flags</b> member of <a href="..\ks\ns-ks-ksobject_create_item.md">KSOBJECT_CREATE_ITEM</a>.


## -returns



<b>KsFilterFactoryAddCreateItem</b> returns success or failure of the attempt to add a new create item.




## -remarks



Normally, only a single create item using the reference GUID supplied in the filter descriptor is added for the filter factory. This function allows the caller to add create items associated with the given filter factory.

For more information, see <a href="https://msdn.microsoft.com/666d6efb-93ec-43f3-87c5-ea1a3983bfd0">Initializing an AVStream Minidriver</a>. 




## -see-also

<a href="..\ks\nf-ks-ksaddobjectcreateitemtoobjectheader.md">KsAddObjectCreateItemToObjectHeader</a>



<a href="..\ks\nf-ks-ksfreeobjectcreateitem.md">KsFreeObjectCreateItem</a>



<a href="..\ks\nf-ks-ksqueryobjectcreateitem.md">KsQueryObjectCreateItem</a>



<a href="..\ks\nf-ks-ksaddobjectcreateitemtodeviceheader.md">KsAddObjectCreateItemToDeviceHeader</a>



<a href="..\ks\ns-ks-ksobject_create_item.md">KSOBJECT_CREATE_ITEM</a>



<a href="..\ks\nf-ks-ksallocateobjectcreateitem.md">KsAllocateObjectCreateItem</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFilterFactoryAddCreateItem function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

