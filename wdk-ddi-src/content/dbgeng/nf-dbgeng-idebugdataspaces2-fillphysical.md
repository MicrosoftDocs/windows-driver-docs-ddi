---
UID: NF:dbgeng.IDebugDataSpaces2.FillPhysical
title: IDebugDataSpaces2::FillPhysical method
author: windows-driver-content
description: The FillPhysical method writes a pattern of bytes to the target's physical memory. The pattern is written repeatedly until the specified memory range is filled.
old-location: debugger\fillphysical.htm
old-project: debugger
ms.assetid: 9fd2cc6d-c891-4566-896b-80d56d143e8d
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: FillPhysical method [Windows Debugging], FillPhysical method [Windows Debugging], IDebugDataSpaces2 interface, FillPhysical method [Windows Debugging], IDebugDataSpaces3 interface, FillPhysical method [Windows Debugging], IDebugDataSpaces4 interface, FillPhysical,IDebugDataSpaces2.FillPhysical, IDebugDataSpaces2, IDebugDataSpaces2 interface [Windows Debugging], FillPhysical method, IDebugDataSpaces2::FillPhysical, IDebugDataSpaces3 interface [Windows Debugging], FillPhysical method, IDebugDataSpaces3::FillPhysical, IDebugDataSpaces4 interface [Windows Debugging], FillPhysical method, IDebugDataSpaces4::FillPhysical, IDebugDataSpaces_a188638a-cb30-4e13-8fd0-07114f03df52.xml, dbgeng/IDebugDataSpaces2::FillPhysical, dbgeng/IDebugDataSpaces3::FillPhysical, dbgeng/IDebugDataSpaces4::FillPhysical, debugger.fillphysical
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
req.lib: 
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
-	IDebugDataSpaces2.FillPhysical
-	IDebugDataSpaces3.FillPhysical
-	IDebugDataSpaces4.FillPhysical
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugDataSpaces2::FillPhysical method


## -description


The <b>FillPhysical</b> method writes a pattern of bytes to the target's physical memory.  The pattern is written repeatedly until the specified memory range is filled.


## -parameters




### -param Start [in]

Specifies the location in the target's physical memory at which to start writing the pattern.


### -param Size [in]

Specifies how many bytes to write to the target's memory.


### -param Pattern [in]

Specifies the pattern to write.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550531">IDebugDataSpaces2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550537">IDebugDataSpaces3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550546">IDebugDataSpaces4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561432">WritePhysical</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugDataSpaces2::FillPhysical method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

