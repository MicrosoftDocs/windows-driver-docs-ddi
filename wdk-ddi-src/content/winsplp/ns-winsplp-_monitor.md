---
UID: NS:winsplp._MONITOR
title: "_MONITOR"
author: windows-driver-content
description: The MONITOR structure is obsolete and is supported only for compatibility reasons.
old-location: print\monitor.htm
old-project: print
ms.assetid: 0b0dc06f-51c2-429f-a9bb-079f8a61411d
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*LPMONITOR, LPMONITOR, LPMONITOR structure pointer [Print Devices], MONITOR, MONITOR structure [Print Devices], _MONITOR, print.monitor, spoolfnc_c7b3aeed-d00f-4728-967d-bbe1a8512a42.xml, winsplp/LPMONITOR, winsplp/MONITOR"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Windows
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
-	MONITOR
product: Windows
targetos: Windows
req.typenames: MONITOR, *LPMONITOR
req.product: Windows 10 or later.
---

# _MONITOR structure


## -description


The MONITOR structure is obsolete and is supported only for compatibility reasons. New print monitors should implement <a href="..\winsplp\ns-winsplp-_monitor2.md">MONITOR2</a> so that they can be used with print server clusters.

The MONITOR structure contains pointers to the functions defined by print monitors.


## -syntax


````
typedef struct _MONITOR {
  BOOL  (WINAPI *pfnEnumPorts)(
      LPWSTR pName, 
      DWORD Level, 
      LPBYTE pPorts, 
      DWORD cbBuf, 
      LPDWORD pcbNeeded, 
      LPDWORD pcReturned);
  BOOL  (WINAPI *pfnOpenPort)(
      LPWSTR pName, 
      PHANDLE pHandle);
  BOOL  (WINAPI *pfnOpenPortEx)(
      LPWSTR pPortName, 
      LPWSTR pPrinterName, 
      PHANDLE pHandle, 
      struct _MONITOR * pMonitor);
  BOOL  (WINAPI *pfnStartDocPort)(
      HANDLE hPort, 
      LPWSTR pPrinterName, 
      DWORD JobId, 
      DWORD Level, 
      LPBYTE pDocInfo);
  BOOL  (WINAPI *pfnWritePort)(
      HANDLE hPort, 
      LPBYTE pBuffer, 
      DWORD cbBuf, 
      LPDWORD pcbWritten);
  BOOL  (WINAPI *pfnReadPort)(
      HANDLE hPort, 
      LPBYTE pBuffer, 
      DWORD cbBuffer, 
      LPDWORD pcbRead);
  BOOL  (WINAPI *pfnEndDocPort)(HANDLE hPort);
  BOOL  (WINAPI *pfnClosePort)(HANDLE hPort);
  BOOL  (WINAPI *pfnAddPort)(
      LPWSTR pName, 
      HWND hWnd, 
      LPWSTR pMonitorName);
  BOOL  (WINAPI *pfnAddPortEx)(
      LPWSTR pName, 
      DWORD Level, 
      LPBYTE lpBuffer, 
      LPWSTR pMonitorName);
  BOOL  (WINAPI *pfnConfigurePort)(
      LPWSTR pName, 
      HWND hWnd, 
      LPWSTR pPortName);
  BOOL  (WINAPI *pfnDeletePort)(
      LPWSTR pName, 
      HWND hWnd, 
      LPWSTR pPortName);
  BOOL  (WINAPI *pfnGetPrinterDataFromPort)(
      HANDLE hPort, 
      DWORD ControlID, 
      LPWSTR pValueName, 
      LPWSTR lpInBuffer, 
      DWORD cbInBuffer, 
      LPWSTR lpOutBuffer, 
      DWORD cbOutBuffer, 
      LPDWORD lpcbReturned);
  BOOL  (WINAPI *pfnSetPortTimeOuts)(
      HANDLE hPort, 
      LPCOMMTIMEOUTS lpCTO, 
      DWORD reserved);
  BOOL  (WINAPI *pfnXcvOpenPort)(
      LPCWSTR pszObject, 
      ACCESS_MASK GrantedAccess, 
      PHANDLE phXcv);
  DWORD (WINAPI *pfnXcvDataPort)(
      HANDLE hXcv, 
      LPCWSTR pszDataName, 
      PBYTE pInputData, 
      DWORD cbInputData, 
      PBYTE pOutputData, 
      DWORD cbOutputData, 
      PDWORD pcbOutputNeeded);
  BOOL  (WINAPI *pfnXcvClosePort)(HANDLE hXcv);
} MONITOR, *LPMONITOR;
````


## -struct-fields




### -field pfnEnumPorts

A port monitor server DLL's <b>EnumPorts</b> function enumerates the ports that the port monitor supports.


### -field pfnOpenPort

Pointer to the print monitor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff559593">OpenPort</a> function.


### -field pfnOpenPortEx

A language monitor's <code>OpenPortEx</code> function opens a printer port.


### -field pfnStartDocPort

A print monitor's <code>StartDocPort</code> function performs the tasks required to start a print job on the specified port.


### -field pfnWritePort

Pointer to the print monitor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff563792">WritePort</a> function.


### -field pfnReadPort

Pointer to the print monitor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff561909">ReadPort</a> function.


### -field pfnEndDocPort

A print monitor's <b>EndDocPort</b> function performs the tasks required to end a print job on the specified port.


### -field pfnClosePort

Pointer to the print monitor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff545975">ClosePort</a> function.


### -field pfnAddPort

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff545022">AddPort</a> function is obsolete and is for use only with Windows NT 4.0 and previous versions.


<a href="https://msdn.microsoft.com/library/windows/hardware/ff545022">AddPort</a> creates a port and adds it to the list of ports currently supported by the specified monitor in the spooler environment.


### -field pfnAddPortEx

(Obsolete. Must be <b>NULL</b>.) Pointer to the print monitor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff545025">AddPortEx</a> function. (Port monitors only.)


### -field pfnConfigurePort

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff546286">ConfigurePort</a> function is obsolete and is for use only with Windows NT 4.0 and previous versions. For later versions of Windows, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff546290">ConfigurePortUI</a>.


<a href="https://msdn.microsoft.com/library/windows/hardware/ff546286">ConfigurePort</a> is a port management function that configures the specified port.


### -field pfnDeletePort

The <b>DeletePort</b> function is obsolete and is for use only with Windows NT 4.0 and previous versions.

<b>DeletePort</b> deletes a port from the monitor's environment.


### -field pfnGetPrinterDataFromPort

A port monitor's <b>GetPrinterDataFromPort</b> function obtains status information from a bidirectional printer and returns it to the caller.


### -field pfnSetPortTimeOuts

A port monitor server DLL's <code>SetPortTimeOuts</code> function sets port time-out values for an open port.


### -field pfnXcvOpenPort

Pointer to the print monitor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff564259">XcvOpenPort</a> function. (Port monitors only.)


### -field pfnXcvDataPort

Pointer to the print monitor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff564258">XcvDataPort</a> function. (Port monitors only.)


### -field pfnXcvClosePort

Pointer to the print monitor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff564254">XcvClosePort</a> function. (Port monitors only.)


## -remarks



The following table describes each member  in more detail.

<table>
<tr>
<td>Callback</td>
<td>Prototype</td>
<td>Parameters</td>
<td>Return values</td>
</tr>
<tr>
<td>AddPort</td>
<td>
<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>typedef BOOL ( WINAPI *pfnAddPort)(
  _In_ HANDLE hMonitor,
  _In_ LPWSTR pName,
  _In_ HWND   hWnd,
  _In_ LPWSTR pMonitorName
);
</pre>
</td>
</tr>
</table></span></div>
</td>
<td>
<ul>
<li><i>hMonitor [in]</i>Caller supplied monitor instance handle. This is the handle returned by the monitor's InitializePrintMonitor2 function. (This parameter does not exist if the print monitor supports InitializePrintMonitor2 instead of InitializePrintMonitor2.)



</li>
<li><i>pName [in]</i>Pointer to a null-terminated string that specifies the name of the server to which the port is connected. If pName is NULL, the port is local.



</li>
<li><i>hWnd [in]</i>Handle to the parent window of the dialog box in which the port name will be entered.



</li>
<li><i>pMonitorName [in]</i>Pointer to a null-terminated string that specifies the monitor associated with the port.

</li>
</ul>
</td>
<td>The return value is TRUE if the function is successful, and FALSE otherwise.

</td>
</tr>
<tr>
<td>ConfigurePort</td>
<td>
<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>typedef BOOL ( WINAPI *pfnConfigurePort)(
  _In_ HANDLE hMonitor,
  _In_ LPWSTR pName,
  _In_ HWND   hWnd,
  _In_ LPWSTR pPortName
);
</pre>
</td>
</tr>
</table></span></div>
</td>
<td>
<ul>
<li><i>hMonitor [in]</i>Caller supplied monitor instance handle. This is the handle returned by the monitor's InitializePrintMonitor2 function. (This parameter does not exist if the print monitor supports InitializePrintMonitor instead of InitializePrintMonitor2.)

</li>
<li><i>pName [in]</i>Pointer to a null-terminated string that specifies the name of the server on which the given port exists. If this string is NULL, the port is local.

</li>
<li><i>hWnd [in]</i>Handle to the parent window of the dialog box in which the configuration information will be entered.



</li>
<li><i>pPortName [in]</i>Pointer to a null-terminated string that specifies the name of the port to be configured.

</li>
</ul>
</td>
<td>The return value is TRUE if the function is successful.

</td>
</tr>
<tr>
<td>DeletePort</td>
<td>
<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>pfnDeletePort DeletePort;

BOOL WINAPI DeletePort(
  _In_ HANDLE hMonitor,
  _In_ LPWSTR pName,
  _In_ HWND   hWnd,
  _In_ LPWSTR pPortName
)
</pre>
</td>
</tr>
</table></span></div>
</td>
<td>
<ul>
<li><i>hMonitor [in]</i>Caller supplied monitor instance handle. This is the handle returned by the monitor's InitializePrintMonitor2 function. (This parameter does not exist if the print monitor supports InitializePrintMonitor instead of InitializePrintMonitor2.)



</li>
<li><i>pName [in]</i>Pointer to a null-terminated string that specifies the name of the server on which the port to be deleted exists. If this parameter is NULL, the port is local.

</li>
<li><i>hWnd [in]</i>Handle to the parent window of the port-deletion dialog box.

</li>
<li><i>pPortName [in] 
</i>Pointer to a null-terminated string that names the port to be deleted.

</li>
</ul>
</td>
<td>The return value is TRUE if the function is successful.</td>
</tr>
<tr>
<td>EndDocPort</td>
<td>
<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>typedef BOOL ( WINAPI *pfnEndDocPort)(
  _In_ HANDLE hPort
);
</pre>
</td>
</tr>
</table></span></div>
</td>
<td>
<ul>
<li><i>hPort [in] 
</i>Caller-supplied port handle.

</li>
</ul>
</td>
<td>If the operation succeeds, the function should return TRUE. Otherwise it should return FALSE.</td>
</tr>
<tr>
<td>EnumPorts</td>
<td>
<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>typedef BOOL ( WINAPI *pfnEnumPorts)(
  _In_     HANDLE  hMonitor,
  _In_opt_ LPWSTR  pName,
  _In_     DWORD   Level,
  _Out_    LPBYTE  pPorts,
  _In_     DWORD   cbBuf,
  _Out_    LPDWORD pcbNeeded,
  _Out_    LPDWORD pcReturned
);
</pre>
</td>
</tr>
</table></span></div>
</td>
<td>
<ul>
<li><i>hMonitor [in] 
</i>Caller supplied monitor instance handle. This is the handle returned by the monitor's InitializePrintMonitor2 function. (This parameter does not exist if the print monitor supports InitializePrintMonitor instead of InitializePrintMonitor2.)

</li>
<li><i>pName [in, optional]</i>Caller-supplied pointer to a string containing the name of the server whose ports are to be enumerated. A NULL pointer represents the system on which the port monitor server DLL is executing.



</li>
<li><i>Level [in] 
</i>Caller-supplied value indicating the type of structures to be returned in the buffer pointed to by pPorts. Possible values are 1:
 PORT_INFO_1
 
or 2:
 PORT_INFO_2.

</li>
<li><i>pPorts [out]</i>Caller-supplied pointer to a buffer to receive port information. Returned information must consist of an array of PORT_INFO_1 or PORT_INFO_2 structures, followed by the strings pointed to by structure members. These structures are described in the Microsoft Windows SDK documentation.



</li>
<li><i>cbBuf [in] 
</i>Caller-supplied size, in bytes, of the buffer pointed to by pPorts.

</li>
<li><i>pcbNeeded [out] 
</i>Caller-supplied pointer to a location to receive the buffer size, in bytes, required to contain all returned information.



</li>
<li><i>pcReturned [out] 
</i>Caller-supplied pointer to a location to receive the number enumerated ports.

</li>
</ul>
</td>
<td>If the operation succeeds, the function should return TRUE. Otherwise it should return FALSE.

</td>
</tr>
<tr>
<td>GetPrinterDataFromPort</td>
<td>
<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>pfnGetPrinterDataFromPort GetPrinterDataFromPort;

BOOL WINAPI GetPrinterDataFromPort(
  _In_  HANDLE  hPort,
  _In_  DWORD   ControlID,
  _In_  LPWSTR  pValueName,
  _In_  LPWSTR  lpInBuffer,
  _In_  DWORD   cbInBuffer,
  _Out_ LPWSTR  lpOutBuffer,
  _In_  DWORD   cbOutBuffer,
  _Out_ LPDWORD lpcbReturned
)</pre>
</td>
</tr>
</table></span></div>
</td>
<td>
<ul>
<li><i>hPort [in]</i>Caller-supplied port handle.

</li>
<li><i>ControlID [in]</i>Caller-supplied device I/O control code. A value of zero indicates a value name is supplied by pValueName.

</li>
<li><i>pValueName [in]</i>Caller-supplied pointer to a string identifying the information being requested. Valid only if ControlID is zero.

</li>
<li><i>lpInBuffer [in]</i>Caller-supplied pointer to a buffer containing input data. Used only if ControlID is nonzero.

</li>
<li><i>cbInBuffer [in]</i>Caller-supplied size, in bytes, of the buffer pointed to by lpInBuffer.



</li>
<li><i>lpOutBuffer [out] 


 


</i>Caller-supplied pointer to a buffer to receive the requested data.

</li>
<li><i>cbOutBuffer [in]</i>Caller-supplied size, in bytes, of the buffer pointed to by lpOutBuffer.

</li>
<li><i>lpcbReturned [out] 
</i>Caller-supplied pointer to a location to receive the number of bytes written into the buffer pointed to by lpOutBuffer.



</li>
</ul>
</td>
<td>If the operation succeeds, the function should return TRUE. Otherwise it should return FALSE.

</td>
</tr>
<tr>
<td>OpenPortEx</td>
<td>
<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>pfnOpenPortEx OpenPortEx;

BOOL WINAPI OpenPortEx(
  _In_  HANDLE           hMonitor,
  _In_  HANDLE           hMonitorPort,
  _In_  LPWSTR           pPortName,
  _In_  LPWSTR           pPrinterName,
  _Out_ PHANDLE          pHandle,
  _In_  struct _MONITOR2 *pMonitor
)
</pre>
</td>
</tr>
</table></span></div>
</td>
<td>
<ul>
<li><i>hMonitor [in]</i> 
Caller supplied language monitor instance handle. This is the handle returned by the monitor's InitializePrintMonitor2 function. (This parameter does not exist if the print monitor supports InitializePrintMonitor instead of InitializePrintMonitor2.) In a cluster environment, there can be multiple instances of language monitors.



</li>
<li><i>hMonitorPort [in]</i> 
Caller supplied port monitor instance handle. This is the handle returned by the monitor's InitializePrintMonitor2 function. (This parameter does not exist if the print monitor supports InitializePrintMonitor instead of InitializePrintMonitor2.) A language monitor must use this handle when it calls functions in the port monitor's MONITOR2 structure.



</li>
<li><i>pPortName [in]</i> 
Caller-supplied pointer to a string containing the name of the port to be opened.



</li>
<li><i>pPrinterName [in]</i>Caller-supplied pointer to a string containing the name of the printer that is connected to the port.



</li>
<li><i>pHandle [out]</i> 
Caller-supplied pointer to a location to receive a port handle.



</li>
<li><i>pMonitor [in] 
</i>Caller-supplied pointer to the MONITOR2 structure returned by a port monitor's InitializePrintMonitor2 function.



</li>
</ul>
</td>
<td>If the operation succeeds, the function should return TRUE. Otherwise it should return FALSE.</td>
</tr>
<tr>
<td>SetPortTimeOuts</td>
<td>
<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>BOOL (WINAPI *pfnSetPortTimeOuts)
    (
    _In_ HANDLE  hPort,
    _In_ LPCOMMTIMEOUTS lpCTO,
    _In_ DWORD   reserved    // must be set to 0
    );</pre>
</td>
</tr>
</table></span></div>
</td>
<td>
<ul>
<li><i>hPort [in] 

</i>Caller-supplied handle to the open port on which to set the time-out values.



</li>
<li><i>lpCTO [in] 
</i>Caller-supplied pointer to a COMMTIMEOUTS structure (described in the Microsoft Windows SDK documentation).



</li>
<li><i>reserved [in] 
</i>Reserved for future use. Must be set to zero.

</li>
</ul>
</td>
<td>If the operation succeeds, the function should return TRUE. Otherwise it should return FALSE.

</td>
</tr>
<tr>
<td>StartDocPort</td>
<td>
<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>typedef BOOL ( WINAPI *pfnStartDocPort)(
  _In_ HANDLE hPort,
  _In_ LPWSTR pPrinterName,
  _In_ DWORD  JobId,
  _In_ DWORD  Level,
  _In_ LPBYTE pDocInfo
);
</pre>
</td>
</tr>
</table></span></div>
</td>
<td>
<ul>
<li><i>hPort [in]</i>Caller-supplied port handle.



</li>
<li><i>pPrinterName [in] 
</i>Caller-supplied pointer to a string containing the printer name.



</li>
<li><i>JobId [in] 
</i>Caller-supplied, spooler-assigned job identifier.



</li>
<li><i>Level [in]</i>Caller-supplied value indicating the type of structure pointed to by pDocInfo. Possible values are 1:
 DOC_INFO_1 or
 
2:
 DOC_INFO_2.

</li>
<li><i>pDocInfo [in] 
</i>Caller-supplied pointer to a DOC_INFO_1 or DOC_INFO_2 structure. These structures are described in the Microsoft Windows SDK documentation.


</li>
</ul>
</td>
<td>If the operation succeeds, the function should return TRUE. Otherwise it should return FALSE</td>
</tr>
</table>
 

The spooler calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff545022">AddPort</a> when it receives an application request to add a port to its environment. The spooler forwards the call to the named port monitor on the named server.


<a href="https://msdn.microsoft.com/library/windows/hardware/ff545022">AddPort</a> allows a port to be added interactively. A monitor should prompt a user to enter the port name in a dialog box on the window associated with <i>hWnd</i>. <b>AddPort</b> should validate the entered port name by calling the Win32 EnumPorts function to ensure that no duplicate port names are added to the spooler environment. A monitor should also verify that the port is one that it supports.

The spooler does not support remote <a href="https://msdn.microsoft.com/library/windows/hardware/ff545022">AddPort</a> calls. Consequently, <b>AddPort</b> implementations can ignore the <i>pName</i> and <i>pMonitorName</i> parameters.

The spooler calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff546286">ConfigurePort</a> so a port monitor can perform port configuration. <b>ConfigurePort</b> can offer a dialog box to obtain some or all of the necessary port configuration information from the user.

The spooler does not support remote <a href="https://msdn.microsoft.com/library/windows/hardware/ff546286">ConfigurePort</a> calls; consequently, monitors can ignore the <i>pName</i> parameter.

The spooler calls <b>DeletePort</b> so a port monitor can delete a port from the monitor's environment. The monitor should delete the specified port from its state. The spooler will not call <b>DeletePort</b> on a monitor as long as a port is open.

Applications can delete local and remote ports. The printer UI displays a confirmation message box before the spooler calls <b>DeletePort</b>, so a monitor should ignore the <i>hWnd</i> parameter and not display another dialog box.


<a href="https://msdn.microsoft.com/26ba1c22-390a-4187-b67a-3f3497964f8e">Language monitors</a> and port monitor server DLLs are required to define an <b>EndDocPort</b> function and include the function's address in a <a href="..\winsplp\ns-winsplp-_monitor2.md">MONITOR2</a> structure.

The handle received as the function's hPort argument is the port handle that the monitor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff559593">OpenPort</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff559596">OpenPortEx</a> function supplied.

A language monitor's <b>EndDocPort</b> function typically calls the associated port monitor's <b>EndDocPort</b> function. It should also notify the spooler when the printing device has finished the job by calling <b>SetJob</b> (described in the Microsoft Windows SDK documentation), specifying a command of JOB_CONTROL_LAST_PAGE_EJECTED. Language monitors for bidirectional printers should not call <b>SetJob</b> until the printer has sent notification that the job is really finished.

A port monitor server DLL's <b>EndDocPort</b> function typically calls the <b>CloseHandle</b> function, described in the Windows SDK documentation, to close the handle that was previously obtained by calling <a href="https://msdn.microsoft.com/80a96083-4de9-4422-9705-b8ad2b6cbd1b">CreateFile</a> from within <a href="https://msdn.microsoft.com/library/windows/hardware/ff562710">StartDocPort</a>. It should also notify the spooler when the printing device has finished the job, by calling <b>SetJob</b>, specifying a command of JOB_CONTROL_SENT_TO_PRINTER. (If a spooler is communicating with the port through a language monitor, it doesn't consider the job complete until the language monitor sends JOB_CONTROL_LAST_PAGE_EJECTED.)

The <b>EndDocPort</b> function should free all resources that were allocated by the <b>StartDocPort</b> function. 

You might want to modify the <b>EndDocPort</b> function's behavior if the user has deleted or restarted the print job. The function can call <b>GetJob</b>, described in the Windows SDK documentation, and check for a status of JOB_STATUS_DELETING or JOB_STATUS_RESTART, to see if either of these events has occurred.

Port monitor server DLLs are required to define an <b>EnumPorts</b> function and include the function's address in a <a href="..\winsplp\ns-winsplp-_monitor2.md">MONITOR2</a> structure. Language monitors do not export this function.

The purpose of the <b>EnumPorts</b> function is to enumerate the ports currently supported by a print monitor. These ports are ones that were previously specified to the monitor's <a href="..\winsplp\nf-winsplp-addportui.md">AddPortUI</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff545025">AddPortEx</a> function.

The <b>EnumPorts</b> function should fill the buffer pointed to by <i>pPort</i> with an array of PORT_INFO_1 or PORT_INFO_2 structures. Then starting in a memory location following the last array element, the function must load all the strings pointed to by the array's structure members. Refer to localmon.dll, a <a href="https://msdn.microsoft.com/dac754bf-f39d-439c-974b-889436211ef3">sample port monitor</a>, for an example of how to do this. The function must also return the number of structures supplied (that is, the number of supported ports) by placing the number in the location pointed to by <i>pcReturned</i>.

The caller specifies the size of the supplied buffer in <i>cbBuf</i>. If the buffer is too small, the function should place the required buffer size in the location pointed to by <i>pcbNeeded</i>, call <b>SetLastError</b> (described in the Microsoft Windows SDK documentation) specifying ERROR_INSUFFICIENT_BUFFER, and return <b>FALSE</b>.

If <i>Level</i> contains an invalid level number, the function should call <b>SetLastError</b> specifying ERROR_INVALID_LEVEL, and return <b>FALSE</b>. Some port monitors only support a level value of 1.

The port monitor must support localization of strings pointed to by the <b>pMonitorName</b> and <b>pDescription</b> members of the PORT_INFO_2 structure. These strings should be defined in resource files and obtained by calling <b>LoadString</b> (described in the Windows SDK documentation).

The <b>fPortType</b> member of the PORT_INFO_2 structure is not used with NT-based operating systems.


<a href="https://msdn.microsoft.com/26ba1c22-390a-4187-b67a-3f3497964f8e">Language monitors</a> and port monitor server DLLs can optionally define a <b>GetPrinterDataFromPort</b> function and include the function's address in a <a href="..\winsplp\ns-winsplp-_monitor2.md">MONITOR2</a> structure.

The function is meant for use with bidirectional printers, and can be used in the following two ways:

<ul>
<li>
As a means for requesting a language monitor to poll the printer port, to obtain the current value of printer-specific information that is stored in the registry.

</li>
<li>
As a means for requesting a port monitor to send an I/O control code to the port driver.

</li>
</ul>
If a language monitor's <b>GetPrinterDataFromPort</b> function receives a string pointer in <i>pValueName</i>, it should return a value in the supplied output buffer. Typically, the string represents a registry value name, and the spooler calls <b>GetPrinterDataFromPort</b> when an application calls the <b>GetPrinterData</b> function (described in the Microsoft Windows SDK documentation).

The language monitor's responsibility is to send a command to the printer hardware by calling the port monitor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff563792">WritePort</a> function, and reading the response by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff561909">ReadPort</a>, to obtain the needed value. For example, pjlmon.dll, the <a href="https://msdn.microsoft.com/fd1ef790-c17b-4735-87fc-6b7b8597ac4d">sample language monitor</a>, can return values for a port's "Installed Memory" and "Available Memory" registry value names.

After the spooler calls <b>GetPrinterDataFromPort</b> to obtain a registry value, it updates the registry with the new value.

Typically, port monitors do not support calls to <b>GetPrinterDataFromPort</b> that include a string pointer in <i>pValueName</i>.

If a language monitor's <b>GetPrinterDataFromPort</b> function receives a nonzero I/O control code in <i>ControlID</i>, it should just call the associated port monitor's <b>GetPrinterDataFromPort</b> function and return the result. The <i>Kernel-Mode Drivers Reference</i> lists I/O control codes for parallel and serial ports.

When a port monitor's <b>GetPrinterDataFromPort</b> function receives a nonzero I/O control code in <i>ControlID</i>, it should call <b>DeviceIOControl</b> (described in the Windows SDK documentation) to pass the control code to the kernel-mode port driver. The <i>lpInBuffer</i>, <i>cbInBuffer</i>, <i>lpOutBuffer</i>, <i>cbOutBuffer</i>, and <i>lpcbReturned</i> parameter values should also be passed to <b>DeviceIOControl</b>.

Language monitors are required to define an <code>OpenPortEx</code> function and include its address in a <a href="..\winsplp\ns-winsplp-_monitor2.md">MONITOR2</a> structure. The <code>OpenPortEx</code> function is called by the print spooler when a print queue is being connected to a port. 

The <code>OpenPortEx</code> function's primary purpose is to return a port handle that the caller can use as an input argument for subsequent calls to the language monitor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff562710">StartDocPort</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff563792">WritePort</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff561909">ReadPort</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548742">EndDocPort</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550506">GetPrinterDataFromPort</a> functions. Because a language monitor typically implements these functions by calling the equivalent functions in its associated port monitor, a language monitor typically obtains a port handle by calling the port monitor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff559593">OpenPort</a> function. For more information see <a href="https://msdn.microsoft.com/6c3c55fc-40f3-43d7-b8a2-20fed8d28813">Language and Port Monitor Interaction</a>.

The <code>OpenPortEx</code> function's <i>pMonitor</i> parameter is a pointer to the port monitor's <a href="..\winsplp\ns-winsplp-_monitor2.md">MONITOR2</a> structure. This structure contains pointers to the port monitor's callable functions. The <code>OpenPortEx</code> function should check the structure to verify that all required function pointers are non-<b>NULL</b>. If the structure is valid, the function should copy it into local storage. Otherwise <code>OpenPortEx</code> should call <b>SetLastError</b>, specifying ERROR_INVALID_PRINT_MONITOR, and return <b>FALSE</b>.

Print monitor functions that accept a port handle as input do not also accept a monitor handle. Therefore, the <code>OpenPortEx</code> function must store the received monitor handle in a location that can be referenced by the port handle. This allows the functions that accept a port handle to reference the monitor handle.

A port monitor server DLL's <code>SetPortTimeOuts</code> function allows a language monitor to specify port time-out values for an open port. The function is optional, and must be provided only if the port monitor controls a port that allows the modification of port time-out values. If the function is defined, its address must be included in a <a href="..\winsplp\ns-winsplp-_monitor2.md">MONITOR2</a> structure.

The function is called by pjlmon.dll, the <a href="https://msdn.microsoft.com/fd1ef790-c17b-4735-87fc-6b7b8597ac4d">sample language monitor</a>, and you can write a customized language monitor that calls it. The print spooler does not call <code>SetPortTimeOuts</code>.

The port monitor should initialize the port's time-out values from within its <a href="https://msdn.microsoft.com/library/windows/hardware/ff559593">OpenPort</a> function.


<a href="https://msdn.microsoft.com/26ba1c22-390a-4187-b67a-3f3497964f8e">Language monitors</a> and port monitor server DLLs are required to define a <code>StartDocPort</code> function and include the function's address in a <a href="..\winsplp\ns-winsplp-_monitor2.md">MONITOR2</a> structure.

The handle received as the function's <i>hPort</i> argument is the port handle that the monitor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff559593">OpenPort</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff559596">OpenPortEx</a> function supplied.

A language monitor's <code>StartDocPort</code> function typically calls the associated port monitor's <code>StartDocPort</code> function.

A port monitor server DLL's <code>StartDocPort</code> function typically calls the <a href="https://msdn.microsoft.com/80a96083-4de9-4422-9705-b8ad2b6cbd1b">CreateFile</a> function, described in the Windows SDK documentation, to create a connection to the kernel-mode port driver.

If necessary, the port monitor should prevent other processes from using the specified port until <a href="https://msdn.microsoft.com/library/windows/hardware/ff548742">EndDocPort</a> is called. For example, a port monitor for a COM port must ensure that, while a spooler is sending printer data to the port, another application does not assume the port is connected to a particular communications device and then attempt to communicate with that device. This cautionary note does not apply to the local print provider, which guarantees that it never calls <code>StartDocPort</code> twice in succession without an intervening call to <b>EndDocPort</b>, but it does apply to print providers that do not make this guarantee.




## -see-also

<a href="..\winsplp\ns-winsplp-_monitor2.md">MONITOR2</a>



<a href="..\winsplp\ns-winsplp-_monitorui.md">MONITORUI</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20MONITOR structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

