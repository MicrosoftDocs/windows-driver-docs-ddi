---
UID: NF:prcomoem.IPrintOemUni.DevMode
title: IPrintOemUni::DevMode (prcomoem.h)
description: The IPrintOemUni::DevMode method, provided by rendering plug-ins for Unidrv, performs operations on private DEVMODEW members.
old-location: print\iprintoemuni_devmode.htm
tech.root: print
ms.assetid: df6bde70-ba14-411b-88a1-b45f2e2756ef
ms.date: 04/20/2018
ms.keywords: DevMode, DevMode method [Print Devices], DevMode method [Print Devices],IPrintOemUni interface, IPrintOemUni interface [Print Devices],DevMode method, IPrintOemUni.DevMode, IPrintOemUni::DevMode, prcomoem/IPrintOemUni::DevMode, print.iprintoemuni_devmode, print_unidrv-pscript_rendering_f7793c3f-de50-4699-a9f1-bf73f8171ecc.xml
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
-	IPrintOemUni.DevMode
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUni::DevMode


## -description


The <code>IPrintOemUni::DevMode</code> method, provided by rendering plug-ins for Unidrv, performs operations on private <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> members.


## -parameters




### -param dwMode

Specifies a caller-supplied constant. See the Remarks section for more information.


### -param pOemDMParam

Caller-supplied pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff557686">OEMDMPARAM</a> structure.


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



A rendering plug-in for Unidrv must implement the <code>IPrintOemUni::DevMode</code> method.

If you are providing a user interface plug-in for Unidrv, and if you are adding private members to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure, you must implement both the <code>IPrintOemUI::DevMode</code> and the <code>IPrintOemUni::DevMode</code> methods. The code implementing these methods must be identical and can be placed in a library that is statically linked to both the UI plug-in and the rendering plug-in.

The <code>IPrintOemUni::DevMode</code> method must perform the operation indicated by its <i>dwMode</i> value. Each time <code>IPrintOemUni::DevMode</code> is called, <i>dwMode</i> contains one of the following constants, which are listed in the order they are received:






## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554167">IPrintOemUI::DevMode</a>



<a href="https://msdn.microsoft.com/097366a0-2ded-435c-9b63-2b736b716032">IPrintOemUni</a>
 

 

