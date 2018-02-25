---
UID: NS:printoem._OEM_DMEXTRAHEADER
title: "_OEM_DMEXTRAHEADER"
author: windows-driver-content
description: The OEM_DMEXTRAHEADER structure must be used to define the first members of a set of private DEVMODEW structure members.
old-location: print\oem_dmextraheader.htm
old-project: print
ms.assetid: fecefdbc-3036-4991-900c-203ae8be254b
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *POEM_DMEXTRAHEADER, ,, A, D, E, H, M, O, OEM_DMEXTRAHEADER, OEM_DMEXTRAHEADER structure [Print Devices], P, POEM_DMEXTRAHEADER, POEM_DMEXTRAHEADER structure pointer [Print Devices], R, T, X, _, _OEM_DMEXTRAHEADER, print.oem_dmextraheader, print_unidrv-pscript_ui_f356f9c1-f867-4c53-8b12-be48da73de4f.xml, printoem/OEM_DMEXTRAHEADER, printoem/POEM_DMEXTRAHEADER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: printoem.h
req.include-header: Printoem.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	printoem.h
apiname:
-	OEM_DMEXTRAHEADER
product: Windows
targetos: Windows
req.typenames: OEM_DMEXTRAHEADER, *POEM_DMEXTRAHEADER
req.product: Windows 10 or later.
---

# _OEM_DMEXTRAHEADER structure


## -description


The OEM_DMEXTRAHEADER structure must be used to define the first members of a set of private <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure members.


## -syntax


````
typedef struct _OEM_DMEXTRAHEADER {
  DWORD dwSize;
  DWORD dwSignature;
  DWORD dwVersion;
} OEM_DMEXTRAHEADER, *POEM_DMEXTRAHEADER;
````


## -struct-fields




### -field dwSize

Total size, in bytes, of the added private DEVMODEW structure members, including the bytes contained in the OEM_DMEXTRAHEADER structure.


### -field dwSignature

Unique signature value that the plug-in also returns when its <a href="https://msdn.microsoft.com/library/windows/hardware/ff554178">IPrintOemUI::GetInfo</a> method receives the OEMGI_GETSIGNATURE flag.


### -field dwVersion

Version number of the user interface plug-in that is defining the private DEVMODEW structure members. The version format is developer-defined.


## -remarks



For more information about adding DEVMODEW structure members, see <a href="https://msdn.microsoft.com/7ce698f5-14c7-484d-be3d-b41c690b9576">Providing DEVMODE Structure Additions</a>. 



