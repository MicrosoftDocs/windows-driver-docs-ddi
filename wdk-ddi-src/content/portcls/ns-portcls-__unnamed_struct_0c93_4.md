---
UID: NS:portcls.__unnamed_struct_0c93_4
title: *PPCMETHOD_ITEM
author: windows-driver-content
description: The PCMETHOD_ITEM structure describes a method supported by a filter, pin, or node.
old-location: audio\pcmethod_item.htm
old-project: audio
ms.assetid: 588d2f0e-0f87-46c7-b2fa-f14f29f6a9f0
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: *PPCMETHOD_ITEM, *PPCMETHOD_ITEM, PCMETHOD_ITEM
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PCMETHOD_ITEM
req.alt-loc: portcls.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PPCMETHOD_ITEM, PCMETHOD_ITEM
---

# *PPCMETHOD_ITEM structure



## -description
The PCMETHOD_ITEM structure describes a method supported by a filter, pin, or node.



## -syntax

````
typedef struct {
  const GUID          *Set;
  ULONG               Id;
  ULONG               Flags;
  PCPFNMETHOD_HANDLER Handler;
} PCMETHOD_ITEM, *PPCMETHOD_ITEM;
````


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
When calling the <b>Handler</b> routine, the caller passes in a single call parameter, which is a pointer to a structure of type <a href="..\portcls\ns-portcls-_pcmethod_request.md">PCMETHOD_REQUEST</a>.


## -remarks
The WDM audio subsystem does not currently support methods on either filter instances or pin instances. This restriction also precludes support for methods on nodes.

The <a href="..\portcls\ns-portcls-__unnamed_struct_0c93_6.md">PCAUTOMATION_TABLE</a> structure contains a pointer to an array of PCMETHOD_ITEM structures.


## -see-also
<dl>
<dt>
<a href="..\portcls\ns-portcls-_pcmethod_request.md">PCMETHOD_REQUEST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PCMETHOD_ITEM structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

