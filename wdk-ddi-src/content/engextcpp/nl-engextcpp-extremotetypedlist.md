---
UID: NL:engextcpp.ExtRemoteTypedList
title: ExtRemoteTypedList
author: windows-driver-content
description: The ExtRemoteTypedList class extends the ExtRemoteList class. The ExtRemoteTypedList class adds type information allowing each item in the list to be represented by an instance of the ExtRemoteTyped class.
old-location: debugger\extremotetypedlist.htm
old-project: debugger
ms.assetid: a7b87f06-491a-4b41-a355-0f2806c0dd8a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: EngExtCpp_Ref_5e1242e6-5704-4b87-85e1-b02a41fc4243.xml, ExtRemoteTypedList, ExtRemoteTypedList class [Windows Debugging], ExtRemoteTypedList class [Windows Debugging], described, debugger.extremotetypedlist, engextcpp/ExtRemoteTypedList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: class
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	engextcpp.hpp
api_name:
-	ExtRemoteTypedList
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteTypedList class


## -description


The <b>ExtRemoteTypedList</b> class extends the <a href="..\engextcpp\nl-engextcpp-extremotelist.md">ExtRemoteList</a> class.  The <b>ExtRemoteTypedList</b> class adds type information allowing each item in the list to be represented by an instance of the <a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a> class.

The <b>ExtRemoteTypedList</b> class includes the following constructors and methods:
<dl>
<dd>

<a href="..\engextcpp\nl-engextcpp-extremotetypedlist.md">ExtRemoteTypedList::ExtRemoteTypedList(ExtRemoteData)</a>


</dd>
<dd>

<a href="..\engextcpp\nl-engextcpp-extremotetypedlist.md">ExtRemoteTypedList::ExtRemoteTypedList(ULONG64)</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/f6e2d8e3-294d-45d8-8fc6-33af3a746244">SetTypeAndLink</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/3bf50952-7ac9-4c6b-9318-dd64748de9d2">GetTypedNodePtr</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/f74090c9-4e15-4d6c-bb62-b8d5c56d5a1c">GetTypedNode</a>


</dd>
</dl><pre class="syntax" xml:space="preserve"><code>class ExtRemoteTypedList : public ExtRemoteList
{
public:
    PCSTR  m_Type;
    ULONG64  m_TypeModBase;
    ULONG  m_TypeId;
};</code></pre>
<dl>
<dt><a id="m_Type"></a><a id="m_type"></a><a id="M_TYPE"></a><b>m_Type</b></dt>
<dd>
The type name for the list items.  <i>Type</i> can include a module qualifier (for example, <b>mymodule!mytype</b>).  If <b>m_TypeId</b> is not zero, <i>Type</i> is not used.

</dd>
<dt><a id="m_TypeModBase"></a><a id="m_typemodbase"></a><a id="M_TYPEMODBASE"></a><b>m_TypeModBase</b></dt>
<dd>
The location in the target's memory of the base address of the module that contains the type specified by <b>m_TypeId</b>.  If <b>m_TypeId</b> is zero, <b>m_TypeModBase</b> is not used.

</dd>
<dt><a id="m_TypeId"></a><a id="m_typeid"></a><a id="M_TYPEID"></a><b>m_TypeId</b></dt>
<dd>
The type ID of the type relative to the module specified by <b>m_TypeModBase</b>.  If <b>m_TypeId</b> is zero, <b>m_Type</b> is used to specify the type of the list items.

</dd>
</dl>

## -see-also

<a href="..\engextcpp\nl-engextcpp-extremotetypedlist.md">ExtRemoteTypedList::ExtRemoteTypedList(ULONG64)</a>



<a href="..\engextcpp\nl-engextcpp-extremotelist.md">ExtRemoteList</a>



<a href="..\engextcpp\nl-engextcpp-extremotetypedlist.md">ExtRemoteTypedList::ExtRemoteTypedList(ExtRemoteData)</a>



<a href="https://msdn.microsoft.com/f6e2d8e3-294d-45d8-8fc6-33af3a746244">SetTypeAndLink</a>



<a href="https://msdn.microsoft.com/f74090c9-4e15-4d6c-bb62-b8d5c56d5a1c">GetTypedNode</a>



<a href="https://msdn.microsoft.com/3bf50952-7ac9-4c6b-9318-dd64748de9d2">GetTypedNodePtr</a>



<a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a>



 

 


