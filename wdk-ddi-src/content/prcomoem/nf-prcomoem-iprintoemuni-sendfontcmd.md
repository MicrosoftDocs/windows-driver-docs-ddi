---
UID: NF:prcomoem.IPrintOemUni.SendFontCmd
title: IPrintOemUni::SendFontCmd method
author: windows-driver-content
description: The IPrintOemUni::SendFontCmd method enables a rendering plug-in to modify a printer's font selection command and then send it to the printer.
old-location: print\iprintoemuni_sendfontcmd.htm
old-project: print
ms.assetid: b90a94d1-c6f3-483c-b5fc-edfee27094ab
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintOemUni, IPrintOemUni interface [Print Devices], SendFontCmd method, IPrintOemUni::SendFontCmd, SendFontCmd method [Print Devices], SendFontCmd method [Print Devices], IPrintOemUni interface, SendFontCmd,IPrintOemUni.SendFontCmd, prcomoem/IPrintOemUni::SendFontCmd, print.iprintoemuni_sendfontcmd, print_unidrv-pscript_rendering_18926c40-665b-4ea9-9343-7939619d093a.xml
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
-	COM
api_location:
-	prcomoem.h
api_name:
-	IPrintOemUni.SendFontCmd
product: Windows
targetos: Windows
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

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The operation succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The operation failed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The method is not implemented.

</td>
</tr>
</table>
 




## -remarks



The <code>IPrintOemUni::SendFontCmd</code> method is used for selecting device fonts on printers that do not recognize the <a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">PCL</a>, CAPSL, or PPDS-formatted font commands supported by Unidrv. Its purpose is to allow a rendering plug-in to modify the font selection command that is specified in the font's .ufm (Unidrv Font Metrics) file. (To see how the command is stored, refer to the description of .ufm file's <a href="..\prntfont\ns-prntfont-_unidrvinfo.md">UNIDRVINFO</a> structure.) If the command needs to be modified before being sent to the printer, you should implement the <code>IPrintOemUni::SendFontCmd</code> method.

The method receives the command string in the <a href="..\printoem\ns-printoem-_finvocation.md">FINVOCATION</a> structure pointed to by <i>pFInv</i>. Typically, the string contains variables for which values must be supplied. For example, the following font selection command requires that <i>#FontHeight</i> and <i>#FontWidth</i> be replaced with numeric values:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>\x1B(9U\x1B(s4148t0b0s#FontHeight1P\x1B)6J\x1B)s4148t0b0s#FontWidth1P</pre>
</td>
</tr>
</table></span></div>
Current values for the font height and width can be obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> to read Unidrv's standard variables.

Whenever the <code>IPrintOemUni::SendFontCmd</code> method called, it must send the command string to the printer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff553138">IPrintOemDriverUni::DrvWriteSpoolBuf</a>.

The <code>IPrintOemUni::SendFontCmd</code> method is optional. If a rendering plug-in implements this method, the plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554253">IPrintOemUni::GetImplementedMethod</a> method must return S_OK when it receives "SendFontCmd" as input.

For additional information see <a href="https://msdn.microsoft.com/6e643703-ace1-4660-990c-3a9ca735829d">Customized Font Management</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554253">IPrintOemUni::GetImplementedMethod</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553138">IPrintOemDriverUni::DrvWriteSpoolBuf</a>



<a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a>



<a href="..\printoem\ns-printoem-_unifontobj.md">UNIFONTOBJ</a>



<a href="..\printoem\ns-printoem-_finvocation.md">FINVOCATION</a>



<a href="..\prcomoem\nn-prcomoem-iprintoemuni.md">IPrintOemUni</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a>



 

 


