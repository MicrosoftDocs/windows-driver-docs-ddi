---
UID: NS:winddiui._DOCEVENT_FILTER
title: "_DOCEVENT_FILTER"
author: windows-driver-content
description: The DOCEVENT_FILTER structure contains a list of document events to which the printer driver will respond. See DrvDocumentEvent for a complete list of the document events.
old-location: print\docevent_filter.htm
old-project: print
ms.assetid: f486efdb-79fd-4c57-bff6-75a0dbd68cc0
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: winddiui/PDOCEVENT_FILTER, *PDOCEVENT_FILTER, DOCEVENT_FILTER, print.docevent_filter, PDOCEVENT_FILTER structure pointer [Print Devices], DOCEVENT_FILTER structure [Print Devices], print_interface-graphics_ddc1c545-869f-440d-a364-7cd90ca189e0.xml, _DOCEVENT_FILTER, winddiui/DOCEVENT_FILTER, PDOCEVENT_FILTER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winddiui.h
req.include-header: Winddiui.h
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
-	winddiui.h
apiname:
-	DOCEVENT_FILTER
product: Windows
targetos: Windows
req.typenames: "*PDOCEVENT_FILTER, DOCEVENT_FILTER"
req.product: Windows 10 or later.
---

# _DOCEVENT_FILTER structure


## -description


The DOCEVENT_FILTER structure contains a list of document events to which the printer driver will respond. See <a href="..\winddiui\nf-winddiui-drvdocumentevent.md">DrvDocumentEvent</a> for a complete list of the document events.


## -syntax


````
typedef struct _DOCEVENT_FILTER {
  UINT  cbSize;
  UINT  cElementsAllocated;
  UINT  cElementsNeeded;
  UINT  cElementsReturned;
  DWORD aDocEventCall[ANYSIZE_ARRAY];
} DOCEVENT_FILTER, *PDOCEVENT_FILTER;
````


## -struct-fields




### -field cbSize

Spooler-supplied size, in bytes, of this structure. The spooler initializes this member to <b>sizeof</b>(DOCEVENT_FILTER).


### -field cElementsAllocated

Spooler-supplied number of elements in the <b>aDocEventCall</b> array member. The spooler initializes this member to DOCUMENTEVENT_LAST - 1. (The DOCUMENTEVENT_LAST constant is defined in header file Winddiui.h.)


### -field cElementsNeeded

Driver-supplied total number of elements needed in the <b>aDocEventCall</b> array member. The spooler initializes this member to 0XFFFFFFFF. For more information, see the following Remarks section.


### -field cElementsReturned

Driver-supplied number of DOCUMENTEVENT_<i>XXX </i>events that it placed in the <b>aDocEventCall</b> array member. The spooler initializes this member to 0XFFFFFFFF. For more information, see the following Remarks section.


### -field aDocEventCall

Driver-filled array of DWORDs listing all of the DOCUMENTEVENT_<i>XXX</i> events to which the printer driver will respond. The spooler initializes this member to 0.


## -remarks



The DOCEVENT_FILTER structure is defined for Windows XP and later.

The printer driver lists the events to which it will respond in the DOCEVENT_FILTER structure. Because this limits the number of calls to the driver the spooler needs to make, printer performance is enhanced. When the spooler makes a call to the <a href="..\winddiui\nf-winddiui-drvdocumentevent.md">DrvDocumentEvent</a> DDI with its <i>iEsc</i> parameter set to DOCUMENTEVENT_QUERYFILTER, the spooler allocates a buffer that contains a DOCEVENT_FILTER structure, including its <b>aDocEventCall</b> array. The amount of memory allocated for the buffer is: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>sizeof(DOCEVENT_FILTER) + sizeof(DWORD) * (DOCUMENTEVENT_LAST - 2)
 </pre>
</td>
</tr>
</table></span></div>
After allocating a buffer that contains a DOCEVENT_FILTER structure, the spooler initializes the structure members to the following values: 

<table>
<tr>
<th>Member</th>
<th>Initialized to:</th>
</tr>
<tr>
<td>
<b>cbSize</b>

</td>
<td>
0

</td>
</tr>
<tr>
<td>
<b>cElementsAllocated</b>

</td>
<td>
DOCUMENTEVENT_LAST - 1

The DOCUMENTEVENT_LAST constant is defined in winddiui.h.

</td>
</tr>
<tr>
<td>
<b>cElementsNeeded</b>

</td>
<td>
0XFFFFFFFF

</td>
</tr>
<tr>
<td>
<b>cElementsReturned</b>

</td>
<td>
0XFFFFFFFF

</td>
</tr>
<tr>
<td>
<b>aDocEventCall</b>

</td>
<td>
0

</td>
</tr>
</table>
 

After the spooler has initialized the structure members to the values shown in the preceding table, it then calls <a href="..\winddiui\nf-winddiui-drvdocumentevent.md">DrvDocumentEvent</a>. When this function returns, the spooler inspects the <b>cElementsNeeded</b> and <b>cElementsReturned</b> members to see if either has been changed. If the driver has written to one of these members, but not the other, the spooler interprets the unwritten-to member as having the value 0.

If the driver supports DOCUMENTEVENT_QUERYFILTER:

<ul>
<li>If the <b>aDocEventCall</b> array is large enough to contain all of the DOCUMENTEVENT_<i>XXX</i> events the printer driver intends to place in it, the printer driver:<ul>
<li>Fills the array with those events.</li>
<li>Sets the <b>cElementsReturned</b> member to that number of events (which should be less than or equal to <b>cElementsAllocated</b>).</li>
<li>Leaves <b>cElementsNeeded</b> unchanged.</li>
<li>Returns DOCUMENTEVENT_SUCCESS.</li>
</ul>
</li>
</ul>
In this case, the spooler uses the first <b>cElementsReturned</b> values in the <b>aDocEventCall</b> array.

<div class="alert"><b>Note</b>    The DOCUMENTEVENT_CREATEDCPRE event is treated in a special way. When the spooler calls <a href="..\winddiui\nf-winddiui-drvdocumentevent.md">DrvDocumentEvent</a> with the <i>iEsc</i> parameter set to DOCUMENTEVENT_CREATEDCPRE, the spooler uses the return value to determine whether future calls to this function are necessary. Unlike other DOCUMENTEVENT_<i>XXX</i> events, the printer driver always receives calls to <b>DrvDocumentEvent</b> with DOCUMENTEVENT_CREATEDCPRE, whether this event is filtered out or not.</div>
<div> </div>
<ul>
<li>
If the <b>aDocEventCall</b> array is not large enough to contain all of the DOCUMENTEVENT_<i>XXX</i> events the printer driver intends to place in it, the printer driver should:<ul>
<li>Set <b>cElementsNeeded</b> to the number of events to which it intends to respond (which should be greater than <b>cElementsAllocated</b>).</li>
<li>Leave <b>cElementsReturned</b> unchanged.</li>
<li>Return DOCUMENTEVENT_SUCCESS.</li>
</ul>


In this case, the spooler then allocates a new buffer that is sufficiently large, and then makes another call to <a href="..\winddiui\nf-winddiui-drvdocumentevent.md">DrvDocumentEvent</a> with DOCUMENTEVENT_QUERYFILTER.

</li>
</ul>
If the driver does not support the DOCUMENTEVENT_QUERYFILTER event, it should return DOCUMENTEVENT_UNSUPPORTED. If the driver does support DOCUMENTEVENT_QUERYFILTER, but encounters internal errors when it handles this event, it should return DOCUMENTEVENT_FAILURE. In either case, the spooler is not able to retrieve the event filter from the driver, so it continues in its behavior of calling <a href="..\winddiui\nf-winddiui-drvdocumentevent.md">DrvDocumentEvent</a> for all events.




## -see-also

<a href="..\winddiui\nf-winddiui-drvdocumentevent.md">DrvDocumentEvent</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20DOCEVENT_FILTER structure%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

