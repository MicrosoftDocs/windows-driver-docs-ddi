---
UID: NN:portcls.IPortClsStreamResourceManager
title: IPortClsStreamResourceManager (portcls.h)
description: IPortClsStreamResourceManager is used to manage the registration of audio stream resources.
old-location: audio\iportclsstreamresourcemanager.htm
tech.root: audio
ms.assetid: FC13CB2E-2027-4BCE-AEEE-346CB0784819
ms.date: 03/19/2018
keywords: ["IPortClsStreamResourceManager interface"]
ms.keywords: IPortClsStreamResourceManager, IPortClsStreamResourceManager interface [Audio Devices], IPortClsStreamResourceManager interface [Audio Devices], described, audio.iportclsstreamresourcemanager, portcls/IPortClsStreamResourceManager
f1_keywords:
 - "portcls/IPortClsStreamResourceManager"
 - "IPortClsStreamResourceManager"
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
req.lib: Portcls.lib
req.dll:
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- portcls.h
api_name:
- IPortClsStreamResourceManager
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPortClsStreamResourceManager interface


## -description


IPortClsStreamResourceManager is used to manage the registration of audio stream resources.

To help ensure glitch-free operation, audio drivers must register their streaming resources.
  This allows the OS to manage resources to avoid interference between audio streaming and other subsystems.
Stream resources are any resources used by the audio driver to process audio streams or ensure audio data flow.

The IPortClsStreamResourceManager interface is supported in Windows 10 and later versions of Windows.


These methods can only be used by audio waveRT miniport drivers.

A WaveRT miniport driver optionally can use this interface instead of hard-linking with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcaddstreamresource">PcAddStreamResource</a>
and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcremovestreamresource">PcRemoveStreamResource</a>.
This option is very useful when the same audio miniport driver must run on previous versions of Windows.
The audio miniport driver can query for the IID_IPortClsStreamResourceManager interface and register its resources
only when PortCls supports the interface.

