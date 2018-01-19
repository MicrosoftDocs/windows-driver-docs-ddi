---
UID: NC:ks.PFNDEREFERENCEDEVICEOBJECT
title: PFNDEREFERENCEDEVICEOBJECT
author: windows-driver-content
description: The driver can use this routine to decrement the reference count of the PDO.
old-location: stream\kstrdereferencedeviceobject.htm
old-project: stream
ms.assetid: 8d220b69-122c-4019-9c70-4c744503481d
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: NpdBrokerUninitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KStrDereferenceDeviceObject
req.alt-loc: ks.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: KEYWORDSELECTOR
---

# PFNDEREFERENCEDEVICEOBJECT callback



## -description
The driver can use this routine to decrement the reference count of the PDO.



## -prototype

````
PFNDEREFERENCEDEVICEOBJECT KStrDereferenceDeviceObject;

VOID KStrDereferenceDeviceObject(
  _In_ PVOID Context
)
{ ... }
````


## -parameters

### -param Context [in]

Pointer to a device extension of the device's PDO.


## -returns
Returns STATUS_SUCCESS if the request is handled. Otherwise returns an appropriate error code.


## -remarks
Minidrivers access this method through the <b>DereferenceDeviceObject</b> member of the <a href="..\ks\ns-ks-bus_interface_reference.md">BUS_INTERFACE_REFERENCE</a> structure.

When the PDO's reference count is 0, it becomes eligible for removal. Note that this condition does not guarantee removal.</p>