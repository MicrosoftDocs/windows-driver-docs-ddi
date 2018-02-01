---
UID: NF:dbgeng.IDebugClient.GetOutputLinePrefix
title: IDebugClient::GetOutputLinePrefix method
author: windows-driver-content
description: Gets the prefix used for multiple lines of output.
old-location: debugger\idebugclient_getoutputlineprefix.htm
old-project: debugger
ms.assetid: FE836B10-1782-4B0E-9D4B-2740FE94B6E1
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.idebugclient_getoutputlineprefix, GetOutputLinePrefix, IDebugClient interface [Windows Debugging], GetOutputLinePrefix method, IDebugClient, GetOutputLinePrefix method [Windows Debugging], IDebugClient interface, dbgeng/IDebugClient::GetOutputLinePrefix, GetOutputLinePrefix method [Windows Debugging], IDebugClient::GetOutputLinePrefix
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
-	IDebugClient.GetOutputLinePrefix
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient::GetOutputLinePrefix method


## -description


    Gets the prefix used for multiple lines of output.


## -syntax


````
HRESULT GetOutputLinePrefix(
  [out]           writes_opt_(BufferSize) PSTR Buffer,
  [in]            ULONG                        BufferSize,
  [out, optional] PULONG                       PrefixSize
);
````


## -parameters




### -param Buffer [out]

A pointer to the buffer to get the prefix.


### -param BufferSize [in]

The size of the buffer.


### -param PrefixSize [out, optional]

A pointer to the size of the buffer.


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


Some of the engine commands produce
    multiple lines of output.  A prefix can be added to each line. 

 The prefix value  is not a general setting for any output
    that contains a newline. Methods which use
    the line prefix are marked in their documentation.



## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::GetOutputLinePrefix method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

