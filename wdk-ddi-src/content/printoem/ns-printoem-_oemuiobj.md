---
UID: NS:printoem._OEMUIOBJ
title: "_OEMUIOBJ"
author: windows-driver-content
description: The OEMUIOBJ structure is used as an input argument to several of the methods exported by user interface plug-ins.
old-location: print\oemuiobj.htm
old-project: print
ms.assetid: ba9252ec-3aef-4e8c-a335-bde33686beae
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: "_OEMUIOBJ, OEMUIOBJ structure [Print Devices], print_unidrv-pscript_ui_ce37eb2d-06c0-4bca-88f0-c5ab836c9fd3.xml, print.oemuiobj, OEMUIOBJ, printoem/POEMUIOBJ, *POEMUIOBJ, printoem/OEMUIOBJ, POEMUIOBJ, POEMUIOBJ structure pointer [Print Devices]"
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
-	OEMUIOBJ
product: Windows
targetos: Windows
req.typenames: OEMUIOBJ, *POEMUIOBJ
req.product: Windows 10 or later.
---

# _OEMUIOBJ structure


## -description


The OEMUIOBJ structure is used as an input argument to several of the methods exported by user interface plug-ins.


## -syntax


````
typedef struct _OEMUIOBJ {
  DWORD       cbSize;
  POEMUIPROCS pOemUIProcs;
} OEMUIOBJ, *POEMUIOBJ;
````


## -struct-fields




### -field cbSize

Size of the OEMUIOBJ structure.


### -field pOemUIProcs

Pointer to a an <a href="..\printoem\ns-printoem-_oemuiprocs.md">OEMUIPROCS</a> structure, which is a private, internal structure.


## -remarks



User interface plug-ins do not need to reference an OEMUIOBJ structure's members. Plug-ins receive a pointer to this structure as input to their <a href="https://msdn.microsoft.com/library/windows/hardware/ff554162">IPrintOemUI::DeviceCapabilities</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff554172">IPrintOemUI::DevQueryPrintEx</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff554186">IPrintOemUI::QueryColorProfile</a> methods. Additionally, the OEMCUIPPARAM structure contains an OEMUIOBJ structure pointer. Plug-ins must supply the received pointer when calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff553114">IPrintOemDriverUI::DrvGetDriverSetting</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff553115">IPrintOemDriverUI::DrvUpdateUISetting</a>.



