---
UID: NF:portcls.IPortWMIRegistration.RegisterWMIProvider
title: IPortWMIRegistration::RegisterWMIProvider (portcls.h)
description: The RegisterWMIProvider method registers the Event Tracing for Windows (ETW) capability of the miniport driver with PortCls.
old-location: audio\iportwmiregistration_registerwmiprovider.htm
tech.root: audio
ms.assetid: 5c092cbd-ef05-4b3d-ac9f-20f2fbf2c37c
ms.date: 05/08/2018
ms.keywords: IPortWMIRegistration interface [Audio Devices],RegisterWMIProvider method, IPortWMIRegistration.RegisterWMIProvider, IPortWMIRegistration::RegisterWMIProvider, RegisterWMIProvider, RegisterWMIProvider method [Audio Devices], RegisterWMIProvider method [Audio Devices],IPortWMIRegistration interface, audio.iportwmiregistration_registerwmiprovider, audmp-routines_3a73bed7-3a9f-4be2-8d15-33f707714c94.xml, portcls/IPortWMIRegistration::RegisterWMIProvider
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.irql: PASSIVE_LEVEL.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Portcls.h
api_name:
-	IPortWMIRegistration.RegisterWMIProvider
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortWMIRegistration::RegisterWMIProvider


## -description


The <code>RegisterWMIProvider</code> method registers the <a href="https://msdn.microsoft.com/library/windows/hardware/dn938554">Event Tracing for Windows</a> (ETW) capability of the miniport driver with PortCls.


## -parameters




### -param






#### - MiniportWmiContext [in]

Specifies a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565813">WMILIB_CONTEXT</a> structure that provides registration information for a driver's data blocks and event blocks.


#### - pDeviceObject [in]

Specifies a pointer to a <a href="https://msdn.microsoft.com/f3522315-cf15-41f7-ac87-c625c7dc8040">DEVICE_OBJECT </a> structure that represents the functional device object of the adapter driver.


## -returns



The <code>RegisterWMIProvider</code> method returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.




## -remarks



For more information about ETW, see <a href="https://go.microsoft.com/fwlink/p/?linkid=154129">Improve Debugging And Performance Tuning With ETW</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn938554">Event Tracing for Windows</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536935">IPortWMIRegistration</a>



<a href="https://go.microsoft.com/fwlink/p/?linkid=154129">Improve Debugging And Performance Tuning With ETW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565813">WMILIB_CONTEXT</a>
 

 

