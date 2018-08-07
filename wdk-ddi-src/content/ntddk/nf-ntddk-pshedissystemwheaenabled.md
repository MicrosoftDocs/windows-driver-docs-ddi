---
UID: NF:ntddk.PshedIsSystemWheaEnabled
title: PshedIsSystemWheaEnabled function
author: windows-driver-content
description: The PshedIsSystemWheaEnabled function returns a Boolean value that indicates whether the system is WHEA-enabled.
old-location: whea\pshedissystemwheaenabled.htm
tech.root: whea
ms.assetid: d9935605-dc5f-4987-8a5b-b2c2b358dbbf
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: PshedIsSystemWheaEnabled, PshedIsSystemWheaEnabled function [WHEA Drivers and Applications], ntddk/PshedIsSystemWheaEnabled, whea.pshedissystemwheaenabled, whearef_492a4370-81bf-411b-bd87-2408f4551b18.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Pshed.dll
api_name:
-	PshedIsSystemWheaEnabled
product:
- Windows
targetos: Windows
req.typenames: 
---

# PshedIsSystemWheaEnabled function


## -description


The <b>PshedIsSystemWheaEnabled</b> function returns a Boolean value that indicates whether the system is WHEA-enabled.


## -parameters






## -returns



A Boolean value that indicates whether the system is WHEA-enabled.




## -remarks



A PSHED plug-in can call the <b>PshedIsSystemWheaEnabled</b> function before it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559466">PshedRegisterPlugin</a> function to verify that the system is WHEA-enabled.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559466">PshedRegisterPlugin</a>
 

 

