---
UID: NF:portcls.PcAddStreamResource
title: PcAddStreamResource function
author: windows-driver-content
description: PcAddStreamResource adds a stream resource.
old-location: audio\pcaddstreamresource.htm
old-project: audio
ms.assetid: CADB17C6-07EA-4497-AA73-4AECCC1D0A45
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: portcls/PcAddStreamResource, PcAddStreamResource, audio.pcaddstreamresource, PcAddStreamResource function [Audio Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NA
apiname:
-	PcAddStreamResource
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# PcAddStreamResource function


## -description


PcAddStreamResource adds a stream resource. 
Two type of stream resources are supported: interrupts and driver-owned threads. PcAddStreamResource can be called by any non-audio WaveRT miniport driver that has interrupts/threads associated with an audio stream. It can also be called by audio WaveRT miniport drivers.


## -syntax


````
NTSTATUS  PcAddStreamResource(
  _In_  PDEVICE_OBJECT               PhysicalDeviceObject,
  _In_  PVOID                        ResourceSet,
  _In_  PPCSTREAMRESOURCE_DESCRIPTOR     ResourceDescriptor,
  _Out_ PCSTREAMRESOURCE*            ResourceHandle
);
````


## -parameters




### -param PhysicalDeviceObject [in]

PDEVICE_OBJECT - The PDO of the device stack using this resource. 


### -param ResourceSet [in]

PVOID - Reserved for future use, set to NULL. Only device-scoped resources are supported at this time. 


### -param ResourceDescriptor [in]

PPCSTREAMRESOURCE_DESCRIPTOR - The resource to add. For more information, see <a href="..\portcls\ns-portcls-_pcstreamresource_descriptor.md">PCSTREAMRESOURCE_DESCRIPTOR</a>. 


### -param ResourceHandle [out]

PCSTREAMRESOURCE* - The location that will hold the resource handle. For more information, see <a href="..\portcls\nf-portcls-pcremovestreamresource.md">PcRemoveStreamResource</a>.  


## -returns


STATUS_SUCCESS – The driver was able to register the resource of the specified PDO. 

 

STATUS_INVALID_PARAMETER – The driver returns this error if it finds any other parameter invalid, aside from the specific cases for other error status instances. 



Additional standard status codes may be returned.



## -remarks


To help ensure glitch-free operation, audio drivers must register their streaming resources with portcls. This allows the OS to manage resources to avoid interference between audio streaming and other subsystems. 

Stream resources are any resources used by the audio driver to process audio streams or ensure audio data flow. 

All audio drivers must register their stream resources with the audio class driver. Driver registers the following resource types: interrupts, driver-owned threads and dependencies on other audio stack’s resources (example: parallel audio driver stacks). See the definition of <a href="..\portcls\ns-portcls-_pcstreamresource_descriptor.md">PCSTREAMRESOURCE_DESCRIPTOR</a> for more information.  

Audio driver must make sure the resource is valid when making this call.

Audio drivers that only run in Windows 10 can use  <b>PcAddStreamResource</b> and <a href="..\portcls\nf-portcls-pcremovestreamresource.md">PcRemoveStreamResource</a>. For Audio waveRT miniport drivers that need to also run under previous versions of Windows, use <a href="https://msdn.microsoft.com/F9F7E13B-E8D1-4B02-9CC5-737145DEFEB9">AddStreamResource</a> and <a href="https://msdn.microsoft.com/35A90B3C-27D7-4BBA-A754-098D191A3201">RemoveStreamResource</a>. 



## -see-also

<a href="..\portcls\nf-portcls-pcremovestreamresource.md">PcRemoveStreamResource</a>

<a href="..\portcls\ns-portcls-_pcstreamresource_descriptor.md">PCSTREAMRESOURCE_DESCRIPTOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcAddStreamResource function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

