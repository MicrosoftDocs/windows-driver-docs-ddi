---
UID: NS:winddiui._DOCEVENT_ESCAPE
title: _DOCEVENT_ESCAPE (winddiui.h)
description: The DOCEVENT_ESCAPE structure is a container for values used as parameters for the ExtEscape function.
old-location: print\docevent_escape.htm
tech.root: print
ms.assetid: 54ac7c45-63a1-4003-8250-524e6f9e8d06
ms.date: 04/20/2018
keywords: ["DOCEVENT_ESCAPE structure"]
ms.keywords: "*PDOCEVENT_ESCAPE, DOCEVENT_ESCAPE, DOCEVENT_ESCAPE structure [Print Devices], PDOCEVENT_ESCAPE, PDOCEVENT_ESCAPE structure pointer [Print Devices], _DOCEVENT_ESCAPE, print.docevent_escape, print_interface-graphics_943033df-71a2-4689-a9fb-abd9feb4ea0d.xml, winddiui/DOCEVENT_ESCAPE, winddiui/PDOCEVENT_ESCAPE"
req.header: winddiui.h
req.include-header: Winddiui.h
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
req.typenames: DOCEVENT_ESCAPE, *PDOCEVENT_ESCAPE
f1_keywords:
 - _DOCEVENT_ESCAPE
 - winddiui/_DOCEVENT_ESCAPE
 - PDOCEVENT_ESCAPE
 - winddiui/PDOCEVENT_ESCAPE
 - DOCEVENT_ESCAPE
 - winddiui/DOCEVENT_ESCAPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winddiui.h
api_name:
 - DOCEVENT_ESCAPE
---

# _DOCEVENT_ESCAPE structure


## -description

The DOCEVENT_ESCAPE structure is a container for values used as parameters for the <b>ExtEscape</b> function.

## -struct-fields

### -field iEscape

Specifies the value of the <b>ExtEscape</b> function's <i>nEscape</i> parameter.

### -field cjInput

Specifies the value of the <b>ExtEscape</b> function's <i>cbInput</i> parameter.

### -field pvInData

Specifies the value of the <b>ExtEscape</b> function's <i>lpszInData</i> parameter.

## -remarks

The DOCEVENT_ESCAPE structure is defined for Windows XP and later.

This structure is used in conjunction with a call to <a href="/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentevent">DrvDocumentEvent</a> or <a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui2-documentevent">IPrintOemUI2::DocumentEvent</a>, in which the <i>iEsc</i> parameter is set to DOCUMENTEVENT_ESCAPE. Before calling either of these functions, the caller must fill in the members of this structure.

Refer to the Microsoft Windows SDK documentation for a description of the <b>ExtEscape</b> function and the three parameters that correspond to the members of this structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentevent">DrvDocumentEvent</a>



<a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui2-documentevent">IPrintOemUI2::DocumentEvent</a>