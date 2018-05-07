---
UID: NE:ntddpcm._PCMCIA_CONTROLLER_CLASS
title: "_PCMCIA_CONTROLLER_CLASS"
author: windows-driver-content
description: The PCMCIA_CONTROLLER_CLASS enumeration lists the different sorts of PC Card and CardBus controllers.
old-location: pcmcia\pcmcia_controller_class.htm
old-project: PCMCIA
ms.assetid: d834d97c-cf2d-430b-8f54-b0b47ab1503c
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PPCMCIA_CONTROLLER_CLASS, PCMCIA.pcmcia_controller_class, PCMCIA_CONTROLLER_CLASS, PCMCIA_CONTROLLER_CLASS enumeration [Buses], PPCMCIA_CONTROLLER_CLASS, PPCMCIA_CONTROLLER_CLASS enumeration pointer [Buses], PcmciaCardBusCompatible, PcmciaCirrusLogic, PcmciaDatabook, PcmciaDatabookCB, PcmciaElcController, PcmciaIntelCompatible, PcmciaInvalidControllerClass, PcmciaNEC, PcmciaNEC_98, PcmciaO2Micro, PcmciaOpti, PcmciaPciPcmciaBridge, PcmciaRicoh, PcmciaTI, PcmciaTopic, PcmciaTrid, _PCMCIA_CONTROLLER_CLASS, memcdref_a3d708d3-6fa4-4edd-af5d-1513c8da5a9b.xml, ntddpcm/PCMCIA_CONTROLLER_CLASS, ntddpcm/PPCMCIA_CONTROLLER_CLASS, ntddpcm/PcmciaCardBusCompatible, ntddpcm/PcmciaCirrusLogic, ntddpcm/PcmciaDatabook, ntddpcm/PcmciaDatabookCB, ntddpcm/PcmciaElcController, ntddpcm/PcmciaIntelCompatible, ntddpcm/PcmciaInvalidControllerClass, ntddpcm/PcmciaNEC, ntddpcm/PcmciaNEC_98, ntddpcm/PcmciaO2Micro, ntddpcm/PcmciaOpti, ntddpcm/PcmciaPciPcmciaBridge, ntddpcm/PcmciaRicoh, ntddpcm/PcmciaTI, ntddpcm/PcmciaTopic, ntddpcm/PcmciaTrid"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddpcm.h
req.include-header: Ntddpcm.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddpcm.h
api_name:
-	PCMCIA_CONTROLLER_CLASS
product:
- Windows
targetos: Windows
req.typenames: PCMCIA_CONTROLLER_CLASS, *PPCMCIA_CONTROLLER_CLASS
---

# _PCMCIA_CONTROLLER_CLASS enumeration


## -description


The PCMCIA_CONTROLLER_CLASS enumeration lists the different sorts of PC Card and CardBus controllers.


## -enum-fields




### -field PcmciaInvalidControllerClass

Indicates that the controller class is invalid. 


### -field PcmciaIntelCompatible

Indicates an Intel-compatible controller. 


### -field PcmciaCardBusCompatible

Indicates a cardbus-compatible controller. 


### -field PcmciaElcController

Indicates an ELC controller. 


### -field PcmciaDatabook

Indicates a controller from the Databook TCIC family of controllers. 


### -field PcmciaPciPcmciaBridge

Indicates a PCI to PCMCIA bridge. 


### -field PcmciaCirrusLogic

Indicates a CirrusLogic cardbus controller. 


### -field PcmciaTI

Indicates a TI cardbus controller. 


### -field PcmciaTopic

Indicates a Toshiba Topic cardbus controller. 


### -field PcmciaRicoh

Indicates a Ricoh cardbus controller. 


### -field PcmciaDatabookCB

Indicates a Databook cardbus controller. 


### -field PcmciaOpti

Indicates an OPTI cardbus controller. 


### -field PcmciaTrid

Indicates a TRID controller. 


### -field PcmciaO2Micro

Indicates an O2Micro cardbus controller. 


### -field PcmciaNEC

Indicates a Yenta-compliant NEC cardbus controller. 


### -field PcmciaNEC_98

Indicates a NEC cardbus controller.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537612">PCMCIA_SOCKET_INFORMATION</a>
 

 

