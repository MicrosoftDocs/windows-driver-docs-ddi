---
UID: NS:portcls._PCMETHOD_REQUEST
title: "_PCMETHOD_REQUEST"
author: windows-driver-content
description: The PCMETHOD_REQUEST structure specifies a method request.
old-location: audio\pcmethod_request.htm
old-project: audio
ms.assetid: aa48330b-93f0-4fb2-bb36-4e9050f19be5
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audpc-struct_08efa6de-5d0e-445b-9402-563604dd8d5d.xml, PPCMETHOD_REQUEST structure pointer [Audio Devices], portcls/PPCMETHOD_REQUEST, PCMETHOD_REQUEST structure [Audio Devices], PCMETHOD_REQUEST, _PCMETHOD_REQUEST, *PPCMETHOD_REQUEST, audio.pcmethod_request, portcls/PCMETHOD_REQUEST, PPCMETHOD_REQUEST
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	portcls.h
apiname:
-	PCMETHOD_REQUEST
product: Windows
targetos: Windows
req.typenames: "*PPCMETHOD_REQUEST, PCMETHOD_REQUEST"
---

# _PCMETHOD_REQUEST structure


## -description


The PCMETHOD_REQUEST structure specifies a method request.


## -syntax


````
typedef struct _PCMETHOD_REQUEST {
  PUNKNOWN            MajorTarget;
  PUNKNOWN            MinorTarget;
  ULONG               Node;
  const PCMETHOD_ITEM *MethodItem;
  ULONG               Verb;
} PCMETHOD_REQUEST, *PPCMETHOD_REQUEST;
````


## -struct-fields




### -field MajorTarget

Pointer to the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface of a miniport object that supports the method set and method specified by <b>MethodItem</b>.


### -field MinorTarget

Pointer to an <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface of a stream object associated with <b>MajorTarget</b>. If the request does not specify a minor target, set this member to <b>NULL</b>.


### -field Node

Specifies the node ID of the target node for the request. If the target is not a node, this member is set to ULONG(-1).


### -field MethodItem

Pointer to a <a href="..\portcls\ns-portcls-__unnamed_struct_0c93_4.md">PCMETHOD_ITEM</a> structure that describes a method supported by a filter, pin, or node.


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


This is the structure that the port driver passes to the miniport driver's method-handler routine. The <a href="..\portcls\ns-portcls-__unnamed_struct_0c93_4.md">PCMETHOD_ITEM</a> structure contains a pointer to a method handler that takes a PCMETHOD_REQUEST pointer as its single call parameter.

The WDM audio subsystem does not currently support method requests.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537695">PCFILTER_NODE</a>

<a href="..\portcls\ns-portcls-__unnamed_struct_0c93_4.md">PCMETHOD_ITEM</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PCMETHOD_REQUEST structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

