---
UID: NN:portcls.IMusicTechnology
title: IMusicTechnology (portcls.h)
description: The IMusicTechnology interface is used to change the music technology GUIDs that are specified in the data range descriptors for the pins belonging to a MIDI or DMus miniport driver.
old-location: audio\imusictechnology.htm
tech.root: audio
ms.assetid: e42380f8-8e82-4c98-88e9-9e44f5091a85
ms.date: 05/08/2018
keywords: ["IMusicTechnology interface"]
ms.keywords: IMusicTechnology, IMusicTechnology interface [Audio Devices], IMusicTechnology interface [Audio Devices],described, audio.imusictechnology, audmp-routines_9300aa03-6606-46a0-ad5b-b0d776c46ed1.xml, portcls/IMusicTechnology
f1_keywords:
 - "portcls/IMusicTechnology"
 - "IMusicTechnology"
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
- IMusicTechnology
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMusicTechnology interface


## -description


The <code>IMusicTechnology</code> interface is used to change the music technology GUIDs that are specified in the data range descriptors for the pins belonging to a MIDI or DMus miniport driver. The GUID specifies the type of MIDI synthesizer device that the pin represents. The DMus miniport driver implements the <code>IMusicTechnology</code> interface and exposes this interface to the DMus port driver. To determine whether the miniport driver supports this interface, the port driver calls the miniport driver's <b>IMiniportDMus::QueryInterface</b> method with REFIID <b>IID_IMusicTechnology</b>. <code>IMusicTechnology</code> inherits from the <b>IUnknown</b> interface.

The system-supplied miniport drivers DMusUART and UART both support the <code>IMusicTechnology</code> interface. For information about these drivers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcnewminiport">PcNewMiniport</a>.

For other MIDI and DMus miniport drivers, support for <code>IMusicTechnology</code> is optional. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/music-technology-guids">Music Technology GUIDs</a>.

