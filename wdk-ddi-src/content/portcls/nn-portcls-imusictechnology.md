---
UID: NN:portcls.IMusicTechnology
title: IMusicTechnology
author: windows-driver-content
description: The IMusicTechnology interface is used to change the music technology GUIDs that are specified in the data range descriptors for the pins belonging to a MIDI or DMus miniport driver.
old-location: audio\imusictechnology.htm
old-project: audio
ms.assetid: e42380f8-8e82-4c98-88e9-9e44f5091a85
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IMusicTechnology, IMusicTechnology interface [Audio Devices], IMusicTechnology interface [Audio Devices], described, audio.imusictechnology, audmp-routines_9300aa03-6606-46a0-ad5b-b0d776c46ed1.xml, portcls/IMusicTechnology
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IMusicTechnology
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMusicTechnology interface


## -description


The <code>IMusicTechnology</code> interface is used to change the music technology GUIDs that are specified in the data range descriptors for the pins belonging to a MIDI or DMus miniport driver. The GUID specifies the type of MIDI synthesizer device that the pin represents. The DMus miniport driver implements the <code>IMusicTechnology</code> interface and exposes this interface to the DMus port driver. To determine whether the miniport driver supports this interface, the port driver calls the miniport driver's <b>IMiniportDMus::QueryInterface</b> method with REFIID <b>IID_IMusicTechnology</b>. <code>IMusicTechnology</code> inherits from the <b>IUnknown</b> interface.

The system-supplied miniport drivers DMusUART and UART both support the <code>IMusicTechnology</code> interface. For information about these drivers, see <a href="..\portcls\nf-portcls-pcnewminiport.md">PcNewMiniport</a>.

For other MIDI and DMus miniport drivers, support for <code>IMusicTechnology</code> is optional. For more information, see <a href="https://msdn.microsoft.com/3b7c2907-e67f-458e-809d-080dcc30be1a">Music Technology GUIDs</a>.

