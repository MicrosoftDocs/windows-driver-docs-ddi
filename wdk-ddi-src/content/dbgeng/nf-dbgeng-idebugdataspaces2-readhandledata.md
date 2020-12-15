---
UID: NF:dbgeng.IDebugDataSpaces2.ReadHandleData
title: IDebugDataSpaces2::ReadHandleData (dbgeng.h)
description: The ReadHandleData method retrieves information about a system object specified by a system handle.
old-location: debugger\readhandledata.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugDataSpaces2::ReadHandleData"]
ms.keywords: IDebugDataSpaces2 interface [Windows Debugging],ReadHandleData method, IDebugDataSpaces2.ReadHandleData, IDebugDataSpaces2::ReadHandleData, IDebugDataSpaces3 interface [Windows Debugging],ReadHandleData method, IDebugDataSpaces3::ReadHandleData, IDebugDataSpaces4 interface [Windows Debugging],ReadHandleData method, IDebugDataSpaces4::ReadHandleData, IDebugDataSpaces_cbad043a-7b6e-4c5c-8a14-9a7b20a0b125.xml, ReadHandleData, ReadHandleData method [Windows Debugging], ReadHandleData method [Windows Debugging],IDebugDataSpaces2 interface, ReadHandleData method [Windows Debugging],IDebugDataSpaces3 interface, ReadHandleData method [Windows Debugging],IDebugDataSpaces4 interface, dbgeng/IDebugDataSpaces2::ReadHandleData, dbgeng/IDebugDataSpaces3::ReadHandleData, dbgeng/IDebugDataSpaces4::ReadHandleData, debugger.readhandledata
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugDataSpaces2::ReadHandleData
 - dbgeng/IDebugDataSpaces2::ReadHandleData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugDataSpaces2.ReadHandleData
 - IDebugDataSpaces3.ReadHandleData
 - IDebugDataSpaces4.ReadHandleData
---

# IDebugDataSpaces2::ReadHandleData


## -description

The <b>ReadHandleData</b> method retrieves information about a system object specified by a system handle.

## -parameters

### -param Handle 

[in]
Specifies the system handle of the object whose data is requested.  See Handles for information about system handles.

### -param DataType 

[in]
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

In this case, the argument <i>Buffer</i> can be considered to have type <a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_handle_data_basic">PDEBUG_HANDLE_DATA_BASIC</a>.

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
Returns the number of handles held by the object.  This is similar to the field <a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_handle_data_basic">DEBUG_HANDLE_DATA_BASIC</a>.<b>HandleCount</b>.

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

### -param Buffer 

[out, optional]
Receives the object data.  Upon successful completion of the method, the contents of this buffer may be accessed by casting <i>Buffer</i> to the type specified in the above table.

If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

### -param BufferSize 

[in]
Specifies the size in bytes of the buffer <i>Buffer</i>.  This is the maximum number of bytes that will be returned.

### -param DataSize 

[out, optional]
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
 

This method can also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

## -remarks

This method is only available in user-mode debugging.

## -see-also

Handles



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces2">IDebugDataSpaces2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces3">IDebugDataSpaces3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces4">IDebugDataSpaces4</a>
