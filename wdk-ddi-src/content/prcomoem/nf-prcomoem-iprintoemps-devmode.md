---
UID: NF:prcomoem.IPrintOemPS.DevMode
title: IPrintOemPS::DevMode method
author: windows-driver-content
description: The IPrintOemPS::DevMode method, provided by rendering plug-ins for Pscript5, performs operations on private DEVMODEW members.
old-location: print\iprintoemps_devmode.htm
old-project: print
ms.assetid: 72775113-435c-44cf-83e7-9aa62f7f252e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: print.iprintoemps_devmode, print_unidrv-pscript_rendering_d14a1c50-fd58-4c64-989d-3a7807cfd929.xml, prcomoem/IPrintOemPS::DevMode, IPrintOemPS::DevMode, DevMode method [Print Devices], IPrintOemPS interface, DevMode, IPrintOemPS, IPrintOemPS interface [Print Devices], DevMode method, DevMode method [Print Devices]
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
-	IPrintOemPS.DevMode
product: Windows
targetos: Windows
req.typenames: *POEMPTOPTS, OEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemPS::DevMode method


## -description


The <code>IPrintOemPS::DevMode</code> method, provided by rendering plug-ins for Pscript5, performs operations on private <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> members.


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


This method must return one of the following values.
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
The operation failed

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


If you are providing a user interface plug-in for Pscript5, and if you are adding private members to the driver's DEVMODEW structure, you must implement both the <code>IPrintOemUI::DevMode</code> and the <code>IPrintOemPS::DevMode</code> methods. The code implementing these methods must be identical and can be placed in a library that is statically linked to both the UI plug-in and the rendering plug-in.

For a description of the <code>IPrintOemPS::DevMode</code> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554167">IPrintOemUI::DevMode</a>.


