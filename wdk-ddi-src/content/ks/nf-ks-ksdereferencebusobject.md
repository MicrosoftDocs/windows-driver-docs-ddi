---
UID: NF:ks.KsDereferenceBusObject
title: KsDereferenceBusObject function
author: windows-driver-content
description: Dereferences the bus Physical Device Object.
old-location: stream\ksdereferencebusobject.htm
old-project: stream
ms.assetid: 5520685c-c438-460b-aac5-791098e14044
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsDereferenceBusObject function [Streaming Media Devices], stream.ksdereferencebusobject, ks/KsDereferenceBusObject, KsDereferenceBusObject, ksfunc_e3b1ab42-bb78-44f7-bc34-64edcf843471.xml
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
-	KsDereferenceBusObject
product: Windows
targetos: Windows
req.typenames: 
---

# KsDereferenceBusObject function


## -description


Dereferences the bus Physical Device Object.


## -syntax


````
VOID KsDereferenceBusObject(
  _In_ KSDEVICE_HEADER Header
);
````


## -parameters




### -param Header [in]

Points to a header previously allocated by <b>KsAllocateDeviceHeader</b> that also contains the PnP device stack object.


## -returns


None.



## -remarks


This is used by filters that use the device header to keep track of the corresponding PnP object stack. This is normally called when closing a filter, if required by the bus for the given device. As an example, a software device would require such a call. This call matches a previous call to <a href="..\ks\nf-ks-ksreferencebusobject.md">KsReferenceBusObject</a> when opening the filter instance. The caller must have previously also called <b>KsSetDevicePnpAndBaseObject</b> in order to set the PnP device stack object. This would have been done in the PnP <b>AddDevice</b> function. The function calls the <b>DereferenceDeviceObject</b> method on the previously retrieved interface. The interface itself is released and freed when the device header is freed.


