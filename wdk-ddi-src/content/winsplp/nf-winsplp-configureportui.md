---
UID: NF:winsplp.ConfigurePortUI
title: ConfigurePortUI function
author: windows-driver-content
description: A port monitor UI DLL's ConfigurePortUI function obtains port configuration information from the user and sends it to the port monitor server DLL.
old-location: print\configureportui.htm
old-project: print
ms.assetid: fef58485-db4e-4bad-a21b-376e8d83f243
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: pfnConfigurePortUI, pfnConfigurePortUI function [Print Devices], spoolfnc_5b799b7f-667a-4c5a-855e-554daa2695ea.xml, print.configureportui, winsplp/pfnConfigurePortUI, ConfigurePortUI
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
-	pfnConfigurePortUI
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# ConfigurePortUI function


## -description


A port monitor UI DLL's <b>ConfigurePortUI</b> function obtains port configuration information from the user and sends it to the port monitor server DLL.


## -syntax


````
BOOL WINAPI pfnConfigurePortUI(
  _In_opt_ PCWSTR pszServer,
  _In_     HWND   hWnd,
  _In_     PCWSTR pszPortName
);
````


## -parameters




### -param pszServer [in, optional]

Caller-supplied pointer to a string representing a server name, or <b>NULL</b> if the printer is local. (The port monitor can ignore this parameter.)


### -param hWnd [in]

Caller-supplied handle of the window that should be used as the parent for dialog boxes. If <b>NULL</b>, no dialog boxes should be displayed.


### -param pszPortName [in]

Caller-supplied pointer to a string representing the name of the port to be configured.


## -returns


If the operation succeeds, the function should return <b>TRUE</b>. Otherwise it should return <b>FALSE</b>. If the operation is unsupported, or is canceled by the user (either by selecting CANCEL or by selecting OK without changing configuration parameters), the function should call SetLastError(ERROR_CANCELLED), then return <b>FALSE</b>.



## -remarks


Port monitor UI DLLs are required to define a <b>ConfigurePortUI</b> function and include the function's address in a <a href="..\winsplp\ns-winsplp-_monitorui.md">MONITORUI</a> structure.

The client's spooler calls <b>ConfigurePortUI</b> from within its <a href="https://msdn.microsoft.com/library/windows/hardware/ff546286">ConfigurePort</a> function (described in the Microsoft Windows SDK documentation). The arguments received by <b>ConfigurePortUI</b> are the arguments received by <b>ConfigurePort</b>. 

The function should perform the following operations:
<ol>
<li>
Call OpenPrinter, specifying a printer name with the following format:<dl>
<dd>\\<i>ServerName</i>\,XcvPort<i>PortName</i></dd>
</dl>


where <i>ServerName</i> and <i>PortName</i> are the server and port names received as <b>ConfigurePortUI</b> function arguments.

The call to OpenPrinter requires a PRINTER_DEFAULTS structure, which is described in the Windows SDK documentation. The structure's <b>DesiredAccess</b> member must be set to SERVER_ACCESS_ADMINISTER. Its <b>pDatatype</b> and <b>pDevMode</b> members can be <b>NULL</b>.

This call causes the print monitor server DLL's <a href="..\winsplp\nf-winsplp-xcvopenport.md">XcvOpenPort</a> function to be called.

</li>
<li>
Obtain port configuration parameters from the user by displaying a dialog box.

</li>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff564255">XcvData</a> one or more times, specifying customized data name strings, to send each configuration parameter to the server DLL. Each <b>XcvData</b> call causes the server's <a href="..\winsplp\nf-winsplp-xcvdataport.md">XcvDataPort</a> function to be called.

</li>
<li>
Call ClosePrinter, specifying the handle received from OpenPrinter. This causes the server DLL's <a href="..\winsplp\nf-winsplp-xcvcloseport.md">XcvClosePort</a> function to be called.

</li>
</ol>


## -see-also

<a href="..\winsplp\nf-winsplp-xcvopenport.md">XcvOpenPort</a>

<a href="..\winsplp\nf-winsplp-xcvcloseport.md">XcvClosePort</a>

<a href="..\winsplp\nf-winsplp-xcvdataport.md">XcvDataPort</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564255">XcvData</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20ConfigurePortUI function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

