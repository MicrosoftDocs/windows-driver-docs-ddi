---
UID: NN:portcls.IPortClsStreamResourceManager2
title: IPortClsStreamResourceManager2 (portcls.h)
description: IPortClsStreamResourceManager2 is used to manage the registration of audio stream resources.
old-location: audio\iportclsstreamresourcemanager2.htm
tech.root: audio
ms.assetid: B37310B5-3C74-428A-B8DF-C39B85A521C0
ms.date: 05/08/2018
ms.keywords: IPortClsStreamResourceManager2, IPortClsStreamResourceManager2 interface [Audio Devices], IPortClsStreamResourceManager2 interface [Audio Devices],described, audio.iportclsstreamresourcemanager2, portcls/IPortClsStreamResourceManager2
ms.topic: interface
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- portcls.h
api_name:
- IPortClsStreamResourceManager2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortClsStreamResourceManager2 interface


## -description


IPortClsStreamResourceManager2 is used to manage the registration of audio stream resources. 

To help ensure glitch-free operation, audio drivers must register their streaming resources. This allows the OS to manage resources to avoid interference between audio streaming and other subsystems. 

Stream resources are any resources used by the audio driver to process audio streams or ensure audio data flow. 


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iportclsstreamresourcemanager-addstreamresource">IPortClsStreamResourceManager::AddStreamResource</a> expects that the caller is an audio miniport driver. <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iportclsstreamresourcemanager2-addstreamresource2">IPortClsStreamResourceManager2::AddStreamResource2</a> does not assume that the caller is an audio miniport driver, and requires an explicit pointer to the Physical Device Object (PDO).

The IPortClsStreamResourceManager2 interface is supported in Windows 10, version 1511 and later versions of Windows. IPortClsStreamResourceManager2 inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iportclsstreamresourcemanager">IPortClsStreamResourceManager</a> and IUnknown.

A WaveRT miniport driver optionally can use this interface instead of hard-linking with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-pcaddstreamresource">PcAddStreamResource</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-pcremovestreamresource">PcRemoveStreamResource</a>. This option is very useful when the 

same audio miniport driver must run on previous versions of Windows. The audio miniport driver can query for the IID_IPortClsStreamResourceManager2 interface and register its resources only when PortCls supports the interface.

