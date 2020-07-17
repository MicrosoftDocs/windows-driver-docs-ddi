---
UID: NC:ks.PFNREFERENCEDEVICEOBJECT
title: PFNREFERENCEDEVICEOBJECT (ks.h)
description: The driver can use this routine to increment the reference count of the PDO.
old-location: stream\kstrreferencedeviceobject.htm
tech.root: stream
ms.assetid: f4bf38eb-5028-4fcb-9752-8dab88db5904
ms.date: 04/23/2018
keywords: ["PFNREFERENCEDEVICEOBJECT callback function"]
ms.keywords: KStrReferenceDeviceObject, KStrReferenceDeviceObject routine [Streaming Media Devices], PFNREFERENCEDEVICEOBJECT, ks/KStrReferenceDeviceObject, ksfunc_721dd90e-6810-4f02-8454-dbacc872f90f.xml, stream.kstrreferencedeviceobject
f1_keywords:
 - "ks/KStrReferenceDeviceObject"
 - "KStrReferenceDeviceObject"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ks.h
api_name:
- KStrReferenceDeviceObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNREFERENCEDEVICEOBJECT callback function


## -description


The driver can use this routine to increment the reference count of the PDO.


## -parameters




### -param Context [in]

Pointer to a device extension of the device's PDO.


## -remarks



The driver can access this method through the <b>ReferenceDeviceObject</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-bus_interface_reference">BUS_INTERFACE_REFERENCE</a> structure.

The device object remains active and enumerated until the reference count returns to 0.



