---
UID: NF:portcls.IPortClsPower.SetIdlePowerManagement
title: IPortClsPower::SetIdlePowerManagement method
author: windows-driver-content
description: The SetIdlePowerManagement method provides a way for the adapter driver to opt in or opt out of idle state detection.
old-location: audio\iportclspower_setidlepowermanagement.htm
old-project: audio
ms.assetid: ccef350c-7c46-43fa-8834-b0d712d9cf38
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: SetIdlePowerManagement method [Audio Devices], IPortClsPower interface, audio.iportclspower_setidlepowermanagement, IPortClsPower, IPortClsPower interface [Audio Devices], SetIdlePowerManagement method, SetIdlePowerManagement method [Audio Devices], IPortClsPower::SetIdlePowerManagement, portcls/IPortClsPower::SetIdlePowerManagement, audmp-routines_909c6232-f96f-4487-a51e-a127dc9ad317.xml, SetIdlePowerManagement
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
-	portcls.h
apiname:
-	IPortClsPower.SetIdlePowerManagement
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# IPortClsPower::SetIdlePowerManagement method


## -description


The <code>SetIdlePowerManagement</code> method provides a way for the adapter driver to opt in or opt out of idle state detection.


## -syntax


````
NTSTATUS SetIdlePowerManagement(
  [in] PDEVICE_OBJECT DeviceObject,
  [in] BOOLEAN        bEnabled
);
````


## -parameters




### -param _DeviceObject [in]

Specifies a pointer to a <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure that represents the functional device object of the adapter.


### -param _bEnabled [in]

Specifies a Boolean variable that indicates whether idle state detection is enabled or disabled.


## -returns



The <code>SetIdlePowerManagement</code> method returns STATUS_SUCCESS if the call was successful. Otherwise, it returns the appropriate error code. 




## -remarks



When the <i>bEnabled</i> parameter is set to <b>TRUE</b>, it indicates that the adapter driver has enabled idle state detection. When the system determines that the adapter is idle, the adapter can be put into the sleep state to save power. If the adapter was not designed to suppress the popping sound that is normally associated with power-up, it is possible that the adapter can experience a popping effect when it comes out of the sleep state.




## -see-also

<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/43721EC9-4901-4C68-9CCC-E0A71BF2200E">Immediate Idle Timeout Opt-in</a>



<a href="..\portcls\nn-portcls-iportclspower.md">IPortClsPower</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortClsPower::SetIdlePowerManagement method%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

