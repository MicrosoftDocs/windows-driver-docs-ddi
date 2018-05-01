---
UID: NS:portcls._PCMETHOD_REQUEST
title: "_PCMETHOD_REQUEST"
author: windows-driver-content
description: The PCMETHOD_REQUEST structure specifies a method request.
old-location: audio\pcmethod_request.htm
old-project: audio
ms.assetid: aa48330b-93f0-4fb2-bb36-4e9050f19be5
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*PPCMETHOD_REQUEST, PCMETHOD_REQUEST, PCMETHOD_REQUEST structure [Audio Devices], PPCMETHOD_REQUEST, PPCMETHOD_REQUEST structure pointer [Audio Devices], _PCMETHOD_REQUEST, audio.pcmethod_request, audpc-struct_08efa6de-5d0e-445b-9402-563604dd8d5d.xml, portcls/PCMETHOD_REQUEST, portcls/PPCMETHOD_REQUEST"
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
-	PCMETHOD_REQUEST
product: Windows
targetos: Windows
req.typenames: PCMETHOD_REQUEST, *PPCMETHOD_REQUEST
---

# _PCMETHOD_REQUEST structure


## -description


The PCMETHOD_REQUEST structure specifies a method request.


## -struct-fields




### -field MajorTarget

Pointer to the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface of a miniport object that supports the method set and method specified by <b>MethodItem</b>.


### -field MinorTarget

Pointer to an <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface of a stream object associated with <b>MajorTarget</b>. If the request does not specify a minor target, set this member to <b>NULL</b>.


### -field Node

Specifies the node ID of the target node for the request. If the target is not a node, this member is set to ULONG(-1).


### -field MethodItem

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537704">PCMETHOD_ITEM</a> structure that describes a method supported by a filter, pin, or node.


### -field Verb

Specifies the type of method request. This member can be set to the bitwise OR of one or more of the flag bits in the following table.

<table>
<tr>
<th>Flag bit</th>
<th>Meaning</th>
</tr>
<tr>
<td>
PCMETHOD_ITEM_FLAG_BASICSUPPORT

</td>
<td>
Returns basic support information about the method specified by <b>MethodItem</b>-&gt;<b>Id</b>.

</td>
</tr>
<tr>
<td>
PCMETHOD_ITEM_FLAG_SEND

</td>
<td>
Executes the method specified by <b>MethodItem</b>-&gt;<b>Id</b>. The client should conform to the basic-support information for the method.

</td>
</tr>
<tr>
<td>
PCMETHOD_ITEM_FLAG_SETSUPPORT

</td>
<td>
Returns information about support for the method set specified by <b>MethodItem</b>-&gt;<b>Set</b>.

</td>
</tr>
</table>
 


## -remarks



This is the structure that the port driver passes to the miniport driver's method-handler routine. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff537704">PCMETHOD_ITEM</a> structure contains a pointer to a method handler that takes a PCMETHOD_REQUEST pointer as its single call parameter.

The WDM audio subsystem does not currently support method requests.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537695">PCFILTER_NODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537704">PCMETHOD_ITEM</a>
 

 

