---
UID: NE:dot11wdi.__unnamed_enum_0
title: eDiagnoseLevel (dot11wdi.h)
description: The eDiagnoseLevel enumeration defines the diagnosis levels for adapter hang diagnosis.
old-location: netvista\wdiediagnoselevel.htm
tech.root: netvista
ms.assetid: C19C250D-3C8D-4855-A8B3-82E139CE09BB
ms.date: 05/02/2018
ms.keywords: DiagnoseLevelDriverStateDump, DiagnoseLevelFirmwareImageDump, DiagnoseLevelHardwareRegisters, DiagnoseLevelNone, dot11wdi/DiagnoseLevelDriverStateDump, dot11wdi/DiagnoseLevelFirmwareImageDump, dot11wdi/DiagnoseLevelHardwareRegisters, dot11wdi/DiagnoseLevelNone, dot11wdi/eDiagnoseLevel, eDiagnoseLevel, eDiagnoseLevel enumeration [Network Drivers Starting with Windows Vista], netvista.wdiediagnoselevel
f1_keywords:
 - "dot11wdi/eDiagnoseLevel"
req.header: dot11wdi.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- dot11wdi.h
api_name:
- eDiagnoseLevel
product:
- Windows
targetos: Windows
req.typenames: eDiagnoseLevel
---

# eDiagnoseLevel enumeration


## -description


The eDiagnoseLevel enumeration defines the diagnosis levels for adapter hang diagnosis.


## -enum-fields




### -field DiagnoseLevelNone

No diagnostic information should be collected.


### -field DiagnoseLevelHardwareRegisters

Dump the hardware registers. This information is included in the LiveKD dump.


### -field DiagnoseLevelFirmwareImageDump

Dump the full firmware image and hardware registers. The firmware image should dump to a file.


### -field DiagnoseLevelDriverStateDump

Dump the driver state, full firmware image, and hardware registers. The driver state and full firmware image should dump to files.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_adapter_hang_diagnose">MiniportWdiAdapterHangDiagnose</a>
 

 

