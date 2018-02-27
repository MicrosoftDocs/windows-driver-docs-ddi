---
UID: NF:dbgeng.IDebugControl2.GetSpecificFilterArgument
title: IDebugControl2::GetSpecificFilterArgument method
author: windows-driver-content
description: The GetSpecificFilterArgument method returns the value of filter argument for thespecific filters that have an argument.
old-location: debugger\getspecificfilterargument.htm
old-project: debugger
ms.assetid: a6e32ca9-ebae-482c-808c-6302ccd48db0
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetSpecificFilterArgument method [Windows Debugging], GetSpecificFilterArgument method [Windows Debugging], IDebugControl interface, GetSpecificFilterArgument method [Windows Debugging], IDebugControl2 interface, GetSpecificFilterArgument method [Windows Debugging], IDebugControl3 interface, GetSpecificFilterArgument,IDebugControl2.GetSpecificFilterArgument, IDebugControl interface [Windows Debugging], GetSpecificFilterArgument method, IDebugControl2, IDebugControl2 interface [Windows Debugging], GetSpecificFilterArgument method, IDebugControl2::GetSpecificFilterArgument, IDebugControl3 interface [Windows Debugging], GetSpecificFilterArgument method, IDebugControl3::GetSpecificFilterArgument, IDebugControl::GetSpecificFilterArgument, IDebugControl_ab3a5161-b3e1-47fe-bc97-1f75af363cff.xml, dbgeng/IDebugControl2::GetSpecificFilterArgument, dbgeng/IDebugControl3::GetSpecificFilterArgument, dbgeng/IDebugControl::GetSpecificFilterArgument, debugger.getspecificfilterargument
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugControl.GetSpecificFilterArgument
-	IDebugControl2.GetSpecificFilterArgument
-	IDebugControl3.GetSpecificFilterArgument
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl2::GetSpecificFilterArgument method


## -description


The <b>GetSpecificFilterArgument</b>  method returns the value of filter argument for thespecific filters that have an argument.


## -syntax


````
HRESULT GetSpecificFilterArgument(
  [in]            ULONG  Index,
  [out, optional] PSTR   Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG ArgumentSize
);
````


## -parameters




### -param Index [in]

Specifies the index of the specific filter whose argument will be returned.  <i>Index</i> must be the index of a specific filter that has an argument.


### -param Buffer [out, optional]

Receives the argument for the specific filter.  The interpretation of the argument depends on the specific filter.


### -param BufferSize [in]

Specifies the size, in characters, of the buffer that <i>Buffer</i> specifies.


### -param ArgumentSize [out, optional]

Receives the size, in characters, of the argument for the specific filter.


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
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
<i>Index</i> does not refer to a specific filter that has an argument.

</td>
</tr>
</table>
 




## -remarks



For a list of specific filters that have argument and the interpretation of those arguments, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">Event Filters</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556791">SetSpecificFilterArgument</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548398">GetSpecificFilterParameters</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="https://msdn.microsoft.com/fdb5059f-e7d9-4e14-aa3d-030e72c30732">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetSpecificFilterArgument method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

