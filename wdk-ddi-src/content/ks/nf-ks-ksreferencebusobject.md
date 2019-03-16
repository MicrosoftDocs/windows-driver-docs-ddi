---
UID: NF:ks.KsReferenceBusObject
title: KsReferenceBusObject function (ks.h)
description: References the bus Physical device object.
old-location: stream\ksreferencebusobject.htm
tech.root: stream
ms.assetid: 96297c0a-a3ba-4f16-befb-ee6a55d2fb25
ms.date: 04/23/2018
ms.keywords: KsReferenceBusObject, KsReferenceBusObject function [Streaming Media Devices], ks/KsReferenceBusObject, ksfunc_35e7b40f-3acf-4e86-8594-3c50912dca42.xml, stream.ksreferencebusobject
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsReferenceBusObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsReferenceBusObject function


## -description


References the bus Physical device object.


## -parameters




### -param Header [in]

Points to a header previously allocated by <b>KsAllocateDeviceHeader</b> that also contains the PnP device stack object.


## -returns



Returns STATUS_SUCCESS if the reference was successful, else an error such as STATUS_INSUFFICIENT_RESOURCES.




## -remarks



This function is used by filters that use the device header to keep track of their PnP object stack. This is normally called on a successful Open of the filter when the bus for this device requires such a reference (such as software devices), and is matched by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff561676">KsDereferenceBusObject</a> on a close of that filter instance. The caller must have previously also called KsSetDevicePnpAndBaseObject in order to set the PnP device stack object. This would have been done in the PnP AddDevice function. If the object has not been previously referenced, interface space is allocated and the function uses the PnP device object to acquire the bus referencing interface. It then calls the ReferenceDeviceObject method on that interface. The interface itself is released and freed when the device header is freed.



