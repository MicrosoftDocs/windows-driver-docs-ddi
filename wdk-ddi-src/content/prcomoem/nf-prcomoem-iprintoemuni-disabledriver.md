---
UID: NF:prcomoem.IPrintOemUni.DisableDriver
title: IPrintOemUni::DisableDriver
author: windows-driver-content
description: The IPrintOemuNI::DisableDriver method allows a rendering plug-in for Unidrv to free resources that were allocated by the plug-in's IPrintOemUni::EnableDriver method.
old-location: print\iprintoemuni_disabledriver.htm
old-project: print
ms.assetid: a92d8c2e-52b5-4941-b49e-42e067e56e91
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: DisableDriver, DisableDriver method [Print Devices], DisableDriver method [Print Devices],IPrintOemUni interface, IPrintOemUni interface [Print Devices],DisableDriver method, IPrintOemUni.DisableDriver, IPrintOemUni::DisableDriver, prcomoem/IPrintOemUni::DisableDriver, print.iprintoemuni_disabledriver, print_unidrv-pscript_rendering_033d3e0c-4d60-4925-a5b4-1fb47aa42cc9.xml
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
-	Prcomoem.h
api_name:
-	IPrintOemUni.DisableDriver
product: Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUni::DisableDriver


## -description


The <code>IPrintOemuNI::DisableDriver</code> method allows a rendering plug-in for <a href="https://msdn.microsoft.com/0a51fa2b-3d09-4a5f-9fff-40604877a414">Unidrv</a> to free resources that were allocated by the plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554248">IPrintOemUni::EnableDriver</a> method.


## -parameters






#### - None


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
The operation failed

</td>
</tr>
</table>
 




## -remarks



A rendering plug-in for Unidrv must implement the <code>IPrintOemUni::DisableDriver</code> method.

The <code>IPrintOemUni::DisableDriver</code> method, provided by rendering plug-ins for Unidrv, performs the same types of operations as the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556196">DrvDisableDriver</a> function that is exported by Unidrv's printer graphics DLL.

<code>IPrintOemUni::DisableDriver</code> and <b>IPrintOemUni::EnableDriver</b> must be implemented as a pair. If you implement one, you must implement the other. For more information, see the Remarks section in <a href="https://msdn.microsoft.com/library/windows/hardware/ff554248">IPrintOemUni::EnableDriver</a>. 

This is the last <b>IPrintOemUni</b> interface method that is called before the rendering plug-in is unloaded.



