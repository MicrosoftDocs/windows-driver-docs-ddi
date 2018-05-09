---
UID: NF:winsplp.InitializePrintMonitor2
title: InitializePrintMonitor2 function
author: windows-driver-content
description: A print monitor's InitializePrintMonitor2 function initializes a print monitor for use with clustered print servers.
old-location: print\initializeprintmonitor2.htm
old-project: print
ms.assetid: 73348405-0cc1-412a-b9b1-cfcc300190d7
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: InitializePrintMonitor2, InitializePrintMonitor2 function [Print Devices], print.initializeprintmonitor2, spoolfnc_34b0ce7d-8bb5-4cb1-9539-cd3b1b0113f4.xml, winsplp/InitializePrintMonitor2
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
-	InitializePrintMonitor2
product:
- Windows
targetos: Windows
req.typenames: 
---

# InitializePrintMonitor2 function


## -description


A print monitor's <b>InitializePrintMonitor2</b> function initializes a print monitor for use with clustered print servers.


## -parameters




### -param pMonitorInit [in]

Caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557535">MONITORINIT</a> structure.


### -param phMonitor [out]

Caller-supplied location in which the function returns a monitor handle.


## -returns



If the operation succeeds, the function should return a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557532">MONITOR2</a> structure. Otherwise the function should call SetLastError (described in the Microsoft Windows SDK documentation) to set an error code, and return <b>NULL</b>.




## -remarks



The <b>InitializePrintMonitor2</b> function must be exported by <a href="https://msdn.microsoft.com/26ba1c22-390a-4187-b67a-3f3497964f8e">language monitors</a> and by port monitor server DLLs. The function is called immediately after the monitor DLL is loaded, and is not called again until the DLL is reloaded. Its purposes are to allow the monitor to initialize itself, and to provide the spooler with pointers to internal monitor functions. Function pointers are contained in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557532">MONITOR2</a> structure.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff557532">MONITOR2</a> structure is larger in Windows XP than it was in Windows 2000. In order to ensure that a monitor developed with the Windows XP Driver Development Kit (DDK) will install on Windows XP and Windows 2000, the monitor must do the following:

<ul>
<li>
Perform a run-time check to determine which operating system version the monitor is running on.

</li>
<li>
If the monitor is running on Windows 2000, it must set the <b>cbSize</b> member of the MONITOR2 structure to MONITOR2_SIZE_WIN2K (defined in Winsplp.h), the size appropriate for Windows 2000 version of this structure.

</li>
</ul>
The following function determines whether the current operating system version is Windows 2000.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BOOL  Is_Win2000()
{
  OSVERSIONINFOEX osvi;
  DWORDLONG dwlConditionMask = 0;

  // Initialize the OSVERSIONINFOEX structure.

  ZeroMemory(&amp;osvi, sizeof(OSVERSIONINFOEX));
  osvi.dwOSVersionInfoSize = sizeof(OSVERSIONINFOEX);
  osvi.dwMajorVersion = 5;
  osvi.dwMinorVersion = 0;

  // Initialize the condition mask.
  VER_SET_CONDITION( dwlConditionMask, VER_MAJORVERSION, VER_EQUAL );
  VER_SET_CONDITION( dwlConditionMask, VER_MINORVERSION, VER_EQUAL );

  // Perform the test.
  return VerifyVersionInfo(
      &amp;osvi,
      VER_MAJORVERSION | VER_MINORVERSION,
      dwlConditionMask);
}</pre>
</td>
</tr>
</table></span></div>
For a monitor that is loading on Windows 2000, the following code sets the MONITOR2 structure's <b>cbSize</b> member appropriately.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>if ( Is_Win2000( ) )
    Monitor2.cbSize = MONITOR2_SIZE_WIN2K;</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557535">MONITORINIT</a>
 

 

