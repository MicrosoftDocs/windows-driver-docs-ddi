---
UID: NF:ntddk.PshedIsSystemWheaEnabled
title: PshedIsSystemWheaEnabled function (ntddk.h)
description: The PshedIsSystemWheaEnabled function returns a Boolean value that indicates whether the system is WHEA-enabled.
old-location: whea\pshedissystemwheaenabled.htm
tech.root: whea
ms.assetid: d9935605-dc5f-4987-8a5b-b2c2b358dbbf
ms.date: 02/20/2018
keywords: ["PshedIsSystemWheaEnabled function"]
ms.keywords: PshedIsSystemWheaEnabled, PshedIsSystemWheaEnabled function [WHEA Drivers and Applications], ntddk/PshedIsSystemWheaEnabled, whea.pshedissystemwheaenabled, whearef_492a4370-81bf-411b-bd87-2408f4551b18.xml
f1_keywords:
 - "ntddk/PshedIsSystemWheaEnabled"
 - "PshedIsSystemWheaEnabled"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
req.lib: Pshed.lib
req.dll: Pshed.dll
req.irql: Any
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Pshed.dll
api_name:
- PshedIsSystemWheaEnabled
product:
- Windows
targetos: Windows
req.typenames: 
---

# PshedIsSystemWheaEnabled function


## -description


The <b>PshedIsSystemWheaEnabled</b> function returns a Boolean value that indicates whether the system is WHEA-enabled.


## -returns



A Boolean value that indicates whether the system is WHEA-enabled.




## -remarks



A PSHED plug-in can call the <b>PshedIsSystemWheaEnabled</b> function before it calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin">PshedRegisterPlugin</a> function to verify that the system is WHEA-enabled.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin">PshedRegisterPlugin</a>
 

 

