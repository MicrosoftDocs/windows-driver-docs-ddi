---
UID: NF:winsplp.AddPortUI
title: AddPortUI function
author: windows-driver-content
description: A port monitor UI DLL's AddPortUI function adds a printer port, then obtains port configuration information from the user and sends it to the port monitor server DLL.
old-location: print\addportui.htm
old-project: print
ms.assetid: 8305ab0c-0783-4597-9e2c-dfd9cbc843d1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: AddPortUI, pfnAddPortUI, pfnAddPortUI function [Print Devices], print.addportui, spoolfnc_e82f0e4d-e4f2-44b8-b957-3fc1b35e8a34.xml, winsplp/pfnAddPortUI
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	winsplp.h
api_name:
-	pfnAddPortUI
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# AddPortUI function


## -description


A port monitor UI DLL's <b>AddPortUI</b> function adds a printer port, then obtains port configuration information from the user and sends it to the port monitor server DLL.


## -parameters




### -param pszServer [in, optional]

Caller-supplied pointer to a string representing a server name, or <b>NULL</b> if the printer is local.


### -param hWnd [in]

Caller-supplied handle of the window that should be used as the parent for dialog boxes. If <b>NULL</b>, no dialog boxes should be displayed.


### -param pszMonitorNameIn

TBD


### -param ppszPortNameOut [out, optional]

Caller-supplied pointer to a location to receive a port name string. Can be <b>NULL</b>, in which case a name is not returned.


#### - pszPortNameIn [in]

Caller-supplied pointer to a string representing the name of the monitor. Can be <b>NULL</b>.


## -returns



If the operation succeeds, the function should return <b>TRUE</b>. Otherwise SetLastError should be called to specify an error code, and the function should return <b>FALSE</b>. If the operation is canceled by the user or is unsupported, the function should call SetLastError(ERROR_CANCELLED), then return <b>FALSE</b>.




## -remarks



Port monitor UI DLLs are required to define an <b>AddPortUI</b> function and include the function's address in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557541">MONITORUI</a> structure.

The spooler calls <b>AddPortUI</b> from within its AddPort function. The first three arguments received by <b>AddPortUI</b> are the arguments received by AddPort. (The AddPort function is described in the Microsoft Windows SDK documentation.)

The function should perform the following operations:

<ol>
<li>
Call OpenPrinter, specifying a printer name with the following format:<dl>
<dd>\\<i>ServerName</i>\,XcvMonitor<i>MonitorName</i></dd>
</dl>


where <i>ServerName</i> and <i>MonitorName</i> are the server and monitor names received as <b>AddPortUI</b> function arguments.

The call to OpenPrinter requires a PRINTER_DEFAULTS structure, which is described in the Windows SDK documentation. The structure's <b>DesiredAccess</b> member must be set to SERVER_ACCESS_ADMINISTER. Its <b>pDatatype</b> and <b>pDevMode</b> members can be <b>NULL</b>.

This call causes the print monitor server DLL's <a href="https://msdn.microsoft.com/library/windows/hardware/ff564259">XcvOpenPort</a> function to be called.

</li>
<li>
Obtain a port name from the user by displaying a dialog box.

</li>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff564255">XcvData</a>, specifying the following input arguments:<ul>
<li>The handle received from OpenPrinter</li>
<li>The port name received from the user</li>
<li>A customized data name string, such as "PortExists"</li>
</ul>


This call causes the server DLL's <a href="https://msdn.microsoft.com/library/windows/hardware/ff564258">XcvDataPort</a> function to be called. The <b>XcvDataPort</b> function should return a value that indicates whether the specified port name has already been used. If it has, the UI DLL should request another name from the user and call <a href="https://msdn.microsoft.com/library/windows/hardware/ff564255">XcvData</a> again.

</li>
<li>
After a valid new port name has been received, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff564255">XcvData</a> again, this time specifying the following input arguments:<ul>
<li>The handle received from OpenPrinter</li>
<li>The validated port name received from the user</li>
<li>A data name string of "AddPort"</li>
</ul>


This call causes the server DLL's <a href="https://msdn.microsoft.com/library/windows/hardware/ff564258">XcvDataPort</a> function to be called again.

</li>
<li>
Obtain port configuration parameters from the user by displaying a dialog box.

</li>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff564255">XcvData</a> one or more times, specifying customized data name strings, to send each configuration parameter to the server DLL. Each <b>XcvData</b> call causes the server's <a href="https://msdn.microsoft.com/library/windows/hardware/ff564258">XcvDataPort</a> function to be called.

</li>
<li>
Call ClosePrinter, specifying the handle received from OpenPrinter. This causes the server DLL's <a href="https://msdn.microsoft.com/library/windows/hardware/ff564254">XcvClosePort</a> function to be called.

</li>
</ol>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557541">MONITORUI</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564254">XcvClosePort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564255">XcvData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564258">XcvDataPort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564259">XcvOpenPort</a>
 

 

