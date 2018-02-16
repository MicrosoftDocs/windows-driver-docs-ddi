---
UID: NF:ks.KsPropertyHandler
title: KsPropertyHandler function
author: windows-driver-content
description: Drivers call KsPropertyHandler function for IRP handling.
old-location: stream\kspropertyhandler.htm
old-project: stream
ms.assetid: af94f36f-6e1a-4ac5-be6d-64a9a8dade9e
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsPropertyHandler function [Streaming Media Devices], stream.kspropertyhandler, KsPropertyHandler, ksfunc_9595b49a-6957-4ebc-8d45-3a92f9190734.xml, ks/KsPropertyHandler
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
-	KsPropertyHandler
product: Windows
targetos: Windows
req.typenames: 
---

# KsPropertyHandler function


## -description


Drivers call <b>KsPropertyHandler</b> function for IRP handling.


## -syntax


````
NTSTATUS KsPropertyHandler(
  _In_       PIRP           Irp,
  _In_       ULONG          PropertySetsCount,
  _In_ const KSPROPERTY_SET *PropertySet
);
````


## -parameters




### -param Irp [in]

Specifies the IRP with the property request being handled.


### -param PropertySetsCount [in]

Specifies the number of property sets being passed.


### -param PropertySet [in]

Points to an array of <a href="..\ks\ns-ks-ksproperty_set.md">KSPROPERTY_SET</a> structures. The driver should provide one structure for each property set it wants KsPropertyHandler to handle.


## -returns



The <b>KsPropertyHandler </b>function returns STATUS_SUCCESS if successful, or an error specific to the property being handled if unsuccessful. The function sets the <a href="..\wdm\ns-wdm-_irp.md">IRP</a>-&gt;<a href="..\wdm\ns-wdm-_io_status_block.md">IO_STATUS_BLOCK</a>.Information member, either through setting it to zero because of an internal error, or through a property handler setting it. The function does not set the lrp-&gt;IoStatus.Status member nor does it complete the IRP.




## -remarks



<b>KsPropertyHandler</b> responds to all property identifiers defined by the sets, and can only be called at PASSIVE_LEVEL.

Each <a href="..\ks\ns-ks-ksproperty_set.md">KSPROPERTY_SET</a> entry contains a pointer to an array of <a href="..\ks\ns-ks-ksproperty_item.md">KSPROPERTY_ITEM</a> structures in its PropertyItem member. For driver-specific processing, KsPropertyHandler hands off each request to one of the driver-supplied callbacks within PropertyItem. KsPropertyHandler takes care of any IRP processing required.

KsPropertyHandler does not use the FastIoTable member of its <a href="..\ks\ns-ks-ksproperty_set.md">KSPROPERTY_SET</a> structure. If the driver needs to support Fast I/O handling of requests, the same KSPROPERTY_SET structure should be passed to the KsFastPropertyHandler routine.

The owner of the property sets can perform prefiltering or postfiltering of property handling. Basic property structure access exceptions are handled by the <b>KsPropertyHandler </b>function, though cleanup for specific exceptions must be covered by the property handler.

<b>KsPropertyHandler</b> places a pointer to the relevant KSPROPERTY_SET structure in the <b>Irp-&gt;Tail.Overlay.DriverContext</b> parameter in the IRP. The minidriver can use the KSPROPERTY_SET_IRP_STORAGE macro, defined in <i>ks.h</i>, to access this pointer.




## -see-also

<a href="..\ks\nf-ks-kspropertyhandlerwithallocator.md">KsPropertyHandlerWithAllocator</a>



<a href="..\ks\nf-ks-ksfastpropertyhandler.md">KsFastPropertyHandler</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPropertyHandler function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

