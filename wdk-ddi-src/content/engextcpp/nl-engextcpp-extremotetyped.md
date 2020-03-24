---
UID: NL:engextcpp.ExtRemoteTyped
title: ExtRemoteTyped (engextcpp.h)
description: The ExtRemoteTyped class provides the ability to manipulate typed data on the target.
old-location: debugger\extremotetyped.htm
tech.root: debugger
ms.assetid: 1f5d71a5-fa60-4819-9838-2b035ef21374
ms.date: 08/09/2018
keywords: ["ExtRemoteTyped class"]
ms.keywords: EngExtCpp_Ref_04970dac-e759-4a04-a1e0-8dab752c1418.xml, ExtRemoteTyped, ExtRemoteTyped class [Windows Debugging], ExtRemoteTyped class [Windows Debugging],described, debugger.extremotetyped, engextcpp/ExtRemoteTyped
f1_keywords:
 - "engextcpp/ExtRemoteTyped"
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
req.lib: 
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
- ExtRemoteTyped
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExtRemoteTyped class


## -description


The <b>ExtRemoteTyped</b> class provides the ability to manipulate typed data on the target.  An instance of this class represents a small region of memory on the target. This region is interpreted as a specific type.  This class provides methods for manipulating the memory according to the type and for accessing the object hierarchy on the target.

<b>ExtRemoteTyped</b> is a subclass of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a>.

The <b>ExtRemoteTyped</b> class includes the following constructors, operators, and methods:
<dl>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nl-engextcpp-extremotetyped">ExtRemoteTyped</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-operator-assign(constextremotetyped-)">operator=</a>


</dd>

<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-copy">Copy(Debug Typed Data)</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-copy(constextremotetyped_)">Copy(ExtRemoteTyped)</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-set(bool_ulong64_ulong_ulong64)">Set(bool)</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-set">Set(pcstr)</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-set(pcstr_ulong64)">Set(pcstr ulong64)</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-set(pcstr_ulong64_bool_pulong64_pcstr)">Set(pcstr ulong64 bool)</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-setprint">SetPrint</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-hasfield">HasField</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-gettypesize">GetTypeSize</a>


</dd>
<dd>
<b>GetFieldSize</b>

</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols-getfieldoffset">GetFieldOffset</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-field">Field</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-arrayelement">ArrayElement</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-dereference">Dereference</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-getpointerto">GetPointerTo</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtf/nf-wdtf-iwdtftarget2-eval">Eval</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/ff544357(v=vs.85)">operator*</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-operator-index">operator[]</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-operator-index">operator[]</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-operator-index">operator[]</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-operator-index">operator[]</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-gettypename">GetTypeName</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-outtypename">OutTypeName</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-outsimplevalue">OutSimpleValue</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-outfullvalue">OutFullValue</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-outtypedefinition">OutTypeDefinition</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-release">Release</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-gettypefieldoffset">GetTypeFieldOffset</a>


</dd>
</dl><pre class="syntax" xml:space="preserve"><code>class ExtRemoteTyped : public ExtRemoteData
{
public:
    DEBUG_TYPED_DATA  m_Typed;
    bool  m_Release;
};


</code></pre>
<dl>
<dt><a id="m_Typed"></a><a id="m_typed"></a><a id="M_TYPED"></a><b>m_Typed</b></dt>
<dd>
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/ns-wdbgexts-_debug_typed_data">DEBUG_TYPED_DATA</a> structure that describes the typed data represented by this instance of <b>ExtRemoteTyped</b>.

</dd>
<dt><a id="m_Release"></a><a id="m_release"></a><a id="M_RELEASE"></a><b>m_Release</b></dt>
<dd>
Indicates whether or not the destructor for this instance of <b>ExtRemoteTyped</b> needs to release the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/ns-wdbgexts-_debug_typed_data">DEBUG_TYPED_DATA</a> structure that is specified in <b>m_Typed</b>.

</dd>
</dl>

## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/ns-wdbgexts-_debug_typed_data">DEBUG_TYPED_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a>
 

 

