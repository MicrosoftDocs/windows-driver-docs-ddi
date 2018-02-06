---
UID: NF:dbgeng.IDebugSystemObjects4.GetCurrentProcessExecutableName
title: IDebugSystemObjects4::GetCurrentProcessExecutableName method
author: windows-driver-content
description: The GetCurrentProcessExecutableName method returns the name of executable file loaded in the current process.
old-location: debugger\getcurrentprocessexecutablename.htm
old-project: debugger
ms.assetid: ea968316-a53d-4ab1-966a-5c699ffb8f2a
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetCurrentProcessExecutableName method [Windows Debugging], IDebugSystemObjects2 interface, GetCurrentProcessExecutableName method [Windows Debugging], IDebugSystemObjects4 interface, dbgeng/IDebugSystemObjects2::GetCurrentProcessExecutableName, GetCurrentProcessExecutableName method [Windows Debugging], IDebugSystemObjects3 interface, GetCurrentProcessExecutableName, GetCurrentProcessExecutableName method [Windows Debugging], dbgeng/IDebugSystemObjects4::GetCurrentProcessExecutableName, IDebugSystemObjects2::GetCurrentProcessExecutableName, IDebugSystemObjects::GetCurrentProcessExecutableName, debugger.getcurrentprocessexecutablename, IDebugSystemObjects4, IDebugSystemObjects4::GetCurrentProcessExecutableName, dbgeng/IDebugSystemObjects3::GetCurrentProcessExecutableName, IDebugSystemObjects4 interface [Windows Debugging], GetCurrentProcessExecutableName method, IDebugSystemObjects_2659a668-4ecb-44de-b287-b4adc830f8c4.xml, GetCurrentProcessExecutableName method [Windows Debugging], IDebugSystemObjects interface, IDebugSystemObjects3::GetCurrentProcessExecutableName, IDebugSystemObjects2 interface [Windows Debugging], GetCurrentProcessExecutableName method, dbgeng/IDebugSystemObjects::GetCurrentProcessExecutableName, IDebugSystemObjects3 interface [Windows Debugging], GetCurrentProcessExecutableName method, IDebugSystemObjects interface [Windows Debugging], GetCurrentProcessExecutableName method
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugSystemObjects.GetCurrentProcessExecutableName
-	IDebugSystemObjects2.GetCurrentProcessExecutableName
-	IDebugSystemObjects3.GetCurrentProcessExecutableName
-	IDebugSystemObjects4.GetCurrentProcessExecutableName
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugSystemObjects4::GetCurrentProcessExecutableName method


## -description


The <b>GetCurrentProcessExecutableName</b>  method returns the name of executable file loaded in the current process.


## -syntax


````
HRESULT GetCurrentProcessExecutableName(
  [out, optional] PSTR   Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG ExeSize
);
````


## -parameters




### -param Buffer [out, optional]

Receives the name of the executable file.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

Specifies the size in characters of the buffer <i>Buffer</i>.


### -param ExeSize [out, optional]

Receives the size in characters of the name of the executable file.  If <i>ExeSize</i> is <b>NULL</b>, this information is not returned.


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
The method was successful. However, the buffer was not large enough to hold the name of the executable file and it was truncated.

</td>
</tr>
</table> 



## -remarks


These methods are only available in user-mode debugging.

If the engine cannot determine the name of the executable file, it writes the string "?NoImage?" to the buffer.

For more information about processes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.


