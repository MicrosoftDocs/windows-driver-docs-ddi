---
UID: NF:portcls.IPortClsPower.SetIdlePowerManagement
title: IPortClsPower::SetIdlePowerManagement (portcls.h)
description: The SetIdlePowerManagement method provides a way for the adapter driver to opt in or opt out of idle state detection.
old-location: audio\iportclspower_setidlepowermanagement.htm
tech.root: audio
ms.assetid: ccef350c-7c46-43fa-8834-b0d712d9cf38
ms.date: 05/08/2018
ms.keywords: IPortClsPower interface [Audio Devices],SetIdlePowerManagement method, IPortClsPower.SetIdlePowerManagement, IPortClsPower::SetIdlePowerManagement, SetIdlePowerManagement, SetIdlePowerManagement method [Audio Devices], SetIdlePowerManagement method [Audio Devices],IPortClsPower interface, audio.iportclspower_setidlepowermanagement, audmp-routines_909c6232-f96f-4487-a51e-a127dc9ad317.xml, portcls/IPortClsPower::SetIdlePowerManagement
ms.topic: method
f1_keywords:
 - "portcls/IPortClsPower.SetIdlePowerManagement"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- portcls.h
api_name:
- IPortClsPower.SetIdlePowerManagement
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortClsPower::SetIdlePowerManagement


## -description


The <code>SetIdlePowerManagement</code> method provides a way for the adapter driver to opt in or opt out of idle state detection.


## -parameters




### -param _DeviceObject [in]

Specifies a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure that represents the functional device object of the adapter.


### -param _bEnabled [in]

Specifies a Boolean variable that indicates whether idle state detection is enabled or disabled.


## -returns



The <code>SetIdlePowerManagement</code> method returns STATUS_SUCCESS if the call was successful. Otherwise, it returns the appropriate error code. 




## -remarks



When the <i>bEnabled</i> parameter is set to <b>TRUE</b>, it indicates that the adapter driver has enabled idle state detection. When the system determines that the adapter is idle, the adapter can be put into the sleep state to save power. If the adapter was not designed to suppress the popping sound that is normally associated with power-up, it is possible that the adapter can experience a popping effect when it comes out of the sleep state.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iportclspower">IPortClsPower</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/immediate-idle-timeout-opt-in">Immediate Idle Timeout Opt-in</a>
 

 

