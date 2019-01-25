---
UID: NF:winsplp.XcvDataPort
title: XcvDataPort function (winsplp.h)
description: A port monitor server DLL's XcvDataPort function receives information from, and returns information to, the port monitor's UI DLL.
old-location: print\xcvdataport.htm
tech.root: print
ms.assetid: 2d0e3509-27d9-439f-9d47-e0e500e8907f
ms.date: 02/02/2018
ms.keywords: print.xcvdataport, winsplp/XcvDataPort, XcvDataPort, spoolfnc_09b26a0a-26ad-43c9-995a-99cd4fb4a726.xml, XcvDataPort function [Print Devices]
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
-	XcvDataPort
product:
- Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# XcvDataPort function


## -description


A port monitor server DLL's <b>XcvDataPort</b> function receives information from, and returns information to, the port monitor's UI DLL.


## -syntax


```cpp
DWORD XcvDataPort(
  _In_  HANDLE  hXcv,
  _In_  LPCWSTR pszDataName,
  _In_  PBYTE   pInputData,
        DWORD   cbInputData,
  _Out_ PBYTE   pOutputData,
        DWORD   cbOutputData,
  _Out_ PDWORD  pcbOutputNeeded
);
```


## -parameters




### -param hXcv [in]

Caller-supplied printer handle, obtained by calling <b>OpenPrinter</b> (described in the Microsoft Windows SDK documentation). This handle is created and returned by the <a href="..\winsplp\nf-winsplp-xcvopenport.md">XcvOpenPort</a> function.


### -param pszDataName [in]

Caller-supplied pointer to a string representing the name of the data being requested. For more information, see the following Remarks section.


### -param pInputData [in]

Caller-supplied pointer to a buffer containing input data.


### -param cbInputData

Caller-supplied size, in bytes, of the buffer pointed to by <i>pInputData</i>.


### -param pOutputData [out]

Caller-supplied pointer to a buffer to receive output data.


### -param cbOutputData

Caller-supplied size, in bytes, of the buffer pointed to by <i>pOutputData</i>.


### -param pcbOutputNeeded [out]

Caller-supplied pointer to a location to receive the minimum size, in bytes, required for the buffer pointed to by <i>pOutputData</i>.


## -returns



If the operation succeeds, this function should return ERROR_SUCCESS. Otherwise, it should return an ERROR_-prefixed Win32 error code. The print monitor UI DLL receives this value in the <i>pdwStatus</i> location specified for <a href="https://msdn.microsoft.com/library/windows/hardware/ff564255">XcvData</a>.




## -remarks



Port monitor server DLLs are required to define an <b>XcvDataPort</b> function so they can receive information from, and return information to, a port monitor UI DLL. The function's address must be included in a <a href="..\winsplp\ns-winsplp-_monitor2.md">MONITOR2</a> structure.

The <b>XcvDataPort</b> function is called by the spooler's <a href="https://msdn.microsoft.com/library/windows/hardware/ff564255">XcvData</a> function. The function parameters for <b>XcvDataPort</b> and <b>XcvData</b> are almost identical. (<b>XcvData</b> has an additional parameter, <i>pdwStatus</i>, that is not present in <b>XcvDataPort</b>.)

The string pointed to by <i>pszDataName</i> specifies the operation to be performed. The function must recognize the following data name strings:

<table>
<tr>
<th>Data Name String</th>
<th>Operation</th>
</tr>
<tr>
<td>
L"AddPort"

</td>
<td>
All information needed for adding a port has been sent. The function should perform operations necessary to add the specified port, including writing the port name in the registry under the Ports key.

The <i>pInputData</i> parameter points to a NULL-terminated port name string.

If the function returns ERROR_SUCCESS, the spooler marks the port as added.

This string is specified by the print monitor UI DLL, from within its <a href="..\winsplp\nf-winsplp-addportui.md">AddPortUI</a> function.

</td>
</tr>
<tr>
<td>
L"DeletePort"

</td>
<td>
All information needed for deleting a port has been sent. The function should perform operations necessary to delete the specified port, including removing the port name from the registry's Ports key.

The <i>pInputData</i> parameter points to a NULL-terminated port name string.

If the function returns ERROR_SUCCESS, the spooler marks the port as deleted.

This string is specified by the print monitor UI DLL, from within its <a href="..\winsplp\nf-winsplp-deleteportui.md">DeletePortUI</a> function.

</td>
</tr>
<tr>
<td>
L"MonitorUI"

</td>
<td>
The function should use <i>pOutputData</i> to return the name of the associated port monitor UI DLL.

This string is specified by the print spooler, when an application calls the Microsoft Windows SDK <b>AddPort</b> function.

</td>
</tr>
</table>
 

Typically, the function is written to recognize additional, customized strings that are sent by the UI DLL from within its <a href="..\winsplp\nf-winsplp-addportui.md">AddPortUI</a>, <a href="..\winsplp\nf-winsplp-configureportui.md">ConfigurePortUI</a>, and <a href="..\winsplp\nf-winsplp-deleteportui.md">DeletePortUI</a> functions. These strings might represent commands that request current configuration values from the server DLL, or that deliver new values. For example, your <b>XcvDataPort</b> function might recognize the string "GetTransmissionRetryTimeout", which your UI DLL could send to your server DLL to request the currently stored transmission retry time-out value. Or, you might define a set of strings that must be sent before "AddPort" or "DeletePort" is sent, where the strings are used to supply information identifying the port to add or delete.

For a given <i>pszDataName</i> string and input buffer, <b>XcvDataPort</b> might first be called with a <i>cbOutputData</i> value of zero. The function should return a required buffer size in <i>pcbOutputNeeded</i>, along with a return value of ERROR_INSUFFICIENT_BUFFER. The caller can use the value received in <i>pcbOutputNeeded</i> to allocate an output buffer of adequate size, and can then call <b>XcvDataPort</b> again, this time specifying the allocated buffer size in <i>cbOutputData</i>.

The <b>XcvDataPort</b> function must validate all input arguments. Specifically, the function must:

<ul>
<li>
Validate the contents of the string pointed to by the <i>pszDataName</i> parameter. If this string represents an administrative operation (typically adding, deleting, or configuring a port), the <b>XcvDataPort</b> function should compare the granted access mask that was previously received by the <a href="..\winsplp\nf-winsplp-xcvopenport.md">XcvOpenPort</a> function with SERVER_ACCESS_ADMINISTER. If the comparison fails, <b>XcvDataPort</b> must  return ERROR_ACCESS_DENIED.

</li>
<li>
Validate the contents of the buffer pointed to by the <i>pInputData</i> parameter. When the spooler calls the <b>XcvOpenPort</b> function, it performs no validation on the contents of this buffer. The monitor can make no assumptions about the validity of this data, which can come from a malicious application.

</li>
</ul>
If you are writing a port monitor that will communicate with TCPMON, see <a href="https://msdn.microsoft.com/7b2b1cff-ab8f-44e0-9327-dc60a0072bf5">TCPMON Xcv Interface</a>.




## -see-also

<a href="..\winsplp\nf-winsplp-xcvopenport.md">XcvOpenPort</a>



<a href="..\winsplp\nf-winsplp-deleteportui.md">DeletePortUI</a>



<a href="..\winsplp\nf-winsplp-configureportui.md">ConfigurePortUI</a>



<a href="..\winsplp\nf-winsplp-addportui.md">AddPortUI</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564255">XcvData</a>



 

 


