---
UID: NF:fltkernel.FltCheckAndGrowNameControl
title: FltCheckAndGrowNameControl function
author: windows-driver-content
description: The FltCheckAndGrowNameControl routine checks whether the buffer in a FLT_NAME_CONTROL structure is large enough to hold the specified number of bytes. If not, FltCheckAndGrowNameControl replaces it with a larger system-allocated buffer.
old-location: ifsk\fltcheckandgrownamecontrol.htm
old-project: ifsk
ms.assetid: 0a49e69e-6b6b-4f86-bd41-d1ad73e63a17
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: fltkernel/FltCheckAndGrowNameControl, FltCheckAndGrowNameControl routine [Installable File System Drivers], FltApiRef_a_to_d_5ab0b3b3-adeb-4752-9cb5-1d7521b84607.xml, ifsk.fltcheckandgrownamecontrol, FltCheckAndGrowNameControl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: FltMgr.lib
req.dll: 
req.irql: <= APC_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	FltMgr.lib
-	FltMgr.dll
apiname: 
-	FltCheckAndGrowNameControl
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltCheckAndGrowNameControl function


## -description


The <b>FltCheckAndGrowNameControl</b> routine checks whether the buffer in a <a href="..\fltkernel\ns-fltkernel-_flt_name_control.md">FLT_NAME_CONTROL</a> structure is large enough to hold the specified number of bytes. If not, <b>FltCheckAndGrowNameControl</b> replaces it with a larger system-allocated buffer. 


## -syntax


````
NTSTATUS FltCheckAndGrowNameControl(
  _Inout_ PFLT_NAME_CONTROL NameCtrl,
  _In_    USHORT            NewSize
);
````


## -parameters




### -param NameCtrl [in, out]

Pointer to a <a href="..\fltkernel\ns-fltkernel-_flt_name_control.md">FLT_NAME_CONTROL</a> structure containing file name information. 


### -param NewSize [in]

Required size, in bytes, of the new name control buffer. 


## -returns


<b>FltCheckAndGrowNameControl</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There is insufficient memory in the free pool to satisfy the request. 

</td>
</tr>
</table> 



## -remarks


Minifilter drivers must not attempt to free or replace the buffer in the <b>Name</b> member of a <a href="..\fltkernel\ns-fltkernel-_flt_name_control.md">FLT_NAME_CONTROL</a> structure directly. Instead, minifilter drivers should call <b>FltCheckAndGrowNameControl</b> to obtain a larger name buffer. 

If the size, in bytes, of the buffer in the <i>NameCtrl</i> structure is less than the value of the <i>NewSize</i> parameter, <b>FltCheckAndGrowNameControl</b> replaces it with a larger system-allocated buffer. <b>FltCheckAndGrowNameControl</b> copies the contents of the old buffer into the new one and frees the old buffer. 

If the size, in bytes, of the buffer in the <i>NameCtrl</i> structure is greater than or equal to the value of the <i>NewSize</i> parameter, <b>FltCheckAndGrowNameControl</b> returns STATUS_SUCCESS and does not replace the buffer. 



## -see-also

<a href="..\fltkernel\nf-fltkernel-fltgetfilenameinformation.md">FltGetFileNameInformation</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543030">FltGetFileNameFormat</a>

<a href="..\fltkernel\nf-fltkernel-fltgetfilenameinformationunsafe.md">FltGetFileNameInformationUnsafe</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543040">FltGetFileNameQueryMethod</a>

<a href="..\fltkernel\ns-fltkernel-_flt_name_control.md">FLT_NAME_CONTROL</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltCheckAndGrowNameControl routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

