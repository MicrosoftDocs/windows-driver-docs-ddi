---
UID: NS:printoem._OEMUIOBJ
title: OEMUIOBJ (printoem.h)
description: The OEMUIOBJ structure is used as an input argument to several of the methods exported by user interface plug-ins.
tech.root: print
ms.date: 08/12/2022
keywords: ["OEMUIOBJ structure"]
ms.keywords: "*POEMUIOBJ, OEMUIOBJ, OEMUIOBJ structure [Print Devices], POEMUIOBJ, POEMUIOBJ structure pointer [Print Devices], _OEMUIOBJ, print.oemuiobj, print_unidrv-pscript_ui_ce37eb2d-06c0-4bca-88f0-c5ab836c9fd3.xml, printoem/OEMUIOBJ, printoem/POEMUIOBJ"
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
targetos: Windows
req.typenames: OEMUIOBJ, *POEMUIOBJ
f1_keywords:
 - _OEMUIOBJ
 - printoem/_OEMUIOBJ
 - POEMUIOBJ
 - printoem/POEMUIOBJ
 - OEMUIOBJ
 - printoem/OEMUIOBJ
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - _OEMUIOBJ
 - POEMUIOBJ
 - OEMUIOBJ
---

## -description

The **OEMUIOBJ** structure is used as an input argument to several of the methods exported by user interface plug-ins.

## -struct-fields

### -field cbSize

Size of the **OEMUIOBJ** structure.

### -field pOemUIProcs

Pointer to a an [**OEMUIPROCS**](/windows-hardware/drivers/ddi/printoem/ns-printoem-_oemuiprocs) structure, which is a private, internal structure.

## -remarks

User interface plug-ins do not need to reference an **OEMUIOBJ** structure's members. Plug-ins receive a pointer to this structure as input to their [IPrintOemUI::DeviceCapabilities](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-devicecapabilities), [IPrintOemUI::DevQueryPrintEx](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-devqueryprintex) and [IPrintOemUI::QueryColorProfile](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-querycolorprofile) methods.

Additionally, the **OEMCUIPPARAM** structure contains an **OEMUIOBJ** structure pointer. Plug-ins must supply the received pointer when calling [IPrintOemDriverUI::DrvGetDriverSetting](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriverui-drvgetdriversetting) or [IPrintOemDriverUI::DrvUpdateUISetting](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriverui-drvupdateuisetting).
