---
UID: NS:printoem._OEMDMPARAM
title: OEMDMPARAM (printoem.h)
description: The OEMDMPARAM structure is used as an input parameter to the IPrintOemUI::DevMode, IPrintOemUni::DevMode, and IPrintOemPS::DevMode methods.
tech.root: print
ms.date: 08/12/2022
keywords: ["OEMDMPARAM structure"]
ms.keywords: "*POEMDMPARAM, OEMDMPARAM, OEMDMPARAM structure [Print Devices], POEMDMPARAM, POEMDMPARAM structure pointer [Print Devices], _OEMDMPARAM, print.oemdmparam, print_unidrv-pscript_ui_49535272-ec29-4133-8105-0ce9b31808a2.xml, printoem/OEMDMPARAM, printoem/POEMDMPARAM"
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
req.typenames: OEMDMPARAM, *POEMDMPARAM
f1_keywords:
 - _OEMDMPARAM
 - printoem/_OEMDMPARAM
 - POEMDMPARAM
 - printoem/POEMDMPARAM
 - OEMDMPARAM
 - printoem/OEMDMPARAM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - _OEMDMPARAM
 - POEMDMPARAM
 - OEMDMPARAM
---

## -description

The **OEMDMPARAM** structure is used as an input parameter to the [IPrintOemUI::DevMode](../prcomoem/nf-prcomoem-iprintoemui-devmode.md), [IPrintOemUni::DevMode](../prcomoem/nf-prcomoem-iprintoemuni-devmode.md), and [IPrintOemPS::DevMode](../prcomoem/nf-prcomoem-iprintoemps-devmode.md) methods.

## -struct-fields

### -field cbSize

Contains the size of the **OEMDMPARAM** structure. Supplied by the Unidrv or Pscript5 driver.

### -field pdriverobj

#### For IPrintOemUI::DevMode

Not used.

#### For IPrintOemUni::DevMode and IPrintOemPS::DevMode

Pointer to a [**DEVOBJ**](./ns-printoem-_devobj.md) structure.

### -field hPrinter

Handle to the printer device. Supplied by the Unidrv or Pscript5 driver.

### -field hModule

Handle to the user interface plug-in module. Supplied by the Unidrv or Pscript5 driver.

### -field pPublicDMIn

Pointer to the printer device's public **DEVMODEW** structure. Supplied by the Unidrv or Pscript5 driver. (Valid if the **DevMode** method's *dwMode* value is OEMDM_DEFAULT, OEMDM_CONVERT, or OEMDM_MERGE.)

### -field pPublicDMOut

Pointer to a location to receive public **DEVMODEW** structure contents. Supplied by the Unidrv or Pscript5 driver. (Valid if the **DevMode** method's *dwMode* value is OEMDM_CONVERT or OEMDM_MERGE.)

### -field pOEMDMIn

Pointer to a set of private **DEVMODEW** members. Supplied by the Unidrv or Pscript5 driver. (Valid if the **DevMode** method's *dwMode* value is OEMDM_CONVERT or OEMDM_MERGE.)

### -field pOEMDMOut

Pointer to memory allocated to receive modified private **DEVMODEW** contents. Supplied by the Unidrv or Pscript5 driver. (Valid if the **DevMode** method's *dwMode* value is OEMDM_DEFAULT, OEMDM_CONVERT or OEMDM_MERGE.)

### -field cbBufSize

On input, contains the caller-supplied size of memory space pointed to by **pOEMDMOut**. (Not valid if the **DevMode** method's *dwMode* value is OEMDM_SIZE.)

On output, contains the method-supplied size of the current version of the private **DEVMODEW** section. (Only used if the **DevMode** method's *dwMode* value is OEMDM_SIZE.)

## -remarks

For more information about the use of **OEMDMPARAM** structure members, see the description of the [IPrintOemUI::DevMode](../prcomoem/nf-prcomoem-iprintoemui-devmode.md) method.