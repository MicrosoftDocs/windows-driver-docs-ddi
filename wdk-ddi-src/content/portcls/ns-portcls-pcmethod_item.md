---
UID: NS:portcls.__unnamed_struct_1
title: PCMETHOD_ITEM (portcls.h)
description: The PCMETHOD_ITEM structure describes a method supported by a filter, pin, or node.
old-location: audio\pcmethod_item.htm
tech.root: audio
ms.assetid: 588d2f0e-0f87-46c7-b2fa-f14f29f6a9f0
ms.date: 05/08/2018
ms.keywords: "*PPCMETHOD_ITEM, PCMETHOD_ITEM, PCMETHOD_ITEM structure [Audio Devices], PPCMETHOD_ITEM, PPCMETHOD_ITEM structure pointer [Audio Devices], audio.pcmethod_item, audpc-struct_58edb038-1bae-4846-8ce9-d0c0c052730c.xml, portcls/PCMETHOD_ITEM, portcls/PPCMETHOD_ITEM"
ms.topic: struct
req.header: portcls.h
req.include-header: Portcls.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	portcls.h
api_name:
-	PCMETHOD_ITEM
product:
- Windows
targetos: Windows
req.typenames: PCMETHOD_ITEM, *PPCMETHOD_ITEM
---

# PCMETHOD_ITEM structure


## -description


The PCMETHOD_ITEM structure describes a method supported by a filter, pin, or node.


## -struct-fields




### -field Set

Specifies the method set. This member is a pointer to a GUID that uniquely identifies the method set.


### -field Id

Specifies the method ID. This member identifies a method item in the method set. If the method set contains <i>n</i> items, valid method IDs are integers in the range 0 to <i>n</i>-1.


### -field Flags

Specifies the type of parameter passing and memory access that a method uses. This member can be set to the bitwise OR of one or more of the flag bits in the following table.

<table>
<tr>
<th>Flag bit</th>
<th>Meaning</th>
</tr>
<tr>
<td>
PCMETHOD_ITEM_FLAG_MODIFY

</td>
<td>
The method reads from and writes to the parameter buffer.

</td>
</tr>
<tr>
<td>
PCMETHOD_ITEM_FLAG_NONE

</td>
<td>
The method does not use the parameter buffer.

</td>
</tr>
<tr>
<td>
PCMETHOD_ITEM_FLAG_READ

</td>
<td>
The method reads from the parameter buffer.

</td>
</tr>
<tr>
<td>
PCMETHOD_ITEM_FLAG_SOURCE

</td>
<td>
The method probes and locks memory pages before attempting memory access.

</td>
</tr>
<tr>
<td>
PCMETHOD_ITEM_FLAG_WRITE

</td>
<td>
The method writes to the parameter buffer.

</td>
</tr>
</table>
 


### -field Handler

Pointer to the method-handler routine. This member is a function pointer of type PCPFNMETHOD_HANDLER, which is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>  typedef NTSTATUS (*PCPFNMETHOD_HANDLER)
  (
      IN PPCMETHOD_REQUEST  MethodRequest
  );</pre>
</td>
</tr>
</table></span></div>
When calling the <b>Handler</b> routine, the caller passes in a single call parameter, which is a pointer to a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff537705">PCMETHOD_REQUEST</a>.


## -remarks



The WDM audio subsystem does not currently support methods on either filter instances or pin instances. This restriction also precludes support for methods on nodes.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff537685">PCAUTOMATION_TABLE</a> structure contains a pointer to an array of PCMETHOD_ITEM structures.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537705">PCMETHOD_REQUEST</a>
 

 

