---
UID: NF:winsplp.DeletePortUI
title: DeletePortUI function
author: windows-driver-content
description: A port monitor UI DLL's DeletePortUI function deletes a printer port.
old-location: print\deleteportui.htm
old-project: print
ms.assetid: a556ec29-9149-4185-b4b3-9aae803e62f7
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: winsplp/pfnDeletePortUI, print.deleteportui, spoolfnc_9b9b8660-cc30-49ea-aea1-163eef7ab973.xml, pfnDeletePortUI, DeletePortUI, pfnDeletePortUI function [Print Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	winsplp.h
apiname:
-	pfnDeletePortUI
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# DeletePortUI function


## -description


A port monitor UI DLL's <b>DeletePortUI</b> function deletes a printer port.


## -syntax


````
BOOL WINAPI pfnDeletePortUI(
  _In_opt_ PCWSTR pszServer,
  _In_     HWND   hWnd,
  _In_     PCWSTR pszPortName
);
````


## -parameters




#### - pszServer [in, optional]

Caller-supplied pointer to a string representing a server name, or <b>NULL</b> if the printer is local. (The port monitor can ignore this parameter.)


#### - hWnd [in]

Caller-supplied handle of the window that should be used as the parent for dialog boxes. If <b>NULL</b>, no dialog boxes should be displayed.


#### - pszPortName [in]

Caller-supplied pointer to a string representing the name of the port to be deleted.


## -returns


If the operation succeeds, the function should return <b>TRUE</b>. Otherwise it should return <b>FALSE</b>. If the operation is canceled by the user or is unsupported, the function should call SetLastError(ERROR_CANCELLED), then return <b>FALSE</b>.



## -remarks


Port monitor UI DLLs are required to define a <b>DeletePortUI</b> function and include the function's address in a <a href="..\winsplp\ns-winsplp-_monitorui.md">MONITORUI</a> structure.

The spooler calls <b>DeletePortUI</b> from within its <b>DeletePort</b> function. The arguments received by <b>DeletePortUI</b> are the arguments received by <b>DeletePort</b>. (The <b>DeletePort</b> function is described in the Microsoft Windows SDK documentation.)

The function should perform the following operations:
<ol>
<li>
Call <b>OpenPrinter</b>, specifying a printer name with the following format:<dl>
<dd><b>\\</b><i>ServerName</i><b>\,XcvPort</b><i>PortName</i></dd>
</dl>


where <i>ServerName</i> and <i>PortName</i> are the server and port names received as <b>DeletePortUI</b> function arguments.

The call to <b>OpenPrinter</b> requires a PRINTER_DEFAULTS structure, which is described in the Windows SDK documentation. The structure's <b>DesiredAccess</b> member must be set to SERVER_ACCESS_ADMINISTER. Its <b>pDatatype</b> and <b>pDevMode</b> members can be <b>NULL</b>.

This call causes the print monitor server DLL's <a href="..\winsplp\nf-winsplp-xcvopenport.md">XcvOpenPort</a> function to be called.

</li>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff564255">XcvData</a>, specifying the following input arguments:<ul>
<li>The handle received from <b>OpenPrinter</b></li>
<li>The port name received as a function argument</li>
<li>A data name string of "DeletePort"</li>
</ul>


This call causes the server DLL's <a href="..\winsplp\nf-winsplp-xcvcloseport.md">XcvClosePort</a> function to be called.

</li>
<li>
If user interaction is required, obtain information from the user by displaying a dialog box and then call <a href="https://msdn.microsoft.com/library/windows/hardware/ff564255">XcvData</a>, specifying customized data name strings, to send the information to the server DLL. The <b>XcvData</b> call causes the server's <a href="..\winsplp\nf-winsplp-xcvdataport.md">XcvDataPort</a> function to be called.

</li>
<li>
Call <b>ClosePrinter</b>, specifying the handle received from <b>OpenPrinter</b>. This causes the server DLL's <a href="..\winsplp\nf-winsplp-xcvcloseport.md">XcvClosePort</a> function to be called.

</li>
</ol>


## -see-also

<a href="..\winsplp\nf-winsplp-xcvcloseport.md">XcvClosePort</a>

<a href="..\winsplp\nf-winsplp-xcvopenport.md">XcvOpenPort</a>

<a href="..\winsplp\nf-winsplp-xcvdataport.md">XcvDataPort</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564255">XcvData</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20DeletePortUI function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

