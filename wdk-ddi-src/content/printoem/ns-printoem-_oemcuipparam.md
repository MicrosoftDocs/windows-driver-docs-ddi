---
UID: NS:printoem._OEMCUIPPARAM
title: OEMCUIPPARAM (printoem.h)
description: The OEMCUIPPARAM structure is used as an input parameter to a user interface plug-in's IPrintOemUI::CommonUIProp method.
tech.root: print
ms.date: 08/12/2022
keywords: ["OEMCUIPPARAM structure"]
ms.keywords: "*POEMCUIPPARAM, OEMCUIPPARAM, OEMCUIPPARAM structure [Print Devices], _OEMCUIPPARAM, print.oemcuipparam, print_unidrv-pscript_ui_6ea92d10-0152-4bb2-a79b-0f6c29507e8c.xml, printoem/OEMCUIPPARAM"
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
req.typenames: "*POEMCUIPPARAM, OEMCUIPPARAM"
f1_keywords:
 - _OEMCUIPPARAM
 - printoem/_OEMCUIPPARAM
 - POEMCUIPPARAM
 - printoem/POEMCUIPPARAM
 - OEMCUIPPARAM
 - printoem/OEMCUIPPARAM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - _OEMCUIPPARAM
 - POEMCUIPPARAM
 - OEMCUIPPARAM
---

## -description

The **OEMCUIPPARAM** structure is used as an input parameter to a user interface plug-in's [IPrintOemUI::CommonUIProp](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-commonuiprop) method.

## -struct-fields

### -field cbSize

Size of the **OEMCUIPPARAM** structure. Supplied by the Unidrv or Pscript5 driver.

### -field poemuiobj

Pointer to an [OEMUIOBJ](/windows-hardware/drivers/ddi/printoem/ns-printoem-_oemuiobj) structure.

### -field hPrinter

Handle to the printer. Supplied by the Unidrv or Pscript5 driver.

### -field pPrinterName

String containing the printer name. Supplied by the Unidrv or Pscript5 driver.

### -field hModule

Handle to the user interface plug-in. Supplied by the Unidrv or Pscript5 driver.

### -field hOEMHeap

Handle to a heap from which space can be allocated by calling the **HeapAlloc** function (described in the Microsoft Windows SDK documentation). Supplied by the Unidrv or Pscript5 driver.

### -field pPublicDM

Pointer to the printer's public **DEVMODEW** structure. Valid only if the [IPrintOemUI::CommonUIProp](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-commonuiprop) method's *dwMode* argument is OEMCUIP_DOCPROP. Supplied by the Unidrv or Pscript5 driver.

### -field pOEMDM

Pointer to the user interface plug-in's private **DEVMODEW** members. Valid only if the **IPrintOemUI::CommonUIProp** method's *dwMode* argument is OEMCUIP_DOCPROP. Supplied by the Unidrv or Pscript5 driver.

### -field dwFlags

#### For calls to IPrintOemUI::CommonUIProp with its dwMode parameter set to OEMCUIP_DOCPROP

Contains the contents of the **fMode** member of the [DOCUMENTPROPERTYHEADER](/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_documentpropertyheader) structure received by the printer driver's [DrvDocumentPropertySheets](/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentpropertysheets) function.

#### For calls to IPrintOemUI::CommonUIProp with its dwMode parameter set to OEMCUIP_PRNPROP

Contains the contents of the **Flags** member of the DEVICEPROPERTYHEADER structure received by the printer driver's [DrvDevicePropertySheets](/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdevicepropertysheets) function.

### -field pDrvOptItems

Pointer to the printer driver's [**OPTITEM**](/windows-hardware/drivers/ddi/compstui/ns-compstui-_optitem) array. Not valid the first time **IPrintOemUI::CommonUIProp** is called. Supplied by the Unidrv or Pscript5 driver.

### -field cDrvOptItems

Count of OPTITEM structures in the array pointed to by **pDrvOptItems**. Supplied by the Unidrv or Pscript5 driver.

### -field pOEMOptItems

Pointer to an array of **OPTITEM** structures. Supplied by **IPrintOemUI::CommonUIProp** caller. The second time the **IPrintOemUI::CommonUIProp** method is called, it must place **OPTITEM** structures defined by the user interface plug-in in this array, and it must place the structure count in **cOEMOptItems**. For each OPTITEM structure placed in the array, you must do the following:

- Set the **OPTITEM** structure's **DMPubID** member either to one of the predefined values or to a value greater than DMPUB_USER. If you use any predefined values, you must search through the entire **OPTITEM** array for structures already containing those values, and you must set their OPTIF_HIDE flags.

- Allocate space for **OPTTYPES** and **OPTPARAMS** structures by calling the Windows SDK **HeapAlloc** function, using the handle contained in the OEMCUIPPARAM structure's **hOEMHeap** member. The printer driver deallocates this space when it is no longer needed.

Not valid the first time **IPrintOemUI::CommonUIProp** is called.

### -field cOEMOptItems

Count of OPTITEM structures contained in the array pointed by **pOEMOptItems**. Supplied by the Unidrv or Pscript5 driver.

The first time the **IPrintOemUI::CommonUIProp** method is called, the caller-supplied value for **cOEMOptItems** is zero. The **IPrintOemUI::CommonUIProp** method must change this value to indicate the number of OPTITEM structures that the method supplies. The second time it is called, **IPrintOemUI::CommonUIProp** must supply the number of OPTITEM structures actually added to the array pointed to by **pOEMOptItems**.

### -field pOEMUserData

Used by the **IPrintOemUI::CommonUIProp** method, the second time it is called, to provide the **OEMCUIPCallback** function with optional extra input information.

### -field OEMCUIPCallback

Used by the **IPrintOemUI::CommonUIProp** method, the second time it is called, to return the address of a callback function of type [OEMCUIPCALLBACK](/windows-hardware/drivers/ddi/printoem/nc-printoem-oemcuipcallback).

## -remarks

A user interface plug-in receives this structure's address as an input argument to both its [IPrintOemUI::CommonUIProp](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-commonuiprop) method and its [OEMCUIPCALLBACK](/windows-hardware/drivers/ddi/printoem/nc-printoem-oemcuipcallback)-typed callback function.

For additional information about the use of this structure and associated functions, see [User Interface Plug-Ins](/windows-hardware/drivers/print/user-interface-plug-ins).
