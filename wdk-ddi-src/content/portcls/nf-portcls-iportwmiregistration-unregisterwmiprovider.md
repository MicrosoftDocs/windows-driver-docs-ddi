---
UID: NF:portcls.IPortWMIRegistration.UnregisterWMIProvider
title: IPortWMIRegistration::UnregisterWMIProvider (portcls.h)
description: The UnregisterWMIProvider method unregisters the Event Tracing for Windows (ETW) interface that was previously registered with a call to the RegisterWMIProvider method. The unregistration disables the ETW registration with PortCls.
old-location: audio\iportwmiregistration_unregisterwmiprovider.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IPortWMIRegistration::UnregisterWMIProvider"]
ms.keywords: IPortWMIRegistration interface [Audio Devices],UnregisterWMIProvider method, IPortWMIRegistration.UnregisterWMIProvider, IPortWMIRegistration::UnregisterWMIProvider, UnregisterWMIProvider, UnregisterWMIProvider method [Audio Devices], UnregisterWMIProvider method [Audio Devices],IPortWMIRegistration interface, audio.iportwmiregistration_unregisterwmiprovider, audmp-routines_3c640b1e-b98a-491d-a586-c6acaf8b07d4.xml, portcls/IPortWMIRegistration::UnregisterWMIProvider
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPortWMIRegistration::UnregisterWMIProvider
 - portcls/IPortWMIRegistration::UnregisterWMIProvider
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Portcls.h
api_name:
 - IPortWMIRegistration.UnregisterWMIProvider
---

# IPortWMIRegistration::UnregisterWMIProvider


## -description

The <code>UnregisterWMIProvider</code> method unregisters the <a href="/windows-hardware/test/wpt/event-tracing-for-windows">Event Tracing for Windows</a> (ETW) interface that was previously registered with a call to the RegisterWMIProvider method. The unregistration disables the ETW registration with PortCls.

## -returns

The <code>UnregisterWMIProvider</code> method returns STATUS_SUCCESS if the call is successful. Otherwise, it returns the appropriate error message.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="/windows-hardware/test/wpt/event-tracing-for-windows">Event Tracing for Windows</a>



<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iportwmiregistration">IPortWMIRegistration</a>
