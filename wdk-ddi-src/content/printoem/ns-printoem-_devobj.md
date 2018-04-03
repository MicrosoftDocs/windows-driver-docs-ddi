---
UID: NS:printoem._DEVOBJ
title: "_DEVOBJ"
author: windows-driver-content
description: The DEVOBJ structure is used as an input argument to several of a rendering plug-in's COM interface methods.
old-location: print\devobj.htm
old-project: print
ms.assetid: cdcd0437-e4fc-4041-827f-caa3c435325c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDEVOBJ, DEVOBJ, DEVOBJ structure [Print Devices], _DEVOBJ, print.devobj, print_unidrv-pscript_rendering_defda1bb-3862-4b55-a7bf-38b040667c97.xml, printoem/DEVOBJ"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	printoem.h
api_name:
-	DEVOBJ
product:
- Windows
targetos: Windows
req.typenames: "*PDEVOBJ, DEVOBJ"
req.product: Windows 10 or later.
---

# _DEVOBJ structure


## -description


The DEVOBJ structure is used as an input argument to several of a rendering plug-in's COM interface methods.


## -struct-fields




### -field dwSize

Specifies the size, in bytes, of the DEVOBJ structure. Supplied by the Unidrv or Pscript5 driver.


### -field pdevOEM

Pointer to the rendering plug-in's private PDEV structure, as returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff554249">IPrintOemUni::EnablePDEV</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff553215">IPrintOemPS::EnablePDEV</a>. Supplied by the Unidrv or Pscript5 driver.


### -field hEngine

GDI handle to the physical device. This handle is received by the printer driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556181">DrvCompletePDEV</a> function, as the function's <i>hdev</i> argument.


### -field hPrinter

Spooler's handle to the printer. This handle is received by the printer driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556211">DrvEnablePDEV</a> function, as the function's <i>hDriver</i> argument.


### -field hOEM

Plug-in instance handle. Supplied by the Unidrv or Pscript5 driver.


### -field pPublicDM

Pointer to the printer's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure. Supplied by the Unidrv or Pscript5 driver.


### -field pOEMDM

Pointer to the rendering plug-in's private DEVMODEW structure members. Supplied by the Unidrv or Pscript5 driver.


### -field pDrvProcs


      Not used. In a previous version of the interface, this was a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548571">DRVPROCS</a> structure.


## -remarks



The DEVOBJ structure is accessible to graphics DDI hooking functions through the <a href="https://msdn.microsoft.com/library/windows/hardware/ff569901">SURFOBJ</a> structure's <b>dhpdev</b> member. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554249">IPrintOemUni::EnablePDEV</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff553215">IPrintOemPS::EnablePDEV</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556181">DrvCompletePDEV</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556211">DrvEnablePDEV</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553215">IPrintOemPS::EnablePDEV</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554249">IPrintOemUni::EnablePDEV</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569901">SURFOBJ</a>
 

 

