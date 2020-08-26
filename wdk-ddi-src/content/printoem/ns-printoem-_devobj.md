---
UID: NS:printoem._DEVOBJ
title: _DEVOBJ (printoem.h)
description: The DEVOBJ structure is used as an input argument to several of a rendering plug-in's COM interface methods.
old-location: print\devobj.htm
tech.root: print
ms.assetid: cdcd0437-e4fc-4041-827f-caa3c435325c
ms.date: 04/20/2018
keywords: ["DEVOBJ structure"]
ms.keywords: "*PDEVOBJ, DEVOBJ, DEVOBJ structure [Print Devices], _DEVOBJ, print.devobj, print_unidrv-pscript_rendering_defda1bb-3862-4b55-a7bf-38b040667c97.xml, printoem/DEVOBJ"
f1_keywords:
 - "printoem/DEVOBJ"
 - "DEVOBJ"
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
- DEVOBJ
targetos: Windows
req.typenames: "*PDEVOBJ, DEVOBJ"
---

# _DEVOBJ structure


## -description


The DEVOBJ structure is used as an input argument to several of a rendering plug-in's COM interface methods.


## -struct-fields




### -field dwSize

Specifies the size, in bytes, of the DEVOBJ structure. Supplied by the Unidrv or Pscript5 driver.


### -field pdevOEM

Pointer to the rendering plug-in's private PDEV structure, as returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-enablepdev">IPrintOemUni::EnablePDEV</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemps-enablepdev">IPrintOemPS::EnablePDEV</a>. Supplied by the Unidrv or Pscript5 driver.


### -field hEngine

GDI handle to the physical device. This handle is received by the printer driver's <a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvcompletepdev">DrvCompletePDEV</a> function, as the function's <i>hdev</i> argument.


### -field hPrinter

Spooler's handle to the printer. This handle is received by the printer driver's <a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvenablepdev">DrvEnablePDEV</a> function, as the function's <i>hDriver</i> argument.


### -field hOEM

Plug-in instance handle. Supplied by the Unidrv or Pscript5 driver.


### -field pPublicDM

Pointer to the printer's <a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devmodew">DEVMODEW</a> structure. Supplied by the Unidrv or Pscript5 driver.


### -field pOEMDM

Pointer to the rendering plug-in's private DEVMODEW structure members. Supplied by the Unidrv or Pscript5 driver.


### -field pDrvProcs


      Not used. In a previous version of the interface, this was a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_drvprocs">DRVPROCS</a> structure.


## -remarks



The DEVOBJ structure is accessible to graphics DDI hooking functions through the <a href="https://docs.microsoft.com/windows/win32/api/winddi/ns-winddi-_surfobj">SURFOBJ</a> structure's <b>dhpdev</b> member. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-enablepdev">IPrintOemUni::EnablePDEV</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemps-enablepdev">IPrintOemPS::EnablePDEV</a>.




## -see-also




<a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devmodew">DEVMODEW</a>



<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvcompletepdev">DrvCompletePDEV</a>



<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvenablepdev">DrvEnablePDEV</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemps-enablepdev">IPrintOemPS::EnablePDEV</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-enablepdev">IPrintOemUni::EnablePDEV</a>



<a href="https://docs.microsoft.com/windows/win32/api/winddi/ns-winddi-_surfobj">SURFOBJ</a>
 

 

