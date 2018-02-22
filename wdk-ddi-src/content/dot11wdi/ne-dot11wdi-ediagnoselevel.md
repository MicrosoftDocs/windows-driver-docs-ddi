---
UID: NE:dot11wdi.eDiagnoseLevel
title: eDiagnoseLevel
author: windows-driver-content
description: The eDiagnoseLevel enumeration defines the diagnosis levels for adapter hang diagnosis.
old-location: netvista\wdiediagnoselevel.htm
old-project: netvista
ms.assetid: C19C250D-3C8D-4855-A8B3-82E139CE09BB
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: DiagnoseLevelFirmwareImageDump, eDiagnoseLevel enumeration [Network Drivers Starting with Windows Vista], eDiagnoseLevel, DiagnoseLevelNone, dot11wdi/DiagnoseLevelFirmwareImageDump, netvista.wdiediagnoselevel, dot11wdi/DiagnoseLevelNone, DiagnoseLevelDriverStateDump, dot11wdi/DiagnoseLevelDriverStateDump, dot11wdi/eDiagnoseLevel, dot11wdi/DiagnoseLevelHardwareRegisters, DiagnoseLevelHardwareRegisters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dot11wdi.h
apiname:
-	eDiagnoseLevel
product: Windows
targetos: Windows
req.typenames: eDiagnoseLevel
---

# eDiagnoseLevel enumeration


## -description


The eDiagnoseLevel enumeration defines the diagnosis levels for adapter hang diagnosis.


## -syntax


````
typedef enum _eDiagnoseLevel { 
  DiagnoseLevelNone               = 0,
  DiagnoseLevelHardwareRegisters  = 1,
  DiagnoseLevelFirmwareImageDump  = 2,
  DiagnoseLevelDriverStateDump    = 3
} eDiagnoseLevel;
````


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

<a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_adapter_hang_diagnose.md">MiniportWdiAdapterHangDiagnose</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20eDiagnoseLevel enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

