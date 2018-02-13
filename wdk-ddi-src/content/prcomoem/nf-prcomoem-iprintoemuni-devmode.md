---
UID: NF:prcomoem.IPrintOemUni.DevMode
title: IPrintOemUni::DevMode method
author: windows-driver-content
description: The IPrintOemUni::DevMode method, provided by rendering plug-ins for Unidrv, performs operations on private DEVMODEW members.
old-location: print\iprintoemuni_devmode.htm
old-project: print
ms.assetid: df6bde70-ba14-411b-88a1-b45f2e2756ef
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: print_unidrv-pscript_rendering_f7793c3f-de50-4699-a9f1-bf73f8171ecc.xml, IPrintOemUni, IPrintOemUni::DevMode, DevMode method [Print Devices], IPrintOemUni interface, print.iprintoemuni_devmode, prcomoem/IPrintOemUni::DevMode, DevMode method [Print Devices], IPrintOemUni interface [Print Devices], DevMode method, DevMode
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
-	IPrintOemUni.DevMode
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemUni::DevMode method


## -description


The <code>IPrintOemUni::DevMode</code> method, provided by rendering plug-ins for Unidrv, performs operations on private <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> members.


## -syntax


````
STDMETHOD DevMode(
   DWORD       dwMode,
   POEMDMPARAM pOemDMParam
);
````


## -parameters




### -param dwMode

Specifies a caller-supplied constant. See the Remarks section for more information.


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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintOemUni::DevMode method%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

