---
UID: NF:dbgeng.IDebugClient3.GetRunningProcessDescriptionWide
title: IDebugClient3::GetRunningProcessDescriptionWide method
author: windows-driver-content
description: The GetRunningProcessDescriptionWide method returns a description of the process that includes the executable image name, the service names, the MTS package names, and the command line.
old-location: debugger\getrunningprocessdescriptionwide.htm
old-project: debugger
ms.assetid: 1af85bbe-19e8-4e16-a598-f9822fd6f766
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetRunningProcessDescriptionWide method [Windows Debugging], GetRunningProcessDescriptionWide method [Windows Debugging], IDebugClient3 interface, GetRunningProcessDescriptionWide method [Windows Debugging], IDebugClient4 interface, GetRunningProcessDescriptionWide method [Windows Debugging], IDebugClient5 interface, GetRunningProcessDescriptionWide,IDebugClient3.GetRunningProcessDescriptionWide, IDebugClient3, IDebugClient3 interface [Windows Debugging], GetRunningProcessDescriptionWide method, IDebugClient3::GetRunningProcessDescriptionWide, IDebugClient4 interface [Windows Debugging], GetRunningProcessDescriptionWide method, IDebugClient4::GetRunningProcessDescriptionWide, IDebugClient5 interface [Windows Debugging], GetRunningProcessDescriptionWide method, IDebugClient5::GetRunningProcessDescriptionWide, dbgeng/IDebugClient3::GetRunningProcessDescriptionWide, dbgeng/IDebugClient4::GetRunningProcessDescriptionWide, dbgeng/IDebugClient5::GetRunningProcessDescriptionWide, debugger.getrunningprocessdescriptionwide
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
-	dbgeng.h
api_name:
-	IDebugClient3.GetRunningProcessDescriptionWide
-	IDebugClient4.GetRunningProcessDescriptionWide
-	IDebugClient5.GetRunningProcessDescriptionWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient3::GetRunningProcessDescriptionWide method


## -description


The <b>GetRunningProcessDescriptionWide</b> method returns a description of the process that includes the executable image name, the service names, the MTS package names, and the command line.


## -parameters




### -param Server [in]

Specifies the process server to query for the process description.  If <i>Server</i> is zero, the engine will query information about the local process directly.


### -param SystemId [in]

Specifies the process ID of the process whose description is desired.


### -param Flags [in]

Specifies a bit-set containing options that affect the behavior of this method.  <i>Flags</i> can contain the following bit flags:

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_PROC_DESC_NO_PATHS

</td>
<td>
Return only file names without path names.

</td>
</tr>
<tr>
<td>
DEBUG_PROC_DESC_NO_SERVICES

</td>
<td>
Do not look up service names.

</td>
</tr>
<tr>
<td>
DEBUG_PROC_DESC_NO_MTS_PACKAGES

</td>
<td>
Do not look up MTS package names.

</td>
</tr>
<tr>
<td>
DEBUG_PROC_DESC_NO_COMMAND_LINE

</td>
<td>
Do not retrieve the command line.

</td>
</tr>
</table>
 


### -param ExeName [out, optional]

Receives the name of the executable file used to start the process.  If <i>ExeName</i> is <b>NULL</b>, this information is not returned.


### -param ExeNameSize [in]

Specifies the size in characters of the buffer <i>ExeNameSize</i>.


### -param ActualExeNameSize [out, optional]

Receives the size in characters of the executable file name.  If <i>ExeNameSize</i> is <b>NULL</b>, this information is not returned.


### -param Description [out, optional]

Receives extra information about the process, including service names, MTS package names, and the command line.  If <i>Description</i> is <b>NULL</b>, this information is not returned.


### -param DescriptionSize [in]

Specifies the size in characters of the buffer <i>Description</i>.


### -param ActualDescriptionSize [out, optional]

Receives the size in characters of the extra information.  If <i>ActualDescriptionSize</i> is <b>NULL</b>, this information is not returned.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
The method was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.  However, either <i>ExeNameSize</i> or <i>DescriptionSize</i> were smaller than the size of the respective string and the string was truncated to fit inside the buffer.

</td>
</tr>
</table>
 




## -remarks



This method is available only for live user-mode debugging.

For more information about creating and attaching to live user-mode targets, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552020">Live User-Mode Targets</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538150">AttachProcess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539237">ConnectProcessServer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540055">CreateProcessAndAttach2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548254">GetRunningProcessSystemIdByExecutableName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548265">GetRunningProcessSystemIds</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550488">IDebugClient3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550494">IDebugClient4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>
 

 

