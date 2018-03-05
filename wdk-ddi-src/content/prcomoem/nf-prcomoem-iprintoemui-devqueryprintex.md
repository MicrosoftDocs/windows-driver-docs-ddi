---
UID: NF:prcomoem.IPrintOemUI.DevQueryPrintEx
title: IPrintOemUI::DevQueryPrintEx method
author: windows-driver-content
description: The IPrintOemUI::DevQueryPrintEx method allows a user interface plug-in to help determine if a print job is printable.
old-location: print\iprintoemui_devqueryprintex.htm
old-project: print
ms.assetid: a1bc9be3-53ec-4506-a409-94a65d7136e1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DevQueryPrintEx method [Print Devices], DevQueryPrintEx method [Print Devices], IPrintOemUI interface, DevQueryPrintEx,IPrintOemUI.DevQueryPrintEx, IPrintOemUI, IPrintOemUI interface [Print Devices], DevQueryPrintEx method, IPrintOemUI::DevQueryPrintEx, prcomoem/IPrintOemUI::DevQueryPrintEx, print.iprintoemui_devqueryprintex, print_unidrv-pscript_ui_64a7a4c1-9478-4710-8d2e-84696b8941b0.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	prcomoem.h
api_name:
-	IPrintOemUI.DevQueryPrintEx
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemUI::DevQueryPrintEx method


## -description


The <code>IPrintOemUI::DevQueryPrintEx</code> method allows a user interface plug-in to help determine if a print job is printable.


## -syntax


````
HRESULT DevQueryPrintEx(
   POEMUIOBJ           poemuiobj,
   PDEVQUERYPRINT_INFO pDQPInfo,
   PDEVMODE            pPublicDM,
   PVOID               pOEMDM
);
````


## -parameters




### -param poemuiobj

Caller-supplied pointer to an <a href="..\printoem\ns-printoem-_oemuiobj.md">OEMUIOBJ</a> structure.


### -param pDQPInfo

Caller-supplied pointer to a <a href="..\winddiui\ns-winddiui-_devqueryprint_info.md">DEVQUERYPRINT_INFO</a> structure.


### -param pPublicDM

Caller-supplied pointer to a validated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure.


### -param pOEMDM

Caller-supplied pointer to the user interface plug-in's private DEVMODEW structure members.


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



A user interface plug-in's <code>IPrintOemUI::DevQueryPrintEx</code> method performs the same types of operations as the <a href="..\winddiui\nf-winddiui-devqueryprintex.md">DevQueryPrintEx</a> function that is exported by user-mode printer interface DLLs. You can use this method to enhance the functionality provided by the <b>DevQueryPrintEx</b> function. Like the <b>DevQueryPrintEx</b> function, the <code>IPrintOemUI::DevQueryPrintEx</code> method's responsibility is to determine if the print job described by the supplied DEVMODEW structure can be printed.

When the driver's <b>DevQueryPrintEx</b> function is called, it checks the DEVMODEW structure, along with the currently selected printer options, to determine if the job is printable. If it is not, the function returns <b>FALSE</b>. If the job appears to be printable, the function calls the <code>IPrintOemUI::DevQueryPrintEx</code> method in each user interface plug-in associated with the driver. If all <code>IPrintOemUI::DevQueryPrintEx</code> methods return S_OK, then <b>DevQueryPrintEx</b> returns <b>TRUE</b>. Thus, a job is not printable unless the <b>DevQueryPrintEx</b> function and all <code>IPrintOemUI::DevQueryPrintEx</code> methods declare it to be printable.

If <code>IPrintOemUI::DevQueryPrintEx</code> methods are exported by multiple user interface plug-ins, the methods are called in the order that the plug-ins are specified for installation.

For more information about creating and installing user interface plug-ins, see <a href="https://msdn.microsoft.com/b7761209-1f6f-4288-af47-4ed855c2e629">Customizing Microsoft's Printer Drivers</a>.




## -see-also

<a href="..\winddiui\nf-winddiui-devqueryprintex.md">DevQueryPrintEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintOemUI::DevQueryPrintEx method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

