---
UID: NF:dbgeng.IDebugDataSpaces3.FillVirtual
title: IDebugDataSpaces3::FillVirtual method
author: windows-driver-content
description: The FillVirtual method writes a pattern of bytes to the target's virtual memory. The pattern is written repeatedly until the specified memory range is filled.
old-location: debugger\fillvirtual.htm
old-project: Debugger
ms.assetid: d55ccd38-00c7-491b-aadf-8b42b5e89600
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: FillVirtual, dbgeng/IDebugDataSpaces4::FillVirtual, IDebugDataSpaces_26ed83e1-6084-4826-bf6c-30be250d3e3f.xml, dbgeng/IDebugDataSpaces3::FillVirtual, IDebugDataSpaces4::FillVirtual, IDebugDataSpaces4 interface [Windows Debugging], FillVirtual method, IDebugDataSpaces3 interface [Windows Debugging], FillVirtual method, IDebugDataSpaces2, FillVirtual method [Windows Debugging], IDebugDataSpaces3 interface, debugger.fillvirtual, IDebugDataSpaces2 interface [Windows Debugging], FillVirtual method, IDebugDataSpaces3::FillVirtual, IDebugDataSpaces2::FillVirtual, IDebugDataSpaces3, FillVirtual method [Windows Debugging], dbgeng/IDebugDataSpaces2::FillVirtual, FillVirtual method [Windows Debugging], IDebugDataSpaces4 interface, FillVirtual method [Windows Debugging], IDebugDataSpaces2 interface
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
-	IDebugDataSpaces2.FillVirtual
-	IDebugDataSpaces3.FillVirtual
-	IDebugDataSpaces4.FillVirtual
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugDataSpaces3::FillVirtual method


## -description


The <b>FillVirtual</b> method writes a pattern of bytes to the target's virtual memory.  The pattern is written repeatedly until the specified memory range is filled.


## -syntax


````
HRESULT FillVirtual(
  [in]            ULONG64 Start,
  [in]            ULONG   Size,
  [in]            PVOID   Pattern,
  [in]            ULONG   PatternSize,
  [out, optional] PULONG  Filled
);
````


## -parameters




### -param Start [in]

Specifies the location in the target's virtual address space at which to start writing the pattern.


### -param Size [in]

Specifies how many bytes to write to the target's memory.


### -param Pattern [in]

Specifies the memory location of the pattern.


### -param PatternSize [in]

Specifies the size in bytes of the pattern.


### -param Filled [out, optional]

Receives the number of bytes written.  If it is set to <b>NULL</b>, this information isn't returned.


## -returns



This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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



This method writes the pattern to the target's memory as many times as will fit in <i>Size</i> bytes.

If the final copy of the pattern will not completely fit into the memory range, it will only be partially written.  This includes the case where the size of the pattern is larger than the value of <i>Size</i>, and the extra bytes in the pattern are ignored.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugdataspaces4.md">IDebugDataSpaces4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561468">WriteVirtual</a>



<a href="..\dbgeng\nn-dbgeng-idebugdataspaces2.md">IDebugDataSpaces2</a>



<a href="..\dbgeng\nn-dbgeng-idebugdataspaces3.md">IDebugDataSpaces3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugDataSpaces2::FillVirtual method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

