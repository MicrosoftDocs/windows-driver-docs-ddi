---
UID: NF:dbgeng.IDebugDataSpaces3.ReadTagged
title: IDebugDataSpaces3::ReadTagged (dbgeng.h)
description: The ReadTagged method reads the tagged data that might be associated with a debugger session.
old-location: debugger\readtagged.htm
tech.root: debugger
ms.assetid: d7ca67d2-7156-44f7-ab16-178e6307e412
ms.date: 05/03/2018
keywords: ["IDebugDataSpaces3::ReadTagged"]
ms.keywords: IDebugDataSpaces3 interface [Windows Debugging],ReadTagged method, IDebugDataSpaces3.ReadTagged, IDebugDataSpaces3::ReadTagged, IDebugDataSpaces4 interface [Windows Debugging],ReadTagged method, IDebugDataSpaces4::ReadTagged, IDebugDataSpaces_cdf64ddf-da14-4607-8df2-1d4703a2eebf.xml, ReadTagged, ReadTagged method [Windows Debugging], ReadTagged method [Windows Debugging],IDebugDataSpaces3 interface, ReadTagged method [Windows Debugging],IDebugDataSpaces4 interface, dbgeng/IDebugDataSpaces3::ReadTagged, dbgeng/IDebugDataSpaces4::ReadTagged, debugger.readtagged
f1_keywords:
 - "dbgeng/IDebugDataSpaces3.ReadTagged"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugDataSpaces3.ReadTagged
- IDebugDataSpaces4.ReadTagged
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugDataSpaces3::ReadTagged


## -description


The <b>ReadTagged</b> method reads the tagged data that might be associated with a debugger session.


## -parameters




### -param Tag [in]

Specifies the GUID identifying the data requested.


### -param Offset [in]

Specifies the offset within the data to read.


### -param Buffer [out, optional]

Receives the data.  If <i>Buffer</i> is <b>NULL</b>, the data is not returned.


### -param BufferSize [in]

Specifies the size in bytes of the buffer <i>Buffer</i>.  This is the maximum number of bytes that will be returned.


### -param TotalSize [out, optional]

Receives the total size in bytes of the data specified by <i>Tag</i>.


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
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
No data identified by <i>Tag</i> could be found.

</td>
</tr>
</table>
 

This method can also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.




## -remarks



Some debugger sessions have arbitrary additional data available.  For example, when a dump file is created, additional dump information files containing extra information may also be created.  This additional data is tagged with a global unique identifier and can only be retrieved via the tag.

LPGUID is a pointer to a 128-bit unique identifier.  It is defined in the Microsoft Windows SDK header file guiddef.h.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugdataspaces4-getnexttagged">GetNextTagged</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces3">IDebugDataSpaces3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugdataspaces4">IDebugDataSpaces4</a>
 

 

