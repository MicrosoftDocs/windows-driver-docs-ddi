---
UID: NF:dbgeng.IDebugDataSpaces4.ReadTagged
title: IDebugDataSpaces4::ReadTagged method
author: windows-driver-content
description: The ReadTagged method reads the tagged data that might be associated with a debugger session.
old-location: debugger\readtagged.htm
old-project: debugger
ms.assetid: d7ca67d2-7156-44f7-ab16-178e6307e412
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugDataSpaces4, IDebugDataSpaces4::ReadTagged, ReadTagged
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
req.alt-api: IDebugDataSpaces3.ReadTagged,IDebugDataSpaces4.ReadTagged
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

# IDebugDataSpaces4::ReadTagged method



## -description
The <b>ReadTagged</b> method reads the tagged data that might be associated with a debugger session.



## -syntax

````
HRESULT ReadTagged(
  [in]            LPGUID Tag,
  [in]            ULONG  Offset,
  [out, optional] PVOID  Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG TotalSize
);
````


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
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>No data identified by <i>Tag</i> could be found.

 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.


## -remarks
Some debugger sessions have arbitrary additional data available.  For example, when a dump file is created, additional dump information files containing extra information may also be created.  This additional data is tagged with a global unique identifier and can only be retrieved via the tag.

LPGUID is a pointer to a 128-bit unique identifier.  It is defined in the Microsoft Windows SDK header file guiddef.h.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces3.md">IDebugDataSpaces3</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces4.md">IDebugDataSpaces4</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547874">GetNextTagged</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugDataSpaces3::ReadTagged method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

