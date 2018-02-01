---
UID: NS:wdbgexts._DEBUG_TYPED_DATA
title: "_DEBUG_TYPED_DATA"
author: windows-driver-content
description: The DEBUG_TYPED_DATA structure describes typed data in the memory of the target.
old-location: debugger\debug_typed_data.htm
old-project: debugger
ms.assetid: 3173e69e-a6e5-4459-a57e-94cf7b10ef32
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: DEBUG_TYPED_DATA, *PDEBUG_TYPED_DATA, PDEBUG_TYPED_DATA structure pointer [Windows Debugging], PDEBUG_TYPED_DATA, Structures_6e8e758c-2c5d-4590-8908-3e1734ea2c7d.xml, _DEBUG_TYPED_DATA, wdbgexts/DEBUG_TYPED_DATA, debugger.debug_typed_data, wdbgexts/PDEBUG_TYPED_DATA, DEBUG_TYPED_DATA structure [Windows Debugging]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdbgexts.h
req.include-header: WdbgExts.h
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	WdbgExts.h
apiname:
-	DEBUG_TYPED_DATA
product: Windows
targetos: Windows
req.typenames: DEBUG_TYPED_DATA, *PDEBUG_TYPED_DATA
req.product: Windows 10 or later.
---

# _DEBUG_TYPED_DATA structure


## -description


The DEBUG_TYPED_DATA structure describes typed data in the memory of the target. 


## -syntax


````
typedef struct _DEBUG_TYPED_DATA {
  ULONG64 ModBase;
  ULONG64 Offset;
  ULONG64 EngineHandle;
  ULONG64 Data;
  ULONG   Size;
  ULONG   Flags;
  ULONG   TypeId;
  ULONG   BaseTypeId;
  ULONG   Tag;
  ULONG   Register;
  ULONG64 Internal[9];
}  DEBUG_TYPED_DATA, *PDEBUG_TYPED_DATA;
````


## -struct-fields




### -field ModBase

The base address of the module, in the target's virtual address space, that contains the typed data.


### -field Offset

The location of the typed data in the target's memory. <b>Offset</b> is a virtual memory address unless there are flags present in <b>Flags</b> that specify that <b>Offset</b> is a physical memory address.


### -field EngineHandle

Set to zero.


### -field Data

The data cast to a ULONG64. If <b>Flags</b> does not contain the DEBUG_TYPED_DATA_IS_IN_MEMORY flag, the data is not available and <b>Data</b> is set to zero.


### -field Size

The size, in bytes, of the data.


### -field Flags

The flags describing the target's memory in which the data resides. The following bit flags can be set.
<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_TYPED_DATA_IS_IN_MEMORY

</td>
<td>
The data is in the target's memory and is available.

</td>
</tr>
<tr>
<td>
DEBUG_TYPED_DATA_PHYSICAL_DEFAULT

</td>
<td>
<b>Offset</b> is a physical memory address, and the physical memory at <b>Offset</b> uses the default memory caching.

</td>
</tr>
<tr>
<td>
DEBUG_TYPED_DATA_PHYSICAL_CACHED

</td>
<td>
<b>Offset</b> is a physical memory address, and the physical memory at <b>Offset</b> is cached.

</td>
</tr>
<tr>
<td>
DEBUG_TYPED_DATA_PHYSICAL_UNCACHED

</td>
<td>
<b>Offset</b> is a physical memory address, and the physical memory at <b>Offset</b> is uncached.

</td>
</tr>
<tr>
<td>
DEBUG_TYPED_DATA_PHYSICAL_WRITE_COMBINED

</td>
<td>
<b>Offset</b> is a physical memory address, and the physical memory at <b>Offset</b> is write-combined.

</td>
</tr>
</table> 


### -field TypeId

The type ID for the data's type.


### -field BaseTypeId

For generated types, the type ID of the type on which the data's type is based. For example, if the typed data represents a pointer (or an array), <b>BaseTypeId</b> is the type of the object pointed to (or held in the array).

For other types, <b>BaseTypeId</b> is the same as <b>TypeId</b>.


### -field Tag

The symbol tag of the typed data. This is a value from the <b>SymTagEnum</b> enumeration. For descriptions of the values, see the DbgHelp API documentation.


### -field Register

The index of the processor's register containing the data, or zero if the data is not contained in a register.  (Note that the zero value can represent either that the data is not in a register or that it is in the register whose index is zero.) 


### -field Internal

Internal <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> data.


## -remarks


Instances of this structure should be manipulated using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541547">DEBUG_REQUEST_EXT_TYPED_DATA_ANSI</a>
<a href="https://msdn.microsoft.com/efb3c93c-5405-418b-a063-afa8e5e9e59a"> Request</a> operation. In particular, instances should be created and released using this method, and members of this structure should not be changed directly.

There is one exception to the preceding rule: the <b>EXT_TDOP_SET_FROM_TYPE_ID_AND_U64</b> and <b>EXT_TDOP_SET_PTR_FROM_TYPE_ID_AND_U64</b> suboperations take a DEBUG_TYPED_DATA instance that is not manipulated using the <b>Request</b> method.  These suboperations take a manually created instance with some members manually filled in.
<div class="alert"><b>Note</b>  Include WdbgExts.h before including DbgEng.h. Additionally, <b>SymTagEnum</b> is defined in DbgHelp.h (include DbgHelp.h).</div><div> </div>


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554564">Request</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541547">DEBUG_REQUEST_EXT_TYPED_DATA_ANSI</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20DEBUG_TYPED_DATA structure%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

