---
UID: NF:engextcpp.ExtRemoteData.SetDouble
title: ExtRemoteData::SetDouble method (engextcpp.h)
description: The ExtRemoteData class provides a wrapper around a small section of a target's memory. ExtRemoteData automatically retrieves the memory and provides a number of convenience methods.
old-location: debugger\extremotedata.htm
tech.root: debugger
ms.assetid: d645867c-3264-45ae-b0bd-4d21e388fb97
ms.date: 01/19/2018
ms.keywords: ExtRemoteData class [Windows Debugging], described, ExtRemoteData::SetChar, EngExtCpp_Ref_e84c03ce-1156-481b-a429-f0a918797565.xml, Clear, debugger.extremotedata, ExtRemoteData::Clear, ExtRemoteData class [Windows Debugging], SetDouble, ExtRemoteData, engextcpp/ExtRemoteData, ExtRemoteData::SetDouble, SetChar, ExtRemoteData::SetBoolean, ExtRemoteData::SetData, SetData, SetBoolean
ms.topic: method
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
- ExtRemoteData
product:
- Windows
targetos: Windows
req.typenames: DXVA_VideoSample32
---

# ExtRemoteData::SetDouble method


## -description


The <b>ExtRemoteData</b> class provides a wrapper around a small section of a target's memory.  <b>ExtRemoteData</b> automatically retrieves the memory and provides a number of convenience methods.

The <b>ExtRemoteData</b> class includes the following constructors and methods:
<dl>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-set(constdebug_typed_data)">Set(Typed)</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-set">Set(Offset Bytes)</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterscriptablesequentialstream-read">Read</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterscriptablesequentialstream-write">Write</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/test/hlk/testref/9be92a88-98d7-496e-ac6c-0a59432a89d5">GetData</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-getchar">GetChar</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-getuchar">GetUchar</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-getboolean">GetBoolean</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-getstdbool">GetStdBool</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-getw32bool">GetW32Bool</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-getshort">GetShort</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-getushort">GetUshort</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-getlong">GetLong</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nf-extsfns-idebugfailureanalysis2-getulong">GetUlong</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-getlong64">GetLong64</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nf-extsfns-idebugfailureanalysis2-getulong64">GetUlong64</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-getfloat">GetFloat</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-getdouble">GetDouble</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-getlongptr">GetLongPtr</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-getulongptr">GetUlongPtr</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-getptr">GetPtr</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-readbuffer">ReadBuffer</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-writebuffer">WriteBuffer</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nf-extsfns-idebugfailureanalysis2-getstring">GetString</a>


</dd>
</dl><pre class="syntax" xml:space="preserve"><code>class ExtRemoteData
{
public:
    PCSTR  m_Name;
    ULONG64  m_Offset;
    bool  m_ValidOffset;
    ULONG  m_Bytes;
    ULONG64  m_Data;
    bool  m_ValidData;
    bool  m_Physical;
    ULONG  m_SpaceFlags;
};</code></pre>
<dl>
<dt><a id="m_Name"></a><a id="m_name"></a><a id="M_NAME"></a><b>m_Name</b></dt>
<dd>
The name given to this instance of <b>ExtRemoteData</b>.  This name is used to provide meaningful error messages and is set by the constructor, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-extremotedata">ExtRemoteData::ExtRemoteData</a>.

</dd>
<dt><a id="m_Offset"></a><a id="m_offset"></a><a id="M_OFFSET"></a><b>m_Offset</b></dt>
<dd>
The location in the target's memory (virtual or physical) of the region of memory represented by this instance of <b>ExtRemoteData</b>.  It can be set by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-extremotedata">ExtRemoteData::ExtRemoteData</a> constructor or by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-set(constdebug_typed_data)">ExtRemoteData::Set(Typed)</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-set">ExtRemoteData::Set(Offset Bytes)</a> methods.

</dd>
<dt><a id="m_ValidOffset"></a><a id="m_validoffset"></a><a id="M_VALIDOFFSET"></a><b>m_ValidOffset</b></dt>
<dd>
Indicates whether the <b>m_Offset</b>location is valid.  If <b>m_ValidOffset</b> is <code>false</code>, the location is not valid and most of the methods for this object will not work. In this case, the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-set(constdebug_typed_data)">ExtRemoteData::Set(Typed)</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-set">ExtRemoteData::Set(Offset Bytes)</a> methods can be called to change <b>m_Offset</b> to a valid location.

</dd>
<dt><a id="m_Bytes"></a><a id="m_bytes"></a><a id="M_BYTES"></a><b>m_Bytes</b></dt>
<dd>
The size, in bytes, of the region of memory represented by this object.  It can be set by the
	  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-extremotedata">ExtRemoteData::ExtRemoteData</a> constructor
	  or by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-set(constdebug_typed_data)">ExtRemoteData::Set(Typed)</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-set">ExtRemoteData::Set(Offset Bytes)</a> methods.

</dd>
<dt><a id="m_Data"></a><a id="m_data"></a><a id="M_DATA"></a><b>m_Data</b></dt>
<dd>
The cached contents of the region of memory specified by this instance of <b>ExtRemoteData</b>.  Setting this member is optional. If the region of memory is large, it will not be cached.

</dd>
<dt><a id="m_ValidData"></a><a id="m_validdata"></a><a id="M_VALIDDATA"></a><b>m_ValidData</b></dt>
<dd>
Indicates whether the <b>m_Data </b>cached data is valid.  If <b>m_ValidData</b> is <code>false</code>, the cached data is not valid and most of the methods for this object will not work. In this case, the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-read">ExtRemoteData::Read</a> method can be called to refresh the cached data.

</dd>
<dt><a id="m_Physical"></a><a id="m_physical"></a><a id="M_PHYSICAL"></a><b>m_Physical</b></dt>
<dd>
Indicates whether the <b>m_Offset</b> location is in the target's virtual address space or in its physical address space.  If <b>m_Physical</b> is <code>true</code>, the <b>m_Offset</b>location is in the target's physical address space.  If <b>m_Physical</b> is  <code>false</code>, the <b>m_Offset</b> location  is in the target's virtual address space.

</dd>
<dt><a id="m_SpaceFlags"></a><a id="m_spaceflags"></a><a id="M_SPACEFLAGS"></a><b>m_SpaceFlags</b></dt>
<dd>
The DEBUG_PHYSICAL_<i>XXX</i> flags used for accessing physical memory on the target.  These flags are only used if <b>m_Physical</b> is <code>true</code>.  For a description of these flags, see the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-readphysical2">ReadPhysical2</a> method.

</dd>
</dl>

## -parameters


## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-set(constdebug_typed_data)">ExtRemoteData::Set(Typed)</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugdataspaces4-readphysical2">ReadPhysical2</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-extremotedata">ExtRemoteData::ExtRemoteData</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-set">ExtRemoteData::Set(Offset Bytes)</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-read">ExtRemoteData::Read</a>

 

 


