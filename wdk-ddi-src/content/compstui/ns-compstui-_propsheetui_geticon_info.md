---
UID: NS:compstui._PROPSHEETUI_GETICON_INFO
title: _PROPSHEETUI_GETICON_INFO (compstui.h)
description: The PROPSHEETUI_GETICON_INFO structure is used as an input parameter to an application's PFNPROPSHEETUI-typed function, when the function is called with a reason value of PROPSHEETUI_REASON_GET_ICON.
old-location: print\propsheetui_geticon_info.htm
tech.root: print
ms.assetid: 23c06f1c-0c8f-4055-a997-1ff94c4a541e
ms.date: 04/20/2018
ms.keywords: "*PPROPSHEETUI_GETICON_INFO, PPROPSHEETUI_GETICON_INFO, PPROPSHEETUI_GETICON_INFO structure pointer [Print Devices], PROPSHEETUI_GETICON_INFO, PROPSHEETUI_GETICON_INFO structure [Print Devices], _PROPSHEETUI_GETICON_INFO, compstui/PPROPSHEETUI_GETICON_INFO, compstui/PROPSHEETUI_GETICON_INFO, cpsuifnc_da228e66-0d1b-4d35-af1e-e1b99e56ad08.xml, print.propsheetui_geticon_info"
ms.topic: struct
req.header: compstui.h
req.include-header: Compstui.h
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
- compstui.h
api_name:
- PROPSHEETUI_GETICON_INFO
product:
- Windows
targetos: Windows
req.typenames: PROPSHEETUI_GETICON_INFO, *PPROPSHEETUI_GETICON_INFO
---

# _PROPSHEETUI_GETICON_INFO structure


## -description


The PROPSHEETUI_GETICON_INFO structure is used as an input parameter to an application's <a href="https://msdn.microsoft.com/library/windows/hardware/ff559812">PFNPROPSHEETUI</a>-typed function, when the function is called with a reason value of PROPSHEETUI_REASON_GET_ICON.


## -struct-fields




### -field cbSize

CPSUI-supplied size, in bytes, of the PROPSHEETUI_GETICON_INFO structure.


### -field Flags

Reserved.


### -field cxIcon

CPSUI-supplied icon width, in pixels.


### -field cyIcon

CPSUI-supplied icon height, in pixels.


### -field hIcon

Receives an application-supplied icon handle. If the icon is not loaded, the member must be set to zero.

