---
UID: NS:winddiui._DOCEVENT_CREATEDCPRE
title: _DOCEVENT_CREATEDCPRE (winddiui.h)
description: The DOCEVENT_CREATEDCPRE structure contains a set of values used in certain calls to DrvDocumentEvent and IPrintOemUI2::DocumentEvent.
old-location: print\docevent_createdcpre.htm
tech.root: print
ms.assetid: ad95d11e-c170-4c21-a498-45e38f41cbbb
ms.date: 04/20/2018
keywords: ["_DOCEVENT_CREATEDCPRE structure"]
ms.keywords: "*PDCEVENT_CREATEDCPRE, DOCEVENT_CREATEDCPRE, DOCEVENT_CREATEDCPRE structure [Print Devices], PDCEVENT_CREATEDCPRE, PDCEVENT_CREATEDCPRE structure pointer [Print Devices], _DOCEVENT_CREATEDCPRE, print.docevent_createdcpre, print_interface-graphics_cb3123e7-a842-4fd8-b01a-4402c63bb43a.xml, winddiui/DOCEVENT_CREATEDCPRE, winddiui/PDCEVENT_CREATEDCPRE"
f1_keywords:
 - "winddiui/DOCEVENT_CREATEDCPRE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- winddiui.h
api_name:
- DOCEVENT_CREATEDCPRE
product:
- Windows
targetos: Windows
req.typenames: DOCEVENT_CREATEDCPRE, *PDCEVENT_CREATEDCPRE
---

# _DOCEVENT_CREATEDCPRE structure


## -description


The DOCEVENT_CREATEDCPRE structure contains a set of values used in certain calls to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentevent">DrvDocumentEvent</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui2-documentevent">IPrintOemUI2::DocumentEvent</a>.


## -struct-fields




### -field pszDriver

Reserved for system use. Set to zero.


### -field pszDevice

Pointer to the first byte of a Unicode string that contains either the device name or the port name, depending on whether print spooling is enabled or disabled. If the print job is being sent directly to the printer (spooling is disabled), this member contains the printer name. If a print job is being spooled, this member contains the port name. 


### -field pdm

Pointer to a <a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devmodew">DEVMODEW</a> structure passed to either CreateIC or CreateDC (both described in the Microsoft Windows SDK documentation). This member can be <b>NULL</b>.


### -field bIC

Specifies whether the DEVMODEW structure pointed to by the <b>pdm</b> member is being passed to CreateIC or CreateDC. If <b>TRUE</b>, CreateIC is being called. If <b>FALSE</b>, CreateDC is being called.


## -remarks



The DOCEVENT_CREATEDCPRE structure is defined for Windows XP and later.

This structure is used in conjunction with a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentevent">DrvDocumentEvent</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui2-documentevent">IPrintOemUI2::DocumentEvent</a>, in which the <i>iEsc</i> parameter is set to DOCUMENTEVENT_CREATEDCPRE. Before calling either of these functions, the caller must fill in the members of this structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentevent">DrvDocumentEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui2-documentevent">IPrintOemUI2::DocumentEvent</a>
 

 

