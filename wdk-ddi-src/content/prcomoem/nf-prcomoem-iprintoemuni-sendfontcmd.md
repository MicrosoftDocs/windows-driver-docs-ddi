---
UID: NF:prcomoem.IPrintOemUni.SendFontCmd
title: IPrintOemUni::SendFontCmd (prcomoem.h)
description: The IPrintOemUni::SendFontCmd method enables a rendering plug-in to modify a printer's font selection command and then send it to the printer.
old-location: print\iprintoemuni_sendfontcmd.htm
tech.root: print
ms.assetid: b90a94d1-c6f3-483c-b5fc-edfee27094ab
ms.date: 04/20/2018
keywords: ["IPrintOemUni::SendFontCmd"]
ms.keywords: IPrintOemUni interface [Print Devices],SendFontCmd method, IPrintOemUni.SendFontCmd, IPrintOemUni::SendFontCmd, SendFontCmd, SendFontCmd method [Print Devices], SendFontCmd method [Print Devices],IPrintOemUni interface, prcomoem/IPrintOemUni::SendFontCmd, print.iprintoemuni_sendfontcmd, print_unidrv-pscript_rendering_18926c40-665b-4ea9-9343-7939619d093a.xml
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
 - IPrintOemUni::SendFontCmd
 - prcomoem/IPrintOemUni::SendFontCmd
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - prcomoem.h
api_name:
 - IPrintOemUni.SendFontCmd
---

# IPrintOemUni::SendFontCmd


## -description

The `IPrintOemUni::SendFontCmd` method enables a rendering plug-in to modify a printer's font selection command and then send it to the printer.

## -parameters

### -param pdevobj

Caller-supplied pointer to a [DEVOBJ](../printoem/ns-printoem-_devobj.md) structure.

### -param pUFObj

Caller-supplied pointer to a [UNIFONTOBJ](../printoem/ns-printoem-_unifontobj.md) structure.

### -param pFInv

Caller-supplied pointer to an [FINVOCATION](../printoem/ns-printoem-_finvocation.md) structure.

## -returns

The method must return one of the following values.

| Return code | Description |
| --- | --- |
| S_OK | The operation succeeded. |
| E_FAIL | The operation failed. |
| E_NOTIMPL | The method is not implemented. |

## -remarks

The `IPrintOemUni::SendFontCmd` method is used for selecting device fonts on printers that do not recognize the PCL, CAPSL, or PPDS-formatted font commands supported by Unidrv. Its purpose is to allow a rendering plug-in to modify the font selection command that is specified in the font's .ufm (Unidrv Font Metrics) file. (To see how the command is stored, refer to the description of .ufm file's [UNIDRVINFO](../prntfont/ns-prntfont-_unidrvinfo.md) structure.) If the command needs to be modified before being sent to the printer, you should implement the `IPrintOemUni::SendFontCmd` method.

The method receives the command string in the [FINVOCATION](../printoem/ns-printoem-_finvocation.md) structure pointed to by *pFInv*. Typically, the string contains variables for which values must be supplied. For example, the following font selection command requires that *#FontHeight* and *#FontWidth* be replaced with numeric values:

```cpp
\x1B(9U\x1B(s4148t0b0s#FontHeight1P\x1B)6J\x1B)s4148t0b0s#FontWidth1P
```

Current values for the font height and width can be obtained by calling [UNIFONTOBJ_GetInfo](../printoem/nc-printoem-pfngetinfo.md) to read Unidrv's standard variables.

Whenever the `IPrintOemUni::SendFontCmd` method called, it must send the command string to the printer by calling [IPrintOemDriverUni::DrvWriteSpoolBuf](./nf-prcomoem-iprintoemdriveruni-drvwritespoolbuf.md).

The `IPrintOemUni::SendFontCmd` method is optional. If a rendering plug-in implements this method, the plug-in's [IPrintOemUni::GetImplementedMethod](./nf-prcomoem-iprintoemuni-getimplementedmethod.md) method must return S_OK when it receives "SendFontCmd" as input.

For additional information see [Customized Font Management](/windows-hardware/drivers/print/customized-font-management).

## -see-also

[DEVOBJ](../printoem/ns-printoem-_devobj.md)

[FINVOCATION](../printoem/ns-printoem-_finvocation.md)

[IPrintOemDriverUni::DrvWriteSpoolBuf](./nf-prcomoem-iprintoemdriveruni-drvwritespoolbuf.md)

[IPrintOemUni](./nn-prcomoem-iprintoemuni.md)

[IPrintOemUni::GetImplementedMethod](./nf-prcomoem-iprintoemuni-getimplementedmethod.md)

[UNIFONTOBJ](../printoem/ns-printoem-_unifontobj.md)

[UNIFONTOBJ_GetInfo](../printoem/nc-printoem-pfngetinfo.md)