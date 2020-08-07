---
UID: NS:printoem._OEMDMPARAM
title: _OEMDMPARAM (printoem.h)
description: The OEMDMPARAM structure is used as an input parameter to the IPrintOemUI::DevMode, IPrintOemUni::DevMode, and IPrintOemPS::DevMode methods.
old-location: print\oemdmparam.htm
tech.root: print
ms.assetid: 625980d1-47eb-4427-a9e8-967b1873bbd6
ms.date: 04/20/2018
keywords: ["OEMDMPARAM structure"]
ms.keywords: "*POEMDMPARAM, OEMDMPARAM, OEMDMPARAM structure [Print Devices], POEMDMPARAM, POEMDMPARAM structure pointer [Print Devices], _OEMDMPARAM, print.oemdmparam, print_unidrv-pscript_ui_49535272-ec29-4133-8105-0ce9b31808a2.xml, printoem/OEMDMPARAM, printoem/POEMDMPARAM"
f1_keywords:
 - "printoem/OEMDMPARAM"
 - "OEMDMPARAM"
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
- OEMDMPARAM
targetos: Windows
req.typenames: OEMDMPARAM, *POEMDMPARAM
---

# _OEMDMPARAM structure


## -description


The OEMDMPARAM structure is used as an input parameter to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-devmode">IPrintOemUI::DevMode</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-devmode">IPrintOemUni::DevMode</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemps-devmode">IPrintOemPS::DevMode</a> methods.


## -struct-fields




### -field cbSize

Contains the size of the OEMDMPARAM structure. Supplied by the Unidrv or Pscript5 driver.


### -field pdriverobj





#### For IPrintOemUI::DevMode:

Not used.



#### For IPrintOemUni::DevMode and IPrintOemPS::DevMode:

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_devobj">DEVOBJ</a> structure.


### -field hPrinter

Handle to the printer device. Supplied by the Unidrv or Pscript5 driver.


### -field hModule

Handle to the user interface plug-in module. Supplied by the Unidrv or Pscript5 driver.


### -field pPublicDMIn

Pointer to the printer device's public DEVMODEW structure. Supplied by the Unidrv or Pscript5 driver. (Valid if the <b>DevMode</b> method's <i>dwMode</i> value is OEMDM_DEFAULT, OEMDM_CONVERT, or OEMDM_MERGE.)


### -field pPublicDMOut

Pointer to a location to receive public DEVMODEW structure contents. Supplied by the Unidrv or Pscript5 driver. (Valid if the <b>DevMode</b> method's <i>dwMode</i> value is OEMDM_CONVERT or OEMDM_MERGE.)


### -field pOEMDMIn

Pointer to a set of private DEVMODEW members. Supplied by the Unidrv or Pscript5 driver. (Valid if the <b>DevMode</b> method's <i>dwMode</i> value is OEMDM_CONVERT or OEMDM_MERGE.)


### -field pOEMDMOut

Pointer to memory allocated to receive modified private DEVMODEW contents. Supplied by the Unidrv or Pscript5 driver. (Valid if the <b>DevMode</b> method's <i>dwMode</i> value is OEMDM_DEFAULT, OEMDM_CONVERT or OEMDM_MERGE.)


### -field cbBufSize

On input, contains the caller-supplied size of memory space pointed to by <b>pOEMDMOut</b>. (Not valid if the <b>DevMode</b> method's <i>dwMode</i> value is OEMDM_SIZE.)

On output, contains the method-supplied size of the current version of the private DEVMODEW section. (Only used if the <b>DevMode</b> method's <i>dwMode</i> value is OEMDM_SIZE.)


## -remarks



For more information about the use of OEMDMPARAM structure members, see the description of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-devmode">IPrintOemUI::DevMode</a> method.



