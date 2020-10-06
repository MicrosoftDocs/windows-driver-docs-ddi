---
UID: NS:printoem._OEMCUIPPARAM
title: _OEMCUIPPARAM (printoem.h)
description: The OEMCUIPPARAM structure is used as an input parameter to a user interface plug-in's IPrintOemUI::CommonUIProp method.
old-location: print\oemcuipparam.htm
tech.root: print
ms.assetid: 178b635c-0916-44f5-87a3-a2766601dcab
ms.date: 04/20/2018
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
 - OEMCUIPPARAM
---

# _OEMCUIPPARAM structure


## -description

The OEMCUIPPARAM structure is used as an input parameter to a user interface plug-in's <a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-commonuiprop">IPrintOemUI::CommonUIProp</a> method.

## -struct-fields

### -field cbSize

Size of the OEMCUIPPARAM structure. Supplied by the Unidrv or Pscript5 driver.

### -field poemuiobj

Pointer to an <a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_oemuiobj">OEMUIOBJ</a> structure.

### -field hPrinter

Handle to the printer. Supplied by the Unidrv or Pscript5 driver.

### -field pPrinterName

String containing the printer name. Supplied by the Unidrv or Pscript5 driver.

### -field hModule

Handle to the user interface plug-in. Supplied by the Unidrv or Pscript5 driver.

### -field hOEMHeap

Handle to a heap from which space can be allocated by calling the <b>HeapAlloc</b> function (described in the Microsoft Windows SDK documentation). Supplied by the Unidrv or Pscript5 driver.

### -field pPublicDM

Pointer to the printer's public DEVMODEW structure. Valid only if the <a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-commonuiprop">IPrintOemUI::CommonUIProp</a> method's <i>dwMode</i> argument is OEMCUIP_DOCPROP. Supplied by the Unidrv or Pscript5 driver.

### -field pOEMDM

Pointer to the user interface plug-in's private DEVMODEW members. Valid only if the <b>IPrintOemUI::CommonUIProp</b> method's <i>dwMode</i> argument is OEMCUIP_DOCPROP. Supplied by the Unidrv or Pscript5 driver.

### -field dwFlags

#### For calls to IPrintOemUI::CommonUIProp with its dwMode parameter set to OEMCUIP_DOCPROP:

Contains the contents of the <b>fMode</b> member of the <a href="/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_documentpropertyheader">DOCUMENTPROPERTYHEADER</a> structure received by the printer driver's <a href="/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentpropertysheets">DrvDocumentPropertySheets</a> function.



#### For calls to IPrintOemUI::CommonUIProp with its dwMode parameter set to OEMCUIP_PRNPROP:

Contains the contents of the <b>Flags</b> member of the DEVICEPROPERTYHEADER structure received by the printer driver's <a href="/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdevicepropertysheets">DrvDevicePropertySheets</a> function.

### -field pDrvOptItems

Pointer to the printer driver's <a href="/windows-hardware/drivers/ddi/compstui/ns-compstui-_optitem">OPTITEM</a> array. Not valid the first time <b>IPrintOemUI::CommonUIProp</b> is called. Supplied by the Unidrv or Pscript5 driver.

### -field cDrvOptItems

Count of OPTITEM structures in the array pointed to by <b>pDrvOptItems</b>. Supplied by the Unidrv or Pscript5 driver.

### -field pOEMOptItems

Pointer to an array of OPTITEM structures. Supplied by <b>IPrintOemUI::CommonUIProp</b> caller. The second time the <b>IPrintOemUI::CommonUIProp</b> method is called, it must place OPTITEM structures defined by the user interface plug-in in this array, and it must place the structure count in <b>cOEMOptItems</b>. For each OPTITEM structure placed in the array, you must do the following:

<ul>
<li>
Set the OPTITEM structure's <b>DMPubID</b> member either to one of the predefined values or to a value greater than DMPUB_USER. If you use any predefined values, you must search through the entire OPTITEM array for structures already containing those values, and you must set their OPTIF_HIDE flags.

</li>
<li>
Allocate space for OPTTYPES and OPTPARAMS structures by calling the Windows SDK <b>HeapAlloc</b> function, using the handle contained in the OEMCUIPPARAM structure's <b>hOEMHeap</b> member. The printer driver deallocates this space when it is no longer needed.

</li>
</ul>
Not valid the first time <b>IPrintOemUI::CommonUIProp</b> is called.

### -field cOEMOptItems

Count of OPTITEM structures contained in the array pointed by <b>pOEMOptItems</b>. Supplied by the Unidrv or Pscript5 driver.

The first time the <b>IPrintOemUI::CommonUIProp</b> method is called, the caller-supplied value for <b>cOEMOptItems</b> is zero. The <b>IPrintOemUI::CommonUIProp</b> method must change this value to indicate the number of OPTITEM structures that the method supplies. The second time it is called, <b>IPrintOemUI::CommonUIProp</b> must supply the number of OPTITEM structures actually added to the array pointed to by <b>pOEMOptItems</b>.

### -field pOEMUserData

Used by the <b>IPrintOemUI::CommonUIProp</b> method, the second time it is called, to provide the <b>OEMCUIPCallback</b> function with optional extra input information.

### -field OEMCUIPCallback

Used by the <b>IPrintOemUI::CommonUIProp</b> method, the second time it is called, to return the address of a callback function of type <a href="/windows-hardware/drivers/ddi/printoem/nc-printoem-oemcuipcallback">OEMCUIPCALLBACK</a>.

## -remarks

A user interface plug-in receives this structure's address as an input argument to both its <a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-commonuiprop">IPrintOemUI::CommonUIProp</a> method and its <a href="/windows-hardware/drivers/ddi/printoem/nc-printoem-oemcuipcallback">OEMCUIPCALLBACK</a>-typed callback function.

For additional information about the use of this structure and associated functions, see <a href="/windows-hardware/drivers/print/user-interface-plug-ins">User Interface Plug-Ins</a>.