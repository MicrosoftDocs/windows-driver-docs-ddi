---
UID: NC:ks.PFNREFERENCEDEVICEOBJECT
title: PFNREFERENCEDEVICEOBJECT
author: windows-driver-content
description: The driver can use this routine to increment the reference count of the PDO.
old-location: stream\kstrreferencedeviceobject.htm
old-project: stream
ms.assetid: f4bf38eb-5028-4fcb-9752-8dab88db5904
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: stream.kstrreferencedeviceobject, KStrReferenceDeviceObject routine [Streaming Media Devices], KStrReferenceDeviceObject, PFNREFERENCEDEVICEOBJECT, PFNREFERENCEDEVICEOBJECT, ks/KStrReferenceDeviceObject, ksfunc_721dd90e-6810-4f02-8454-dbacc872f90f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h, Swenum.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ks.h
apiname:
-	KStrReferenceDeviceObject
product: Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---

# PFNREFERENCEDEVICEOBJECT callback


## -description


The driver can use this routine to increment the reference count of the PDO.


## -prototype


````
PFNREFERENCEDEVICEOBJECT KStrReferenceDeviceObject;

VOID KStrReferenceDeviceObject(
  _In_ PVOID Context
)
{ ... }
````


## -parameters




### -param Context [in]

Pointer to a device extension of the device's PDO.


## -returns



None.




## -remarks



The driver can access this method through the <b>ReferenceDeviceObject</b> member of the <a href="..\ks\ns-ks-bus_interface_reference.md">BUS_INTERFACE_REFERENCE</a> structure.

The device object remains active and enumerated until the reference count returns to 0.



