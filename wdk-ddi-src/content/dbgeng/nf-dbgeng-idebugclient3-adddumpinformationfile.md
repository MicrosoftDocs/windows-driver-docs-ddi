---
UID: NF:dbgeng.IDebugClient3.AddDumpInformationFile
title: IDebugClient3::AddDumpInformationFile method
author: windows-driver-content
description: The AddDumpInformationFile method registers additional files containing supporting information that will be used when opening a dump file. The Unicode version of this method is AddDumpInformationFileWide.
old-location: debugger\adddumpinformationfile.htm
old-project: debugger
ms.assetid: c111eb7e-7c42-4848-89d3-177f240fff7f
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugClient4 interface [Windows Debugging], AddDumpInformationFile method, IDebugClient3, IDebugClient_11398d02-21c4-4ec5-9e1c-8e7e87808c35.xml, IDebugClient5::AddDumpInformationFile, AddDumpInformationFile method [Windows Debugging], IDebugClient4 interface, dbgeng/IDebugClient5::AddDumpInformationFile, dbgeng/IDebugClient4::AddDumpInformationFile, IDebugClient3 interface [Windows Debugging], AddDumpInformationFile method, IDebugClient2 interface [Windows Debugging], AddDumpInformationFile method, IDebugClient2, dbgeng/IDebugClient3::AddDumpInformationFile, AddDumpInformationFile, debugger.adddumpinformationfile, IDebugClient5 interface [Windows Debugging], AddDumpInformationFile method, IDebugClient4::AddDumpInformationFile, dbgeng/IDebugClient2::AddDumpInformationFile, AddDumpInformationFile method [Windows Debugging], IDebugClient3::AddDumpInformationFile, AddDumpInformationFile method [Windows Debugging], IDebugClient3 interface, IDebugClient2::AddDumpInformationFile, AddDumpInformationFile method [Windows Debugging], IDebugClient2 interface, AddDumpInformationFile method [Windows Debugging], IDebugClient5 interface
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
-	IDebugClient2.AddDumpInformationFile
-	IDebugClient3.AddDumpInformationFile
-	IDebugClient4.AddDumpInformationFile
-	IDebugClient5.AddDumpInformationFile
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugClient3::AddDumpInformationFile method


## -description


The <b>AddDumpInformationFile</b> method registers additional files containing supporting information that will be used when opening a dump file.  The Unicode version of this method is <a href="https://msdn.microsoft.com/library/windows/hardware/ff537874">AddDumpInformationFileWide</a>.


## -syntax


````
HRESULT AddDumpInformationFile(
  [in] PCSTR InfoFile,
  [in] ULONG Type
);
````


## -parameters




### -param InfoFile [in]

Specifies the name of the file containing the supporting information.


### -param Type [in]

Specifies the type of the file <i>InfoFile</i>.  Currently, only files containing paging file information are supported, and <i>Type</i> must be set to DEBUG_DUMP_FILE_PAGE_FILE_DUMP.


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



If supporting information is to be used when opening a dump file, this method or <a href="https://msdn.microsoft.com/library/windows/hardware/ff537874">AddDumpInformationFileWide</a> must be called before <a href="https://msdn.microsoft.com/library/windows/hardware/ff552322">OpenDumpFile</a> is called. If a session has already started, this method cannot be used.

For more information about crash dump files, see <a href="https://msdn.microsoft.com/83fb6753-a6c1-4899-9b06-a6331b3c31a8">Dump File Targets</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552324">OpenDumpFileWide</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547887">GetNumberDumpFiles</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537874">AddDumpInformationFileWide</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546586">GetDumpFile</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552322">OpenDumpFile</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient2::AddDumpInformationFile method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

