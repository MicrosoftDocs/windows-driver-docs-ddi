---
UID: NF:portcls.IUnregisterPhysicalConnection.UnregisterPhysicalConnection
title: IUnregisterPhysicalConnection::UnregisterPhysicalConnection method
author: windows-driver-content
description: The UnregisterPhysicalConnection method deletes the registration of a physical connection that was registered by a previous call to PcRegisterPhysicalConnection.
old-location: audio\iunregisterphysicalconnection_unregisterphysicalconnection.htm
old-project: audio
ms.assetid: e8b99549-0fe2-4c8a-ad93-6689ebddee40
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IUnregisterPhysicalConnection, IUnregisterPhysicalConnection interface [Audio Devices], UnregisterPhysicalConnection method, IUnregisterPhysicalConnection::UnregisterPhysicalConnection, UnregisterPhysicalConnection method [Audio Devices], UnregisterPhysicalConnection method [Audio Devices], IUnregisterPhysicalConnection interface, UnregisterPhysicalConnection,IUnregisterPhysicalConnection.UnregisterPhysicalConnection, audio.iunregisterphysicalconnection_unregisterphysicalconnection, audmp-routines_5ecc7a84-6d2c-4514-9de8-cb1e4c60a61c.xml, portcls/IUnregisterPhysicalConnection::UnregisterPhysicalConnection
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IUnregisterPhysicalConnection.UnregisterPhysicalConnection
product:
- Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IUnregisterPhysicalConnection::UnregisterPhysicalConnection method


## -description


The <code>UnregisterPhysicalConnection</code> method deletes the registration of a physical connection that was registered by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff537726">PcRegisterPhysicalConnection</a>.


## -parameters




### -param DeviceObject [in]

Pointer to the device object for the adapter device. This parameter must point to a system structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>.


### -param FromUnknown [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536842">IPort</a> interface of a port driver object. The port driver object that is associated with <i>FromUnknown</i> is bound to the subdevice that supplies the connection's data source pin.


### -param FromPin [in]

Specifies a pin ID. This parameter identifies the data source (output) pin on the filter that is associated with the <i>FromUnknown</i> interface.


### -param ToUnknown [in]

Pointer to the <b>IPort</b> interface of a port driver object. The port driver object that is associated with <i>ToUnknown</i> is bound to the subdevice that supplies the connection's data sink pin.


### -param ToPin [in]

Specifies a pin ID. This parameter identifies the data sink (input) pin on the filter that is associated with the <i>ToUnknown</i> interface.


## -returns



<code>UnregisterPhysicalConnection</code> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.




## -remarks



For more information, see <a href="https://msdn.microsoft.com/d8ebd6d9-37ed-4890-aae1-5ecf58f2e22a">Dynamic Audio Subdevices</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536842">IPort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537022">IUnregisterPhysicalConnection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537726">PcRegisterPhysicalConnection</a>
 

 

