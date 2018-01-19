---
UID: NF:prcomoem.IPrintOemUni.SendFontCmd
title: IPrintOemUni::SendFontCmd method
author: windows-driver-content
description: The IPrintOemUni::SendFontCmd method enables a rendering plug-in to modify a printer's font selection command and then send it to the printer.
old-location: print\iprintoemuni_sendfontcmd.htm
old-project: print
ms.assetid: b90a94d1-c6f3-483c-b5fc-edfee27094ab
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintOemUni, IPrintOemUni::SendFontCmd, SendFontCmd
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrintOemUni.SendFontCmd
req.alt-loc: prcomoem.h
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
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemUni::SendFontCmd method



## -description
The <code>IPrintOemUni::SendFontCmd</code> method enables a rendering plug-in to modify a printer's font selection command and then send it to the printer.



## -syntax

````
HRESULT SendFontCmd(
   PDEVOBJ      pdevobj,
   PUNIFONTOBJ  pUFObj,
   PFINVOCATION pFInv
);
````


## -parameters

### -param pdevobj 

Caller-supplied pointer to a <a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a> structure.


### -param pUFObj 

Caller-supplied pointer to a <a href="..\printoem\ns-printoem-_unifontobj.md">UNIFONTOBJ</a> structure.


### -param pFInv 

Caller-supplied pointer to an <a href="..\printoem\ns-printoem-_finvocation.md">FINVOCATION</a> structure.


## -returns
The method must return one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The operation succeeded.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>The operation failed.
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>The method is not implemented.

 


## -remarks
The <code>IPrintOemUni::SendFontCmd</code> method is used for selecting device fonts on printers that do not recognize the <a href="wdkgloss.p#wdkgloss.pcl#wdkgloss.pcl"><i>PCL</i></a>, CAPSL, or PPDS-formatted font commands supported by Unidrv. Its purpose is to allow a rendering plug-in to modify the font selection command that is specified in the font's .ufm (Unidrv Font Metrics) file. (To see how the command is stored, refer to the description of .ufm file's <a href="..\prntfont\ns-prntfont-_unidrvinfo.md">UNIDRVINFO</a> structure.) If the command needs to be modified before being sent to the printer, you should implement the <code>IPrintOemUni::SendFontCmd</code> method.

The method receives the command string in the <a href="..\printoem\ns-printoem-_finvocation.md">FINVOCATION</a> structure pointed to by <i>pFInv</i>. Typically, the string contains variables for which values must be supplied. For example, the following font selection command requires that <i>#FontHeight</i> and <i>#FontWidth</i> be replaced with numeric values:

Current values for the font height and width can be obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> to read Unidrv's standard variables.

Whenever the <code>IPrintOemUni::SendFontCmd</code> method called, it must send the command string to the printer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff553138">IPrintOemDriverUni::DrvWriteSpoolBuf</a>.

The <code>IPrintOemUni::SendFontCmd</code> method is optional. If a rendering plug-in implements this method, the plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554253">IPrintOemUni::GetImplementedMethod</a> method must return S_OK when it receives "SendFontCmd" as input.

For additional information see <a href="https://msdn.microsoft.com/6e643703-ace1-4660-990c-3a9ca735829d">Customized Font Management</a>.


## -see-also
<dl>
<dt>
<a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a>
</dt>
<dt>
<a href="..\printoem\ns-printoem-_unifontobj.md">UNIFONTOBJ</a>
</dt>
<dt>
<a href="..\printoem\ns-printoem-_finvocation.md">FINVOCATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553138">IPrintOemDriverUni::DrvWriteSpoolBuf</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554253">IPrintOemUni::GetImplementedMethod</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintOemUni::SendFontCmd method%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

