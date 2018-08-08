---
UID: NF:portcls.PcAddStreamResource
title: PcAddStreamResource function
author: windows-driver-content
description: PcAddStreamResource adds a stream resource.
old-location: audio\pcaddstreamresource.htm
tech.root: audio
ms.assetid: CADB17C6-07EA-4497-AA73-4AECCC1D0A45
ms.author: windowsdriverdev
ms.date: 5/8/2018
ms.keywords: PcAddStreamResource, PcAddStreamResource function [Audio Devices], audio.pcaddstreamresource, portcls/PcAddStreamResource
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.dll: NA
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NA
api_name:
-	PcAddStreamResource
product:
- Windows
targetos: Windows
req.typenames: 
---

# PcAddStreamResource function


## -description


PcAddStreamResource adds a stream resource. 
Two type of stream resources are supported: interrupts and driver-owned threads. PcAddStreamResource can be called by any non-audio WaveRT miniport driver that has interrupts/threads associated with an audio stream. It can also be called by audio WaveRT miniport drivers.


## -parameters




### -param PhysicalDeviceObject [in]

PDEVICE_OBJECT - The PDO of the device stack using this resource. 


### -param ResourceSet [in]

PVOID - Reserved for future use, set to NULL. Only device-scoped resources are supported at this time. 


### -param ResourceDescriptor [in]

PPCSTREAMRESOURCE_DESCRIPTOR - The resource to add. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/mt298191">PCSTREAMRESOURCE_DESCRIPTOR</a>. 


### -param ResourceHandle [out]

PCSTREAMRESOURCE* - The location that will hold the resource handle. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/mt298189">PcRemoveStreamResource</a>.  


## -returns



STATUS_SUCCESS – The driver was able to register the resource of the specified PDO. 

 

STATUS_INVALID_PARAMETER – The driver returns this error if it finds any other parameter invalid, aside from the specific cases for other error status instances. 



Additional standard status codes may be returned.




## -remarks



To help ensure glitch-free operation, audio drivers must register their streaming resources with portcls. This allows the OS to manage resources to avoid interference between audio streaming and other subsystems. 

Stream resources are any resources used by the audio driver to process audio streams or ensure audio data flow. 

All audio drivers must register their stream resources with the audio class driver. Driver registers the following resource types: interrupts, driver-owned threads and dependencies on other audio stack’s resources (example: parallel audio driver stacks). See the definition of <a href="https://msdn.microsoft.com/library/windows/hardware/mt298191">PCSTREAMRESOURCE_DESCRIPTOR</a> for more information.  

Audio driver must make sure the resource is valid when making this call.

Audio drivers that only run in Windows 10 can use  <b>PcAddStreamResource</b> and <a href="https://msdn.microsoft.com/library/windows/hardware/mt298189">PcRemoveStreamResource</a>. For Audio waveRT miniport drivers that need to also run under previous versions of Windows, use <a href="https://msdn.microsoft.com/F9F7E13B-E8D1-4B02-9CC5-737145DEFEB9">AddStreamResource</a> and <a href="https://msdn.microsoft.com/35A90B3C-27D7-4BBA-A754-098D191A3201">RemoveStreamResource</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt298191">PCSTREAMRESOURCE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt298189">PcRemoveStreamResource</a>
 

 

