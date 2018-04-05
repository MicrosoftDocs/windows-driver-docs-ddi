---
UID: NF:portcls.IMiniportWaveRT.GetDeviceDescription
title: IMiniportWaveRT::GetDeviceDescription method
author: windows-driver-content
description: The GetDeviceDescription method returns a pointer to a DEVICE_DESCRIPTION structure describing the device.
old-location: audio\iminiportwavert_getdevicedescription.htm
old-project: audio
ms.assetid: c6c0da06-c304-4d2d-907c-ccbb141c385b
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: GetDeviceDescription method [Audio Devices], GetDeviceDescription method [Audio Devices], IMiniportWaveRT interface, GetDeviceDescription,IMiniportWaveRT.GetDeviceDescription, IMiniportWaveRT, IMiniportWaveRT interface [Audio Devices], GetDeviceDescription method, IMiniportWaveRT::GetDeviceDescription, audio.iminiportwavert_getdevicedescription, audmp-routines_3a5441ed-a935-42ea-84be-29f1f6b6db07.xml, portcls/IMiniportWaveRT::GetDeviceDescription
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later Windows operating systems.
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
req.irql: Passive level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IMiniportWaveRT.GetDeviceDescription
product:
- Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportWaveRT::GetDeviceDescription method


## -description


The <code>GetDeviceDescription</code> method returns a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543107">DEVICE_DESCRIPTION</a> structure describing the device.


## -parameters




### -param DeviceDescription [out]

Pointer to a DEVICE_DESCRIPTION structure to be filled in by the miniport. The caller specifies a valid, non-NULL pointer value for this parameter.


## -returns



<code>GetDeviceDescription</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error status code.




## -remarks



The <i>DeviceDescription</i> parameter contains a pointer to a DEVICE_DESCRIPTION structure that the miniport fills in to describe the device




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543107">DEVICE_DESCRIPTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536737">IMiniportWaveRT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536920">IPortWaveRT</a>
 

 

