---
UID: NF:dbgeng.IDebugDataSpaces4.ReadHandleData
title: IDebugDataSpaces4::ReadHandleData method
author: windows-driver-content
description: The ReadHandleData method retrieves information about a system object specified by a system handle.
old-location: debugger\readhandledata.htm
old-project: debugger
ms.assetid: 9ad8e8c1-6aee-4eac-93e6-5997212c63d0
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugDataSpaces2 interface [Windows Debugging], ReadHandleData method, ReadHandleData method [Windows Debugging], IDebugDataSpaces3 interface, IDebugDataSpaces_cbad043a-7b6e-4c5c-8a14-9a7b20a0b125.xml, ReadHandleData method [Windows Debugging], IDebugDataSpaces2 interface, ReadHandleData method [Windows Debugging], dbgeng/IDebugDataSpaces4::ReadHandleData, dbgeng/IDebugDataSpaces3::ReadHandleData, dbgeng/IDebugDataSpaces2::ReadHandleData, IDebugDataSpaces4 interface [Windows Debugging], ReadHandleData method, IDebugDataSpaces4::ReadHandleData, debugger.readhandledata, IDebugDataSpaces3::ReadHandleData, IDebugDataSpaces3 interface [Windows Debugging], ReadHandleData method, ReadHandleData, ReadHandleData method [Windows Debugging], IDebugDataSpaces4 interface, IDebugDataSpaces4, IDebugDataSpaces2::ReadHandleData
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
-	IDebugDataSpaces2.ReadHandleData
-	IDebugDataSpaces3.ReadHandleData
-	IDebugDataSpaces4.ReadHandleData
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugDataSpaces4::ReadHandleData method


## -description


The <b>ReadHandleData</b> method retrieves information about a system object specified by a system handle.


## -syntax


````
HRESULT ReadHandleData(
  [in]            ULONG64 Handle,
  [in]            ULONG   DataType,
  [out, optional] PVOID   Buffer,
  [in]            ULONG   BufferSize,
  [out, optional] PULONG  DataSize
);
````


## -parameters




### -param Handle [in]

Specifies the system handle of the object whose data is requested.  See Handles for information about system handles.


### -param DataType [in]

Specifies the data type to return for the system handle.  The following table contains the valid values, along with the corresponding return type:
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_HANDLE_DATA_TYPE_BASIC

</td>
<td>
Returns basic information about the system object.

In this case, the argument <i>Buffer</i> can be considered to have type <a href="..\dbgeng\ns-dbgeng-_debug_handle_data_basic.md">PDEBUG_HANDLE_DATA_BASIC</a>.

</td>
</tr>
<tr>
<td>
DEBUG_HANDLE_DATA_TYPE_TYPE_NAME

</td>
<td>
Returns the name of the object type.  For example, "Process" or "Thread".

In this case, the argument <i>Buffer</i> can be considered to have type PSTR.

</td>
</tr>
<tr>
<td>
DEBUG_HANDLE_DATA_TYPE_OBJECT_NAME

</td>
<td>
Returns the name of the object.  This includes its location in the object directory.

In this case, the argument <i>Buffer</i> can be considered to have type PSTR.

</td>
</tr>
<tr>
<td>
DEBUG_HANDLE_DATA_TYPE_HANDLE_COUNT

</td>
<td>
Returns the number of handles held by the object.  This is similar to the field <a href="..\dbgeng\ns-dbgeng-_debug_handle_data_basic.md">DEBUG_HANDLE_DATA_BASIC</a>.<b>HandleCount</b>.

In this case, the argument <i>Buffer</i> can be considered to have type PULONG.

</td>
</tr>
<tr>
<td>
DEBUG_HANDLE_DATA_TYPE_TYPE_NAME_WIDE

</td>
<td>
Returns the name of the object type.

In this case, the argument <i>Buffer</i> can be considered to have type PWSTR

</td>
</tr>
<tr>
<td>
DEBUG_HANDLE_DATA_TYPE_OBJECT_NAME_WIDE

</td>
<td>
Returns the name of the object.

In this case, the argument <i>Buffer</i> can be considered to have type PWSTR.

</td>
</tr>
</table> 


### -param Buffer [out, optional]

Receives the object data.  Upon successful completion of the method, the contents of this buffer may be accessed by casting <i>Buffer</i> to the type specified in the above table.

If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

Specifies the size in bytes of the buffer <i>Buffer</i>.  This is the maximum number of bytes that will be returned.


### -param DataSize [out, optional]

Receives the size of the data in bytes.  If <i>DataSize</i> is <b>NULL</b>, this information is not returned.


## -returns


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

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.



## -remarks


This method is only available in user-mode debugging.



## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugdataspaces2.md">IDebugDataSpaces2</a>

<a href="..\dbgeng\nn-dbgeng-idebugdataspaces3.md">IDebugDataSpaces3</a>

<a href="..\dbgeng\nn-dbgeng-idebugdataspaces4.md">IDebugDataSpaces4</a>

Handles

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugDataSpaces2::ReadHandleData method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

