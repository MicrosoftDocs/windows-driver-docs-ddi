---
UID: NF:portcls.IPortClsPnp.UnregisterAdapterPnpManagement
title: IPortClsPnp::UnregisterAdapterPnpManagement method
author: windows-driver-content
description: The UnRegisterAdapterPowerManagement method unregisters the PnP management interface of the adapter from PortCls.
old-location: audio\iportclspnp_unregisteradapterpnpmanagement.htm
old-project: audio
ms.assetid: 7FAA5C88-2846-4C98-A44A-B53A1A7A953C
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IPortClsPnp, IPortClsPnp interface [Audio Devices], UnregisterAdapterPnpManagement method, IPortClsPnp::UnregisterAdapterPnpManagement, UnregisterAdapterPnpManagement method [Audio Devices], UnregisterAdapterPnpManagement method [Audio Devices], IPortClsPnp interface, UnregisterAdapterPnpManagement,IPortClsPnp.UnregisterAdapterPnpManagement, audio.iportclspnp_unregisteradapterpnpmanagement, portcls/IPortClsPnp::UnregisterAdapterPnpManagement
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 10, version 1511 and later versions of Windows.
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
-	IPortClsPnp.UnregisterAdapterPnpManagement
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPortClsPnp::UnregisterAdapterPnpManagement method


## -description


The <code>UnRegisterAdapterPowerManagement</code> method unregisters the PnP management interface of the adapter from PortCls.


## -parameters




### -param DeviceObject [in]

Specifies a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure that represents the functional device object of the adapter that the PnP management was registered with earlier using <a href="https://msdn.microsoft.com/library/windows/hardware/mt604860">IPortClsPnp::RegisterAdapterPnpManagement</a>.


## -returns



The <code>UnregisterAdapterPowerManagement</code> method returns STATUS_SUCCESS if the call is successful. Otherwise, it returns the appropriate error code.




## -remarks



For more information,  see <a href="https://msdn.microsoft.com/FCAD7F8B-AA9B-430A-BCAF-04E13FA15382">Implement PnP Rebalance for PortCls Audio Drivers</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt604859">IPortClsPnp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt604860">IPortClsPnp::RegisterAdapterPnpManagement</a>
 

 

