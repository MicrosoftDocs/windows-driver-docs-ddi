---
UID: NS:printoem._OEMUIOBJ
title: _OEMUIOBJ (printoem.h)
description: The OEMUIOBJ structure is used as an input argument to several of the methods exported by user interface plug-ins.
old-location: print\oemuiobj.htm
tech.root: print
ms.assetid: ba9252ec-3aef-4e8c-a335-bde33686beae
ms.date: 04/20/2018
keywords: ["_OEMUIOBJ structure"]
ms.keywords: "*POEMUIOBJ, OEMUIOBJ, OEMUIOBJ structure [Print Devices], POEMUIOBJ, POEMUIOBJ structure pointer [Print Devices], _OEMUIOBJ, print.oemuiobj, print_unidrv-pscript_ui_ce37eb2d-06c0-4bca-88f0-c5ab836c9fd3.xml, printoem/OEMUIOBJ, printoem/POEMUIOBJ"
f1_keywords:
 - "printoem/OEMUIOBJ"
 - "OEMUIOBJ"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- printoem.h
api_name:
- OEMUIOBJ
targetos: Windows
req.typenames: OEMUIOBJ, *POEMUIOBJ
---

# _OEMUIOBJ structure


## -description


The OEMUIOBJ structure is used as an input argument to several of the methods exported by user interface plug-ins.


## -struct-fields




### -field cbSize

Size of the OEMUIOBJ structure.


### -field pOemUIProcs

Pointer to a an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_oemuiprocs">OEMUIPROCS</a> structure, which is a private, internal structure.


## -remarks



User interface plug-ins do not need to reference an OEMUIOBJ structure's members. Plug-ins receive a pointer to this structure as input to their <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-devicecapabilities">IPrintOemUI::DeviceCapabilities</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-devqueryprintex">IPrintOemUI::DevQueryPrintEx</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-querycolorprofile">IPrintOemUI::QueryColorProfile</a> methods. Additionally, the OEMCUIPPARAM structure contains an OEMUIOBJ structure pointer. Plug-ins must supply the received pointer when calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriverui-drvgetdriversetting">IPrintOemDriverUI::DrvGetDriverSetting</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriverui-drvupdateuisetting">IPrintOemDriverUI::DrvUpdateUISetting</a>.



