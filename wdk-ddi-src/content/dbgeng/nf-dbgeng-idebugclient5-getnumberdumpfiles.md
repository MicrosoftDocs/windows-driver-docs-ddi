---
UID: NF:dbgeng.IDebugClient5.GetNumberDumpFiles
title: IDebugClient5::GetNumberDumpFiles method
author: windows-driver-content
description: The GetNumberDumpFiles method returns the number of files containing supporting information that were used when opening the current dump target.
old-location: debugger\getnumberdumpfiles.htm
old-project: debugger
ms.assetid: d3fa4314-2f11-4ac4-86bd-3eb3f3ea9029
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetNumberDumpFiles method [Windows Debugging], GetNumberDumpFiles method [Windows Debugging], IDebugClient4 interface, GetNumberDumpFiles method [Windows Debugging], IDebugClient5 interface, GetNumberDumpFiles,IDebugClient5.GetNumberDumpFiles, IDebugClient4 interface [Windows Debugging], GetNumberDumpFiles method, IDebugClient4::GetNumberDumpFiles, IDebugClient5, IDebugClient5 interface [Windows Debugging], GetNumberDumpFiles method, IDebugClient5::GetNumberDumpFiles, IDebugClient_db74cf2c-c7e7-46c2-be98-f4023b22c5c3.xml, dbgeng/IDebugClient4::GetNumberDumpFiles, dbgeng/IDebugClient5::GetNumberDumpFiles, debugger.getnumberdumpfiles
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
-	IDebugClient4.GetNumberDumpFiles
-	IDebugClient5.GetNumberDumpFiles
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient5::GetNumberDumpFiles method


## -description


The <b>GetNumberDumpFiles</b> method returns the number of files containing supporting information that were used when opening the current dump target.


## -syntax


````
HRESULT GetNumberDumpFiles(
  [out] PULONG Number
);
````


## -parameters




### -param Number [out]

Receives the number of files.


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
</table>
 




## -remarks



For more information about crash dump files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542783">Dump-File Targets</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537874">AddDumpInformationFileWide</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546586">GetDumpFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537865">AddDumpInformationFile</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient4::GetNumberDumpFiles method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

