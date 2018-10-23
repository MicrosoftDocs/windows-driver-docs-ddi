---
UID: NF:portcls.IPortWMIRegistration.UnregisterWMIProvider
title: IPortWMIRegistration::UnregisterWMIProvider
author: windows-driver-content
description: The UnregisterWMIProvider method unregisters the Event Tracing for Windows (ETW) interface that was previously registered with a call to the RegisterWMIProvider method. The unregistration disables the ETW registration with PortCls.
old-location: audio\iportwmiregistration_unregisterwmiprovider.htm
tech.root: audio
ms.assetid: 51c43e1a-ec8e-4dd2-ab08-b90cd89d9b5d
ms.date: 05/08/2018
ms.keywords: IPortWMIRegistration interface [Audio Devices],UnregisterWMIProvider method, IPortWMIRegistration.UnregisterWMIProvider, IPortWMIRegistration::UnregisterWMIProvider, UnregisterWMIProvider, UnregisterWMIProvider method [Audio Devices], UnregisterWMIProvider method [Audio Devices],IPortWMIRegistration interface, audio.iportwmiregistration_unregisterwmiprovider, audmp-routines_3c640b1e-b98a-491d-a586-c6acaf8b07d4.xml, portcls/IPortWMIRegistration::UnregisterWMIProvider
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
-	IPortWMIRegistration.UnregisterWMIProvider
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortWMIRegistration::UnregisterWMIProvider


## -description


The <code>UnregisterWMIProvider</code> method unregisters the <a href="https://msdn.microsoft.com/library/windows/hardware/dn938554">Event Tracing for Windows</a> (ETW) interface that was previously registered with a call to the RegisterWMIProvider method. The unregistration disables the ETW registration with PortCls.


## -parameters






#### - pDeviceObject

Specifies a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure that represents the functional device object of the adapter driver.


## -returns



The <code>UnregisterWMIProvider</code> method returns STATUS_SUCCESS if the call is successful. Otherwise, it returns the appropriate error message.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn938554">Event Tracing for Windows</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536935">IPortWMIRegistration</a>
 

 

