---
UID: NF:winsplp.DeletePortUI
title: DeletePortUI function (winsplp.h)
description: A port monitor UI DLL's DeletePortUI function deletes a printer port.
old-location: print\deleteportui.htm
tech.root: print
ms.assetid: a556ec29-9149-4185-b4b3-9aae803e62f7
ms.date: 04/20/2018
ms.keywords: DeletePortUI, pfnDeletePortUI, pfnDeletePortUI function [Print Devices], print.deleteportui, spoolfnc_9b9b8660-cc30-49ea-aea1-163eef7ab973.xml, winsplp/pfnDeletePortUI
ms.topic: function
req.header: winsplp.h
req.include-header: Winsplp.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- winsplp.h
api_name:
- pfnDeletePortUI
product:
- Windows
targetos: Windows
req.typenames: 
---

# DeletePortUI function


## -description


A port monitor UI DLL's <b>DeletePortUI</b> function deletes a printer port.


## -parameters




### -param pszServer [in, optional]

Caller-supplied pointer to a string representing a server name, or <b>NULL</b> if the printer is local. (The port monitor can ignore this parameter.)


### -param hWnd [in]

Caller-supplied handle of the window that should be used as the parent for dialog boxes. If <b>NULL</b>, no dialog boxes should be displayed.


### -param pszPortName [in]

Caller-supplied pointer to a string representing the name of the port to be deleted.


## -returns



If the operation succeeds, the function should return <b>TRUE</b>. Otherwise it should return <b>FALSE</b>. If the operation is canceled by the user or is unsupported, the function should call SetLastError(ERROR_CANCELLED), then return <b>FALSE</b>.




## -remarks



Port monitor UI DLLs are required to define a <b>DeletePortUI</b> function and include the function's address in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557541">MONITORUI</a> structure.

The spooler calls <b>DeletePortUI</b> from within its <b>DeletePort</b> function. The arguments received by <b>DeletePortUI</b> are the arguments received by <b>DeletePort</b>. (The <b>DeletePort</b> function is described in the Microsoft Windows SDK documentation.)

The function should perform the following operations:

<ol>
<li>
Call <b>OpenPrinter</b>, specifying a printer name with the following format:<dl>
<dd><b>\\</b><i>ServerName</i><b>\,XcvPort</b><i>PortName</i></dd>
</dl>


where <i>ServerName</i> and <i>PortName</i> are the server and port names received as <b>DeletePortUI</b> function arguments.

The call to <b>OpenPrinter</b> requires a PRINTER_DEFAULTS structure, which is described in the Windows SDK documentation. The structure's <b>DesiredAccess</b> member must be set to SERVER_ACCESS_ADMINISTER. Its <b>pDatatype</b> and <b>pDevMode</b> members can be <b>NULL</b>.

This call causes the print monitor server DLL's <a href="https://msdn.microsoft.com/library/windows/hardware/ff564259">XcvOpenPort</a> function to be called.

</li>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff564255">XcvData</a>, specifying the following input arguments:<ul>
<li>The handle received from <b>OpenPrinter</b></li>
<li>The port name received as a function argument</li>
<li>A data name string of "DeletePort"</li>
</ul>


This call causes the server DLL's <a href="https://msdn.microsoft.com/library/windows/hardware/ff564254">XcvClosePort</a> function to be called.

</li>
<li>
If user interaction is required, obtain information from the user by displaying a dialog box and then call <a href="https://msdn.microsoft.com/library/windows/hardware/ff564255">XcvData</a>, specifying customized data name strings, to send the information to the server DLL. The <b>XcvData</b> call causes the server's <a href="https://msdn.microsoft.com/library/windows/hardware/ff564258">XcvDataPort</a> function to be called.

</li>
<li>
Call <b>ClosePrinter</b>, specifying the handle received from <b>OpenPrinter</b>. This causes the server DLL's <a href="https://msdn.microsoft.com/library/windows/hardware/ff564254">XcvClosePort</a> function to be called.

</li>
</ol>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564254">XcvClosePort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564255">XcvData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564258">XcvDataPort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564259">XcvOpenPort</a>
 

 

