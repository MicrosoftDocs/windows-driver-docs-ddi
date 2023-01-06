---
UID: NF:prcomoem.IPrintOemUni.EnableDriver
title: IPrintOemUni::EnableDriver (prcomoem.h)
description: The IPrintOemUni::EnableDriver method allows a rendering plug-in for Unidrv to hook out some graphics DDI functions.
tech.root: print
ms.date: 01/04/2023
keywords: ["IPrintOemUni::EnableDriver"]
ms.keywords: EnableDriver, EnableDriver method [Print Devices], EnableDriver method [Print Devices],IPrintOemUni interface, IPrintOemUni interface [Print Devices],EnableDriver method, IPrintOemUni.EnableDriver, IPrintOemUni::EnableDriver, prcomoem/IPrintOemUni::EnableDriver, print.iprintoemuni_enabledriver, print_unidrv-pscript_rendering_804d9469-6ac6-4220-b123-25a2d226b609.xml
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
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
req.typenames: 
f1_keywords:
 - IPrintOemUni::EnableDriver
 - prcomoem/IPrintOemUni::EnableDriver
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Prcomoem.h
api_name:
 - IPrintOemUni::EnableDriver
---

## -description

The **IPrintOemUni::EnableDriver** method allows a rendering plug-in for [Unidrv](/windows-hardware/drivers/print/microsoft-universal-printer-driver) to hook out some graphics DDI functions.

## -parameters

### -param DriverVersion

Caller-supplied interface version number. This value is defined by PRINTER_OEMINTF_VERSION, in printoem.h.

### -param cbSize

Caller-supplied size, in bytes, of the structure pointed to by *pded*.

### -param pded

Caller-supplied pointer to a [DRVENABLEDATA](/windows/win32/api/winddi/ns-winddi-drvenabledata) structure.

## -returns

The method must return one of the following values.

| Return code | Description |
|---|---|
| **S_OK** | The operation succeeded. |
| **E_FAIL** | The operation failed |

## -remarks

A rendering plug-in for Unidrv must implement the **IPrintOemUni::EnableDriver** method.

The **IPrintOemUni::EnableDriver** method allows a rendering plug-in to perform the same types of operations as the [DrvEnableDriver](/windows/win32/api/winddi/nf-winddi-drvenabledriver) function that is exported by printer graphics DLLs.

Like the **DrvEnableDriver** function, the **IPrintOemUni::EnableDriver** method is responsible for providing addresses of internally supported graphics DDI functions, known as hooking functions. It can also perform other one-time initialization operations. Unlike the **DrvEnableDriver** function, implementation of **IPrintOemUni::EnableDriver** is optional.

If you implement **IPrintOemUni::EnableDriver**, you must also implement [IPrintOemUni::DisableDriver](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-disabledriver). Actions begun in the former method might need to be completed in the latter method. For example, if a large buffer is allocated in **IPrintOemUni::EnableDriver**, but not deallocated in **IPrintOemUni::DisableDriver**, a memory leak can occur.

The method should fill the supplied [DRVENABLEDATA](/windows/win32/api/winddi/ns-winddi-drvenabledata) structure and allocate an array of [DRVFN](/windows/win32/api/winddi/ns-winddi-drvfn) structures. It should fill the array with pointers to hooking functions, along with winddi.h-defined index values that identify the hooked out graphics DDI functions.

A rendering plug-in for Unidrv can hook out a graphics DDI function only if the Unidrv driver defines the function. The following graphics DDI functions are defined in Unidrv and/or Pscript5 and can therefore be hooked out:

- [DrvAlphaBlend](/windows/win32/api/winddi/nf-winddi-drvalphablend)

- [DrvBitBlt](/windows/win32/api/winddi/nf-winddi-drvbitblt)

- [DrvCopyBits](/windows/win32/api/winddi/nf-winddi-drvcopybits)

- [DrvDitherColor](/windows/win32/api/winddi/nf-winddi-drvdithercolor)

- [DrvEndDoc](/windows/win32/api/winddi/nf-winddi-drvenddoc)

- [DrvEscape](/windows/win32/api/winddi/nf-winddi-drvescape)

- [DrvFillPath](/windows/win32/api/winddi/nf-winddi-drvfillpath)

- [DrvFontManagement](/windows/win32/api/winddi/nf-winddi-drvfontmanagement)

- [DrvGetGlyphMode](/windows/win32/api/winddi/nf-winddi-drvgetglyphmode)

- [DrvGradientFill](/windows/win32/api/winddi/nf-winddi-drvgradientfill)

- [DrvIcmCreateColorTransform](/windows/win32/api/winddi/nf-winddi-drvicmcreatecolortransform)

- [DrvIcmDeleteColorTransform](/windows/win32/api/winddi/nf-winddi-drvicmdeletecolortransform)

- [DrvLineTo](/windows/win32/api/winddi/nf-winddi-drvlineto)

- [DrvNextBand](/windows/win32/api/winddi/nf-winddi-drvnextband)

- [DrvPlgBlt](/windows/win32/api/winddi/nf-winddi-drvplgblt)

- [DrvQueryAdvanceWidths](/windows/win32/api/winddi/nf-winddi-drvqueryadvancewidths)

- [DrvQueryDeviceSupport](/windows/win32/api/winddi/nf-winddi-drvquerydevicesupport)

- [DrvQueryFont](/windows/win32/api/winddi/nf-winddi-drvqueryfont)

- [DrvQueryFontData](/windows/win32/api/winddi/nf-winddi-drvqueryfontdata)

- [DrvQueryFontTree](/windows/win32/api/winddi/nf-winddi-drvqueryfonttree)

- [DrvRealizeBrush](/windows/win32/api/winddi/nf-winddi-drvrealizebrush)

- [DrvSendPage](/windows/win32/api/winddi/nf-winddi-drvsendpage)

- [DrvStartBanding](/windows/win32/api/winddi/nf-winddi-drvstartbanding)

- [DrvStartDoc](/windows/win32/api/winddi/nf-winddi-drvstartdoc)

- [DrvStartPage](/windows/win32/api/winddi/nf-winddi-drvstartpage)

- [DrvStretchBlt](/windows/win32/api/winddi/nf-winddi-drvstretchblt)

- [DrvStretchBltROP](/windows/win32/api/winddi/nf-winddi-drvstretchbltrop)

- [DrvStrokeAndFillPath](/windows/win32/api/winddi/nf-winddi-drvstrokeandfillpath)

- [DrvStrokePath](/windows/win32/api/winddi/nf-winddi-drvstrokepath)

- [DrvTextOut](/windows/win32/api/winddi/nf-winddi-drvtextout)

- [DrvTransparentBlt](/windows/win32/api/winddi/nf-winddi-drvtransparentblt)

If you provide a customized hooking function, it preempts the driver's equivalent graphics DDI function. Hooking functions can also call back into the driver's graphics DDI functions. For more information see [Customized Graphics DDI Functions](/windows-hardware/drivers/print/customized-graphics-ddi-functions).

Customized hooking functions have the same input and output parameters as the equivalent graphics DDI function, with one exception - where graphics DDI functions receive PDEV pointers, customized hooking functions receive [DEVOBJ](/windows-hardware/drivers/ddi/printoem/ns-printoem-_devobj) pointers. There are two ways for graphics DDI functions to receive PDEV pointers:

- As the contents of the **dhpdev** member of a [SURFOBJ](/windows/win32/api/winddi/ns-winddi-surfobj) structure for the destination surface. For the equivalent customized hooking function, the destination SURFOBJ structure's **dhpdev** member points to a DEVOBJ structure, and must be cast to type PDEVOBJ when referenced. An example graphics DDI function is **DrvBitBlt**.

- As an input argument for a *dhpdev* parameter. The equivalent customized hooking function must cast this input parameter to type PDEVOBJ when referencing it. An example graphics DDI function is **DrvDitherColor**.

Note that while a [printer graphics DLL](/windows-hardware/drivers/print/printer-graphics-dll) includes the addresses of its [DrvEnablePDEV](/windows/win32/api/winddi/nf-winddi-drvenablepdev), [DrvDisablePDEV](/windows/win32/api/winddi/nf-winddi-drvdisablepdev), and [DrvResetPDEV](/windows/win32/api/winddi/nf-winddi-drvresetpdev) functions in the DRVENABLEDATA structure, a rendering plug-in explicitly exports **EnablePDEV**, **DisablePDEV**, and **ResetPDEV** as methods of the **IPrintOemUni** interface and does not place their addresses in the DRVENABLEDATA structure.

If **IPrintOemUni::EnableDriver** methods are exported by multiple rendering plug-ins, the methods are called in the order that the plug-ins are specified for installation.

Each graphics DDI function can be hooked out by only one rendering plug-in. If multiple plug-ins attempt to hook out the same graphics DDI function, all hook-outs after the first one are ignored.

For more information about creating and installing rendering plug-ins, see [Customizing Microsoft's Printer Drivers](/windows-hardware/drivers/print/customizing-microsoft-s-printer-drivers).
