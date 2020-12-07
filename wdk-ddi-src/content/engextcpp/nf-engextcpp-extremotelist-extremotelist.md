---
UID: NF:engextcpp.ExtRemoteList.ExtRemoteList
title: ExtRemoteList::ExtRemoteList method (engextcpp.h)
description: The ExtRemoteList class provides a wrapper around a singly-linked or doubly-linked list. The class contains methods that can be used to move both forward and backward through the list.
old-location: debugger\extremotelist.htm
tech.root: debugger
ms.date: 01/19/2018
keywords: ["ExtRemoteList::ExtRemoteList method"]
ms.keywords: engextcpp/ExtRemoteList, ExtRemoteList class [Windows Debugging], ExtRemoteList::ExtRemoteList, ExtRemoteList, ExtRemoteList class [Windows Debugging], described, debugger.extremotelist, EngExtCpp_Ref_83df4aa3-cb9c-4921-a588-ef473a57f0e2.xml
f1_keywords:
 - "engextcpp/ExtRemoteList"
 - "ExtRemoteList"
req.header: engextcpp.hpp
req.include-header: Engextcpp.hpp
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
req.lib: engextcpp.hpp
req.dll:
req.irql:
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- engextcpp.hpp
api_name:
- ExtRemoteList
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteList::ExtRemoteList method


## -description


The <b>ExtRemoteList</b> class provides a wrapper around a singly-linked or doubly-linked list.  The class contains methods that can be used to move both forward and backward through the list.

<b>ExtRemoteList</b> supports both NULL-terminated and circular lists.

<b>ExtRemoteList</b> expects that a list is lists implemented in the way that NT-based versions of Windows implements a list.  It also expects that the list uses the SINGLE_LIST_ENTRY or LIST_ENTRY structure.  In particular, <b>ExtRemoteList</b> expects the lists to have the following characteristics:
<ol>
<li>
The list has a <i>head</i>.  The head represents the beginning (and, for circular and doubly-linked lists, the end) of the list and is not a list item.  The type of the head is SINGLE_LIST_ENTRY or LIST_ENTRY.

</li>
<li>
The pointer to the next item in the list points to the pointer to the following item.  In other words, the pointer to the next item points to the SINGLE_LIST_ENTRY or LIST_ENTRY structure embedded in the next item.

</li>
<li>
For doubly-linked lists, the pointer to the previous item in the list points to the pointer to the current item.  In other words, the pointer to the previous item points to the LIST_ENTRY structure embedded in the previous item.

</li>
<li>
For doubly-linked lists, the pointer to the previous item immediately follows the pointer to the next item.  This matches the layout of the LIST_ENTRY structure in memory.

</li>
</ol>For more information about the SINGLE_LIST_ENTRY and LIST_ENTRY structures and their use, see the Windows Driver Kit (WDK) documentation.

The <b>ExtRemoteList</b> class includes the following methods:
<dl>
<dd>

<a href="..\engextcpp\nl-engextcpp-extremotelist.md">ExtRemoteList::ExtRemoteList (ExtRemoteData)</a>


</dd>
<dd>

<a href="..\engextcpp\nl-engextcpp-extremotelist.md">ExtRemoteList::ExtRemoteList (ULONG64)</a>


</dd>
<dd>

<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotelist-starthead">StartHead</a>


</dd>
<dd>

<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotelist-starttail">StartTail</a>


</dd>
<dd>

<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotelist-hasnode">HasNode</a>


</dd>
<dd>

<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotelist-getnodeoffset">GetNodeOffset</a>


</dd>
<dd>

<a href="/windows-hardware/test/wpt/next-ienumprofile">Next</a>


</dd>
<dd>

<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotelist-prev">Prev</a>


</dd>
</dl><pre class="syntax" xml:space="preserve"><code>class ExtRemoteList
{
public:
    ULONG64  m_Head;
    ULONG  m_LinkOffset;
    bool  m_Double;
    ULONG  m_MaxIter;
    ExtRemoteData  m_Node;
    ULONG  m_CurIter;
};</code></pre>
<dl>
<dt><a id="m_Head"></a><a id="m_head"></a><a id="M_HEAD"></a><b>m_Head</b></dt>
<dd>
The location in the target's memory of the head of the list.

</dd>
<dt><a id="m_LinkOffset"></a><a id="m_linkoffset"></a><a id="M_LINKOFFSET"></a><b>m_LinkOffset</b></dt>
<dd>
The offset of the SINGLE_LIST_ENTRY or LIST_ENTRY structures embedded within the list items.

</dd>
<dt><a id="m_Double"></a><a id="m_double"></a><a id="M_DOUBLE"></a><b>m_Double</b></dt>
<dd>
<code>true</code> for a doubly-linked list.  <code>false</code> for a singly-linked list.

</dd>
<dt><a id="m_MaxIter"></a><a id="m_maxiter"></a><a id="M_MAXITER"></a><b>m_MaxIter</b></dt>
<dd>
The maximum number of nodes that can be returned when iterating over the list.  The default value of <b>m_MaxIter</b> is 65536. Limiting the number of nodes that can be returned in an iteration protects against loops.

</dd>
<dt><a id="m_Node"></a><a id="m_node"></a><a id="M_NODE"></a><b>m_Node</b></dt>
<dd>
The pointer to the current item in the list.  <b>m_Node</b> is not set until an iteration is initialized using <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotelist-starthead">StartHead</a> or <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotelist-starttail">StartTail</a>.  <b>m_Node</b> is of type <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>, which describes the pointer.

</dd>
<dt><a id="m_CurIter"></a><a id="m_curiter"></a><a id="M_CURITER"></a><b>m_CurIter</b></dt>
<dd>
The number of steps taken in the current list iteration.  For doubly-linked lists, <b>m_CurIter</b> is increased for both forward and backward steps.

</dd>
</dl>

## -parameters


## -see-also

<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotelist-starttail">StartTail</a>

<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotelist-starthead">StartHead</a>

<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>

 

 
