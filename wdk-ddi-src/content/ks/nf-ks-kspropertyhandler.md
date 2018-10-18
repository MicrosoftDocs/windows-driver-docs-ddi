---
UID: NF:ks.KsPropertyHandler
title: KsPropertyHandler function
author: windows-driver-content
description: Drivers call KsPropertyHandler function for IRP handling.
old-location: stream\kspropertyhandler.htm
tech.root: stream
ms.assetid: af94f36f-6e1a-4ac5-be6d-64a9a8dade9e
ms.date: 04/23/2018
ms.keywords: KsPropertyHandler, KsPropertyHandler function [Streaming Media Devices], ks/KsPropertyHandler, ksfunc_9595b49a-6957-4ebc-8d45-3a92f9190734.xml, stream.kspropertyhandler
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
-	KsPropertyHandler
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsPropertyHandler function


## -description


Drivers call <b>KsPropertyHandler</b> function for IRP handling.


## -parameters




### -param Irp [in]

Specifies the IRP with the property request being handled.


### -param PropertySetsCount [in]

Specifies the number of property sets being passed.


### -param PropertySet [in]

Points to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff565617">KSPROPERTY_SET</a> structures. The driver should provide one structure for each property set it wants KsPropertyHandler to handle.


## -returns



The <b>KsPropertyHandler </b>function returns STATUS_SUCCESS if successful, or an error specific to the property being handled if unsuccessful. The function sets the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a>-&gt;<a href="https://msdn.microsoft.com/library/windows/hardware/ff550671">IO_STATUS_BLOCK</a>.Information member, either through setting it to zero because of an internal error, or through a property handler setting it. The function does not set the lrp-&gt;IoStatus.Status member nor does it complete the IRP.




## -remarks



<b>KsPropertyHandler</b> responds to all property identifiers defined by the sets, and can only be called at PASSIVE_LEVEL.

Each <a href="https://msdn.microsoft.com/library/windows/hardware/ff565617">KSPROPERTY_SET</a> entry contains a pointer to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff565176">KSPROPERTY_ITEM</a> structures in its PropertyItem member. For driver-specific processing, KsPropertyHandler hands off each request to one of the driver-supplied callbacks within PropertyItem. KsPropertyHandler takes care of any IRP processing required.

KsPropertyHandler does not use the FastIoTable member of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff565617">KSPROPERTY_SET</a> structure. If the driver needs to support Fast I/O handling of requests, the same KSPROPERTY_SET structure should be passed to the KsFastPropertyHandler routine.

The owner of the property sets can perform prefiltering or postfiltering of property handling. Basic property structure access exceptions are handled by the <b>KsPropertyHandler </b>function, though cleanup for specific exceptions must be covered by the property handler.

<b>KsPropertyHandler</b> places a pointer to the relevant KSPROPERTY_SET structure in the <b>Irp-&gt;Tail.Overlay.DriverContext</b> parameter in the IRP. The minidriver can use the KSPROPERTY_SET_IRP_STORAGE macro, defined in <i>ks.h</i>, to access this pointer.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561946">KsFastPropertyHandler</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564264">KsPropertyHandlerWithAllocator</a>
 

 

