---
UID: NF:portcls.IPortClsPower.RegisterAdapterPowerManagement
title: IPortClsPower::RegisterAdapterPowerManagement method
author: windows-driver-content
description: The RegisterAdapterPowerManagement method registers the power management interface of the adapter with PortCls.
old-location: audio\iportclspower_registeradapterpowermanagement.htm
old-project: audio
ms.assetid: f4eb9d18-4352-47e2-bd5f-256e1fa831d3
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IPortClsPower, IPortClsPower interface [Audio Devices], RegisterAdapterPowerManagement method, IPortClsPower::RegisterAdapterPowerManagement, RegisterAdapterPowerManagement method [Audio Devices], RegisterAdapterPowerManagement method [Audio Devices], IPortClsPower interface, RegisterAdapterPowerManagement,IPortClsPower.RegisterAdapterPowerManagement, audio.iportclspower_registeradapterpowermanagement, audmp-routines_9c179fd9-d332-478d-a114-469dc1c746fc.xml, portcls/IPortClsPower::RegisterAdapterPowerManagement
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IPortClsPower.RegisterAdapterPowerManagement
product:
- Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPortClsPower::RegisterAdapterPowerManagement method


## -description


The <code>RegisterAdapterPowerManagement</code> method registers the power management interface of the adapter with PortCls.


## -parameters




### -param _pUnknown [in]

Specifies a pointer to <b>IUnknown</b>. . PortCls queries this <b>IUnknown</b> object for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536485">IAdapterPowerManagement</a> or the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536486">IAdapterPowerManagement2</a> interface of the adapter.


### -param _DeviceObject [in]

Specifies a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure that represents the functional device object of the adapter.


## -returns



The <code>RegisterAdapterPowerManagement</code> method returns STATUS_SUCCESS if the call is successful. Otherwise, it returns the appropriate error code.




## -remarks



When the <code>RegisterAdapterPowerManagement</code> method registers the power management interface for the adapter with PortCls, it allows the adapter driver to be notified of power state change events.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536485">IAdapterPowerManagement</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536486">IAdapterPowerManagement2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536844">IPortClsPower</a>
 

 

