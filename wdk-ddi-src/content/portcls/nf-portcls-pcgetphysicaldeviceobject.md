---
UID: NF:portcls.PcGetPhysicalDeviceObject
title: PcGetPhysicalDeviceObject function (portcls.h)
description: The PcGetPhysicalDeviceObject function enables audio miniport drivers to retrieve the underlying physical device object of the audio device.
old-location: audio\pcgetphysicaldeviceobject.htm
tech.root: audio
ms.assetid: A7917082-4C3F-445A-AD26-32DE670754E5
ms.date: 05/08/2018
keywords: ["PcGetPhysicalDeviceObject function"]
ms.keywords: PcGetPhysicalDeviceObject, PcGetPhysicalDeviceObject function [Audio Devices], audio.pcgetphysicaldeviceobject, portcls/PcGetPhysicalDeviceObject
f1_keywords:
 - "portcls/PcGetPhysicalDeviceObject"
req.header: portcls.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting in Windows 8.
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
req.lib: Portcls.lib
req.dll: 
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Portcls.lib
- Portcls.dll
api_name:
- PcGetPhysicalDeviceObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# PcGetPhysicalDeviceObject function


## -description


The <b>PcGetPhysicalDeviceObject</b> function enables audio miniport drivers to retrieve the  underlying physical device object of the audio device.


## -parameters




### -param pDeviceObject [in]

Pointer to the device object for the device.


### -param ppPhysicalObject [out]

Pointer to the physical object for the device.


## -returns



The <b>PcGetPhysicalDeviceObject</b> function returns STATUS_SUCCESS if the function call was successful. Otherwise, it returns the appropriate error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/audio-port-class-functions">Audio Port Class Functions</a>
 

 

