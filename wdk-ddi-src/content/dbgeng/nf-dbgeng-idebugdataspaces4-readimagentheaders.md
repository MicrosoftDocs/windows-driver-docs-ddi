---
UID: NF:dbgeng.IDebugDataSpaces4.ReadImageNtHeaders
title: IDebugDataSpaces4::ReadImageNtHeaders method
author: windows-driver-content
description: The ReadImageNtHeaders method returns the NT headers for the specified image loaded in the target.
old-location: debugger\readimagentheaders.htm
old-project: debugger
ms.assetid: 2735aabf-b8b0-4eb1-89a2-4733d0b346ed
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: dbgeng/IDebugDataSpaces4::ReadImageNtHeaders, IDebugDataSpaces4::ReadImageNtHeaders, debugger.readimagentheaders, ReadImageNtHeaders method [Windows Debugging], IDebugDataSpaces4, ReadImageNtHeaders method [Windows Debugging], IDebugDataSpaces3 interface, IDebugDataSpaces3 interface [Windows Debugging], ReadImageNtHeaders method, ReadImageNtHeaders method [Windows Debugging], IDebugDataSpaces4 interface, IDebugDataSpaces_333f4fab-a56c-43e2-92d7-59775b794e1f.xml, dbgeng/IDebugDataSpaces3::ReadImageNtHeaders, IDebugDataSpaces4 interface [Windows Debugging], ReadImageNtHeaders method, ReadImageNtHeaders, IDebugDataSpaces3, IDebugDataSpaces3::ReadImageNtHeaders
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
-	IDebugDataSpaces3.ReadImageNtHeaders
-	IDebugDataSpaces4.ReadImageNtHeaders
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugDataSpaces4::ReadImageNtHeaders method


## -description


The <b>ReadImageNtHeaders</b> method returns the NT headers for the specified image loaded in the target.


## -syntax


````
HRESULT ReadImageNtHeaders(
  [in]  ULONG64             ImageBase,
  [out] PIMAGE_NT_HEADERS64 Headers
);
````


## -parameters




### -param ImageBase [in]

Specifies the location in the target's virtual address space of the image whose NT headers are being requested.


### -param Headers [out]

Receives the NT headers for the specified image.


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
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
No NT headers were found for the specified image.

</td>
</tr>
</table>
 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



If the image's NT headers are 32-bit, they are automatically converted to 64-bit for consistency.  To determine if the headers were originally 32-bit, look at the value of <b>Headers.OptionalHeader.Magic</b>.  If the value is IMAGE_NT_OPTIONAL_HDR32_MAGIC, the NT headers were originally 32-bit; otherwise the value is IMAGE_NT_OPTIONAL_HDR64_MAGIC, indicating the NT headers were originally 64-bit.

This method will not read ROM headers.

IMAGE_NT_HEADERS64, IMAGE_NT_OPTIONAL_HDR32_MAGIC, and IMAGE_NT_OPTIONAL_HDR64_MAGIC appear in the Microsoft Windows SDK header file winnt.h.  IMAGE_NT_HEADERS64 is the 64-bit equivalent of IMAGE_NT_HEADERS, which is described in the Windows SDK documentation.



