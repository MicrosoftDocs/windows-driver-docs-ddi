---
UID: NF:portcls.IPortClsPower.UnregisterAdapterPowerManagement
title: IPortClsPower::UnregisterAdapterPowerManagement
description: The UnregisterAdapterPowerManagement method unregisters the adapter's power management interface with PortCls.
old-location: audio\iportclspower_unregisteradapterpowermanagement.htm
tech.root: audio
ms.assetid: 4c8734b1-d7f5-476b-a85f-1d3f4df888b9
ms.date: 05/08/2018
ms.keywords: IPortClsPower interface [Audio Devices],UnregisterAdapterPowerManagement method, IPortClsPower.UnregisterAdapterPowerManagement, IPortClsPower::UnregisterAdapterPowerManagement, UnregisterAdapterPowerManagement, UnregisterAdapterPowerManagement method [Audio Devices], UnregisterAdapterPowerManagement method [Audio Devices],IPortClsPower interface, audio.iportclspower_unregisteradapterpowermanagement, audmp-routines_3dca5fa9-542d-437d-a2d9-9eef51b5f2ea.xml, portcls/IPortClsPower::UnregisterAdapterPowerManagement
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windwows.
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
-	IPortClsPower.UnregisterAdapterPowerManagement
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortClsPower::UnregisterAdapterPowerManagement


## -description


The <code>UnregisterAdapterPowerManagement</code> method unregisters the adapter's power management interface with PortCls.


## -parameters




### -param _DeviceObject [in]

Specifies a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure that represents the functional device object of the adapter.


## -returns



The <code>UnregisterAdapterPowerManagement</code> method returns STATUS_SUCCESS if the call is successful. Otherwise, it returns the appropriate error code.




## -remarks



The <code>UnregisterAdapterPowerManagement</code> method unregisters the adapter's power management interface that was registered by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536874">IPortClsPower::RegisterAdapterPowerManagement</a> method.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536844">IPortClsPower</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536874">IPortClsPower::RegisterAdapterPowerManagement</a>
 

 

