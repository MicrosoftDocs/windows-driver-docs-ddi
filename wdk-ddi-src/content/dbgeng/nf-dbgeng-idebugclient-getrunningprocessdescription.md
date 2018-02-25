---
UID: NF:dbgeng.IDebugClient.GetRunningProcessDescription
title: IDebugClient::GetRunningProcessDescription method
author: windows-driver-content
description: The GetRunningProcessDescription method returns a description of the process that includes the executable image name, the service names, the MTS package names, and the command line.
old-location: debugger\getrunningprocessdescription.htm
old-project: debugger
ms.assetid: 1fdc4b85-d969-4433-8409-512f3f52cbbb
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., :, C, D, G, GetRunningProcessDescription method [Windows Debugging], GetRunningProcessDescription method [Windows Debugging], IDebugClient interface, GetRunningProcessDescription method [Windows Debugging], IDebugClient2 interface, GetRunningProcessDescription method [Windows Debugging], IDebugClient3 interface, GetRunningProcessDescription method [Windows Debugging], IDebugClient4 interface, GetRunningProcessDescription method [Windows Debugging], IDebugClient5 interface, GetRunningProcessDescription,IDebugClient.GetRunningProcessDescription, I, IDebugClient, IDebugClient interface [Windows Debugging], GetRunningProcessDescription method, IDebugClient2 interface [Windows Debugging], GetRunningProcessDescription method, IDebugClient2::GetRunningProcessDescription, IDebugClient3 interface [Windows Debugging], GetRunningProcessDescription method, IDebugClient3::GetRunningProcessDescription, IDebugClient4 interface [Windows Debugging], GetRunningProcessDescription method, IDebugClient4::GetRunningProcessDescription, IDebugClient5 interface [Windows Debugging], GetRunningProcessDescription method, IDebugClient5::GetRunningProcessDescription, IDebugClient::GetRunningProcessDescription, IDebugClient_e5736881-635f-4998-809b-d210bf447a36.xml, P, R, b, c, dbgeng/IDebugClient2::GetRunningProcessDescription, dbgeng/IDebugClient3::GetRunningProcessDescription, dbgeng/IDebugClient4::GetRunningProcessDescription, dbgeng/IDebugClient5::GetRunningProcessDescription, dbgeng/IDebugClient::GetRunningProcessDescription, debugger.getrunningprocessdescription, e, g, i, l, n, o, p, r, s, t, u"
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
-	IDebugClient.GetRunningProcessDescription
-	IDebugClient2.GetRunningProcessDescription
-	IDebugClient3.GetRunningProcessDescription
-	IDebugClient4.GetRunningProcessDescription
-	IDebugClient5.GetRunningProcessDescription
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient::GetRunningProcessDescription method


## -description


The <b>GetRunningProcessDescription</b>  method returns a description of the process that includes the executable image name, the service names, the MTS package names, and the command line.


## -syntax


````
HRESULT GetRunningProcessDescription(
  [in]            ULONG64 Server,
  [in]            ULONG   SystemId,
  [in]            ULONG   Flags,
  [out, optional] PSTR    ExeName,
  [in]            ULONG   ExeNameSize,
  [out, optional] PULONG  ActualExeNameSize,
  [out, optional] PSTR    Description,
  [in]            ULONG   DescriptionSize,
  [out, optional] PULONG  ActualDescriptionSize
);
````


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548265">GetRunningProcessSystemIds</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539237">ConnectProcessServer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540055">CreateProcessAndAttach2</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548254">GetRunningProcessSystemIdByExecutableName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538150">AttachProcess</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::GetRunningProcessDescription method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

