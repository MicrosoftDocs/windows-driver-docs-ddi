---
UID: NF:engextcpp.ExtRemoteData.SetUshort
title: ExtRemoteData::SetUshort method
description: The ExtRemoteData class provides a wrapper around a small section of a target's memory. ExtRemoteData automatically retrieves the memory and provides a number of convenience methods.
old-location: debugger\extremotedata.htm
tech.root: debugger
ms.assetid: d645867c-3264-45ae-b0bd-4d21e388fb97
ms.date: 01/19/2018
ms.keywords: ExtRemoteData::SetChar, SetLong64, ExtRemoteData::SetUlongPtr, ExtRemoteData::SetPtr, SetUlong, ExtRemoteData::SetStdBool, ExtRemoteData::SetUchar, ExtRemoteData::SetUshort, ExtRemoteData::SetData, SetLongPtr, SetBoolean, SetLong, SetUlongPtr, SetUshort, SetUlong64, SetUchar, ExtRemoteData::SetFloat, SetDouble, ExtRemoteData, ExtRemoteData::SetLong64, SetShort, SetChar, ExtRemoteData::SetLong, ExtRemoteData::SetBoolean, ExtRemoteData class [Windows Debugging], described, EngExtCpp_Ref_e84c03ce-1156-481b-a429-f0a918797565.xml, Clear, ExtRemoteData::SetShort, ExtRemoteData::SetLongPtr, SetPtr, SetFloat, debugger.extremotedata, ExtRemoteData class [Windows Debugging], ExtRemoteData::SetUlong, engextcpp/ExtRemoteData, ExtRemoteData::SetDouble, SetStdBool, ExtRemoteData::Clear, SetData, ExtRemoteData::SetUlong64
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	engextcpp.hpp
apiname:
-	ExtRemoteData
product:
- Windows
targetos: Windows
req.typenames: DXVA_VideoSample32
---

# ExtRemoteData::SetUshort method


## -description


The <b>ExtRemoteData</b> class provides a wrapper around a small section of a target's memory.  <b>ExtRemoteData</b> automatically retrieves the memory and provides a number of convenience methods.

The <b>ExtRemoteData</b> class includes the following constructors and methods:
<dl>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/a335f881-7b6f-4069-87fe-c036867b0c77">Set(Typed)</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/50b4bee4-3a8c-45a1-9a3f-b416aa8a19e5">Set(Offset Bytes)</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439702">Read</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439706">Write</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/dn949631">GetData</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/bf916e7c-f03b-4d02-8260-bc90e8957cc9">GetChar</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/2c4b7f40-210a-44fa-b7d4-150355d6b75b">GetUchar</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/7a580683-ae56-4566-95b4-b4d42ae0e1ab">GetBoolean</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/f6a55181-7e1a-4af0-ac45-1991c42cdc87">GetStdBool</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/a17812f5-4e20-4793-9352-3cabed25a6da">GetW32Bool</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/5e364e83-76db-44b0-b5bc-15eed53bbbdf">GetShort</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/e5e2061f-5133-4645-8e07-659f08473a51">GetUshort</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/064f50e7-bae8-4c29-9802-47efdb749652">GetLong</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/jj983420">GetUlong</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/dd6f051a-d287-4cb9-8c53-928415e0f152">GetLong64</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/jj983421">GetUlong64</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/f2781f6b-cc3e-427c-8181-908639613270">GetFloat</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/f8645e92-659f-42b8-a850-49a434ec2a67">GetDouble</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/9f796af1-870b-4349-b86a-3c9d868662f6">GetLongPtr</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/1a3a870b-9f50-4430-b4f4-6d877d2fac3e">GetUlongPtr</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/f9778881-9b53-49c5-9fe8-80f9a866b9af">GetPtr</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/1ad13196-a133-4168-9a36-1f7e4ed5c4f1">ReadBuffer</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/b50f0cf3-4cd5-4f9e-9749-49b1c9365a8f">WriteBuffer</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/jj983419">GetString</a>


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
The name given to this instance of <b>ExtRemoteData</b>.  This name is used to provide meaningful error messages and is set by the constructor, <a href="https://msdn.microsoft.com/library/windows/hardware/ff544006">ExtRemoteData::ExtRemoteData</a>.

</dd>
<dt><a id="m_Offset"></a><a id="m_offset"></a><a id="M_OFFSET"></a><b>m_Offset</b></dt>
<dd>
The location in the target's memory (virtual or physical) of the region of memory represented by this instance of <b>ExtRemoteData</b>.  It can be set by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544006">ExtRemoteData::ExtRemoteData</a> constructor or by the <a href="https://msdn.microsoft.com/a335f881-7b6f-4069-87fe-c036867b0c77">ExtRemoteData::Set(Typed)</a> or <a href="https://msdn.microsoft.com/50b4bee4-3a8c-45a1-9a3f-b416aa8a19e5">ExtRemoteData::Set(Offset Bytes)</a> methods.

</dd>
<dt><a id="m_ValidOffset"></a><a id="m_validoffset"></a><a id="M_VALIDOFFSET"></a><b>m_ValidOffset</b></dt>
<dd>
Indicates whether the <b>m_Offset</b>location is valid.  If <b>m_ValidOffset</b> is <code>false</code>, the location is not valid and most of the methods for this object will not work. In this case, the <a href="https://msdn.microsoft.com/a335f881-7b6f-4069-87fe-c036867b0c77">ExtRemoteData::Set(Typed)</a> or <a href="https://msdn.microsoft.com/50b4bee4-3a8c-45a1-9a3f-b416aa8a19e5">ExtRemoteData::Set(Offset Bytes)</a> methods can be called to change <b>m_Offset</b> to a valid location.

</dd>
<dt><a id="m_Bytes"></a><a id="m_bytes"></a><a id="M_BYTES"></a><b>m_Bytes</b></dt>
<dd>
The size, in bytes, of the region of memory represented by this object.  It can be set by the
	  <a href="https://msdn.microsoft.com/library/windows/hardware/ff544006">ExtRemoteData::ExtRemoteData</a> constructor
	  or by the <a href="https://msdn.microsoft.com/a335f881-7b6f-4069-87fe-c036867b0c77">ExtRemoteData::Set(Typed)</a> or <a href="https://msdn.microsoft.com/50b4bee4-3a8c-45a1-9a3f-b416aa8a19e5">ExtRemoteData::Set(Offset Bytes)</a> methods.

</dd>
<dt><a id="m_Data"></a><a id="m_data"></a><a id="M_DATA"></a><b>m_Data</b></dt>
<dd>
The cached contents of the region of memory specified by this instance of <b>ExtRemoteData</b>.  Setting this member is optional. If the region of memory is large, it will not be cached.

</dd>
<dt><a id="m_ValidData"></a><a id="m_validdata"></a><a id="M_VALIDDATA"></a><b>m_ValidData</b></dt>
<dd>
Indicates whether the <b>m_Data </b>cached data is valid.  If <b>m_ValidData</b> is <code>false</code>, the cached data is not valid and most of the methods for this object will not work. In this case, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544083">ExtRemoteData::Read</a> method can be called to refresh the cached data.

</dd>
<dt><a id="m_Physical"></a><a id="m_physical"></a><a id="M_PHYSICAL"></a><b>m_Physical</b></dt>
<dd>
Indicates whether the <b>m_Offset</b> location is in the target's virtual address space or in its physical address space.  If <b>m_Physical</b> is <code>true</code>, the <b>m_Offset</b>location is in the target's physical address space.  If <b>m_Physical</b> is  <code>false</code>, the <b>m_Offset</b> location  is in the target's virtual address space.

</dd>
<dt><a id="m_SpaceFlags"></a><a id="m_spaceflags"></a><a id="M_SPACEFLAGS"></a><b>m_SpaceFlags</b></dt>
<dd>
The DEBUG_PHYSICAL_<i>XXX</i> flags used for accessing physical memory on the target.  These flags are only used if <b>m_Physical</b> is <code>true</code>.  For a description of these flags, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554311">ReadPhysical2</a> method.

</dd>
</dl>

## -parameters


## -see-also

<a href="https://msdn.microsoft.com/a335f881-7b6f-4069-87fe-c036867b0c77">ExtRemoteData::Set(Typed)</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554311">ReadPhysical2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544006">ExtRemoteData::ExtRemoteData</a>

<a href="https://msdn.microsoft.com/50b4bee4-3a8c-45a1-9a3f-b416aa8a19e5">ExtRemoteData::Set(Offset Bytes)</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544083">ExtRemoteData::Read</a>

 

 


