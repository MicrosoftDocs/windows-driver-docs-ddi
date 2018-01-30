---
UID: NF:portcls.IPortWMIRegistration.UnregisterWMIProvider
title: IPortWMIRegistration::UnregisterWMIProvider method
author: windows-driver-content
description: The UnregisterWMIProvider method unregisters the Event Tracing for Windows (ETW) interface that was previously registered with a call to the RegisterWMIProvider method. The unregistration disables the ETW registration with PortCls.
old-location: audio\iportwmiregistration_unregisterwmiprovider.htm
old-project: audio
ms.assetid: 51c43e1a-ec8e-4dd2-ab08-b90cd89d9b5d
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPortWMIRegistration interface [Audio Devices], UnregisterWMIProvider method, IPortWMIRegistration, UnregisterWMIProvider method [Audio Devices], audio.iportwmiregistration_unregisterwmiprovider, UnregisterWMIProvider method [Audio Devices], IPortWMIRegistration interface, audmp-routines_3c640b1e-b98a-491d-a586-c6acaf8b07d4.xml, UnregisterWMIProvider, portcls/IPortWMIRegistration::UnregisterWMIProvider, IPortWMIRegistration::UnregisterWMIProvider
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: portcls.h
req.dll: 
req.irql: PASSIVE_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Portcls.h
apiname:
-	IPortWMIRegistration.UnregisterWMIProvider
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPortWMIRegistration::UnregisterWMIProvider method


## -description


The <code>UnregisterWMIProvider</code> method unregisters the <a href="https://msdn.microsoft.com/library/windows/hardware/dn938554">Event Tracing for Windows</a> (ETW) interface that was previously registered with a call to the RegisterWMIProvider method. The unregistration disables the ETW registration with PortCls.


## -syntax


````
NTSTATUS UnregisterWMIProvider(
   pDeviceObject pDeviceObject
);
````


## -parameters





#### - pDeviceObject

Specifies a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure that represents the functional device object of the adapter driver.


## -returns


The <code>UnregisterWMIProvider</code> method returns STATUS_SUCCESS if the call is successful. Otherwise, it returns the appropriate error message.



## -see-also

<a href="..\portcls\nn-portcls-iportwmiregistration.md">IPortWMIRegistration</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/dn938554">Event Tracing for Windows</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortWMIRegistration::UnregisterWMIProvider method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

