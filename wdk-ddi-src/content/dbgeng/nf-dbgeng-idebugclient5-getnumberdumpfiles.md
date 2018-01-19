---
UID: NF:dbgeng.IDebugClient5.GetNumberDumpFiles
title: IDebugClient5::GetNumberDumpFiles method
author: windows-driver-content
description: The GetNumberDumpFiles method returns the number of files containing supporting information that were used when opening the current dump target.
old-location: debugger\getnumberdumpfiles.htm
old-project: debugger
ms.assetid: d3fa4314-2f11-4ac4-86bd-3eb3f3ea9029
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugClient5, IDebugClient5::GetNumberDumpFiles, GetNumberDumpFiles
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
req.alt-api: IDebugClient4.GetNumberDumpFiles,IDebugClient5.GetNumberDumpFiles
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
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
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
For more information about crash dump files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542783">Dump-File Targets</a>.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546586">GetDumpFile</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537865">AddDumpInformationFile</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537874">AddDumpInformationFileWide</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient4::GetNumberDumpFiles method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

