---
UID: NF:prcomoem.IPrintOemUI.DevMode
title: IPrintOemUI::DevMode method
author: windows-driver-content
description: The IPrintOemUI::DevMode method, provided by user interface plug-ins, performs operations on the plug-in's private DEVMODEW members.
old-location: print\iprintoemui_devmode.htm
old-project: print
ms.assetid: decc76c4-1973-41c5-9091-6dc5b9ccd30d
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: IPrintOemUI::DevMode, DevMode method [Print Devices], IPrintOemUI interface, DevMode method [Print Devices], prcomoem/IPrintOemUI::DevMode, IPrintOemUI interface [Print Devices], DevMode method, print_unidrv-pscript_ui_3d5344ac-bacd-499b-87f7-c8e1b7f0e174.xml, IPrintOemUI, print.iprintoemui_devmode, DevMode
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
req.lib: prcomoem.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Prcomoem.h
apiname:
-	IPrintOemUI.DevMode
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemUI::DevMode method


## -description


The <code>IPrintOemUI::DevMode</code> method, provided by user interface plug-ins, performs operations on the plug-in's private DEVMODEW members.


## -syntax


````
STDMETHOD DevMode(
   DWORD       dwMode,
   POEMDMPARAM pOemDMParam
);
````


## -parameters




### -param dwMode

Caller-supplied constant. See the following Remarks section.


### -param pOemDMParam

Caller-supplied pointer to an <a href="..\printoem\ns-printoem-_oemdmparam.md">OEMDMPARAM</a> structure.


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



User interface plug-ins must implement a <code>IPrintOemUI::DevMode</code> method if they define private <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure members. The method's purpose is to define, validate, or convert (from one version to another) the contents of the private DEVMODEW structure members.

A private DEVMODEW section must be prefaced by a <a href="..\printoem\ns-printoem-_oem_dmextraheader.md">OEM_DMEXTRAHEADER</a> structure.

The <code>IPrintOemUI::DevMode</code> method must perform the operation indicated by its <i>dwMode</i> value. Each time <code>IPrintOemUI::DevMode</code> is called, <i>dwMode</i> contains one of the following constants, which are listed in the order they are received:






## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554230">IPrintOemUni::DevMode</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553205">IPrintOemPS::DevMode</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintOemUI::DevMode method%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

