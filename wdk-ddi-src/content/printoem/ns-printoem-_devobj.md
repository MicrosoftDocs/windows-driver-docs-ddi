---
UID: NS:printoem._DEVOBJ
title: DEVOBJ (printoem.h)
description: The DEVOBJ structure is used as an input argument to several of a rendering plug-in's COM interface methods.
tech.root: print
ms.date: 08/12/2022
keywords: ["DEVOBJ structure"]
ms.keywords: "*PDEVOBJ, DEVOBJ, DEVOBJ structure [Print Devices], _DEVOBJ, print.devobj, print_unidrv-pscript_rendering_defda1bb-3862-4b55-a7bf-38b040667c97.xml, printoem/DEVOBJ"
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
req.typenames: "*PDEVOBJ, DEVOBJ"
f1_keywords:
 - _DEVOBJ
 - printoem/_DEVOBJ
 - PDEVOBJ
 - printoem/PDEVOBJ
 - DEVOBJ
 - printoem/DEVOBJ
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - _DEVOBJ
 - PDEVOBJ
 - DEVOBJ
---

## -description

The **DEVOBJ** structure is used as an input argument to several of a rendering plug-in's COM interface methods.

## -struct-fields

### -field dwSize

Specifies the size, in bytes, of the **DEVOBJ** structure. Supplied by the Unidrv or Pscript5 driver.

### -field pdevOEM

Pointer to the rendering plug-in's private PDEV structure, as returned by [IPrintOemUni::EnablePDEV](../prcomoem/nf-prcomoem-iprintoemuni-enablepdev.md) or [IPrintOemPS::EnablePDEV](../prcomoem/nf-prcomoem-iprintoemps-enablepdev.md). Supplied by the Unidrv or Pscript5 driver.

### -field hEngine

GDI handle to the physical device. This handle is received by the printer driver's [DrvCompletePDEV](/windows/win32/api/winddi/nf-winddi-drvcompletepdev) function, as the function's *hdev* argument.

### -field hPrinter

Spooler's handle to the printer. This handle is received by the printer driver's [DrvEnablePDEV](/windows/win32/api/winddi/nf-winddi-drvenablepdev) function, as the function's *hDriver* argument.

### -field hOEM

Plug-in instance handle. Supplied by the Unidrv or Pscript5 driver.

### -field pPublicDM

Pointer to the printer's [DEVMODEW](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure. Supplied by the Unidrv or Pscript5 driver.

### -field pOEMDM

Pointer to the rendering plug-in's private DEVMODEW structure members. Supplied by the Unidrv or Pscript5 driver.

### -field pDrvProcs

      Not used. In a previous version of the interface, this was a pointer to a [DRVPROCS](./ns-printoem-_drvprocs.md) structure.

## -remarks

The **DEVOBJ** structure is accessible to graphics DDI hooking functions through the [SURFOBJ](/windows/win32/api/winddi/ns-winddi-surfobj) structure's **dhpdev** member. For more information, see [IPrintOemUni::EnablePDEV](../prcomoem/nf-prcomoem-iprintoemuni-enablepdev.md) or [IPrintOemPS::EnablePDEV](../prcomoem/nf-prcomoem-iprintoemps-enablepdev.md).

## -see-also

[DEVMODEW](/windows/win32/api/wingdi/ns-wingdi-devmodew)

[DrvCompletePDEV](/windows/win32/api/winddi/nf-winddi-drvcompletepdev)

[DrvEnablePDEV](/windows/win32/api/winddi/nf-winddi-drvenablepdev)

[IPrintOemPS::EnablePDEV](../prcomoem/nf-prcomoem-iprintoemps-enablepdev.md)

[IPrintOemUni::EnablePDEV](../prcomoem/nf-prcomoem-iprintoemuni-enablepdev.md)

[SURFOBJ](/windows/win32/api/winddi/ns-winddi-surfobj)