---
UID: NF:portcls.PcRemoveStreamResource
title: PcRemoveStreamResource function (portcls.h)
description: PcRemoveStreamResource removes an existing stream resource.
old-location: audio\pcremovestreamresource.htm
tech.root: audio
ms.assetid: D923DA5C-0169-475D-8C0C-6A99EB06ECE0
ms.date: 05/08/2018
ms.keywords: PcRemoveStreamResource, PcRemoveStreamResource function [Audio Devices], audio.pcremovestreamresource, portcls/PcRemoveStreamResource
ms.topic: function
f1_keywords:
 - "portcls/PcRemoveStreamResource"
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NA
api_name:
- PcRemoveStreamResource
product:
- Windows
targetos: Windows
req.typenames: 
---

# PcRemoveStreamResource function


## -description


PcRemoveStreamResource removes an existing  stream resource. PcRemoveStreamResource can be called by any driver, including non-audio WaveRT miniport drivers, that has interrupts/threads associated with an audio stream. It can also be called by audio WaveRT miniport drivers. 


## -parameters




### -param ResourceHandle [in]

PCSTREAMRESOURCE– Resource handle returned by PcAddStreamResource.  
For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-pcaddstreamresource">PcAddStreamResource</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/ns-portcls-_pcstreamresource_descriptor">PCSTREAMRESOURCE_DESCRIPTOR</a>.  


## -returns



STATUS_SUCCESS – The driver was able to register the resource of the specified PDO. 

 

STATUS_INVALID_PARAMETER – The driver returns this error if it finds any other parameter invalid, aside from the specific cases for other error status instances. 



Additional standard status codes may be returned.




## -remarks



To help ensure glitch-free operation, audio drivers must register their streaming resources with portcls. This allows the OS to manage resources to avoid interference between audio streaming and other subsystems. 

Stream resources are any resources used by the audio driver to process audio streams or ensure audio data flow. 

Audio drivers must remove a previously registered resource.  Drivers may unregister a resource as a result of the following system activities:  



<ul>
<li>Device re-balance when I/O resources change. 

</li>
<li>Device power transitions (D0<- ->Dx) when resources are destroyed or created. For example interrupts may be disconnected when going in Dx and reconnected with moving back to D0. 

</li>
<li>When processing stop, surprise-remove, remove plug and play events. 

</li>
<li>When associated audio endpoints go away. For example if a thread is created to handle the data stream of an endpoint and the endpoint is removed. In this case, the driver should remove the thread stream resource.</li>
</ul>
The audio driver must make sure the resource is valid when making this call.

Audio drivers that only run in Windows 10 can use  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-pcaddstreamresource">PcAddStreamResource</a> and <b>PcRemoveStreamResource</b>. For Audio waveRT miniport drivers that need to also run under previous versions of Windows, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iportclsstreamresourcemanager-addstreamresource">AddStreamResource</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iportclsstreamresourcemanager-removestreamresource">RemoveStreamResource</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/ns-portcls-_pcstreamresource_descriptor">PCSTREAMRESOURCE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-pcaddstreamresource">PcAddStreamResource</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/ne-portcls-_pcstreamresourcetype">PcStreamResourceType</a>
 

 

