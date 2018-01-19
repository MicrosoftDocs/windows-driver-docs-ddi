---
UID: NF:engextcpp.ExtRemoteData.SetLong
title: ExtRemoteData::SetLong method
author: windows-driver-content
description: The ExtRemoteData class provides a wrapper around a small section of a target's memory. ExtRemoteData automatically retrieves the memory and provides a number of convenience methods.
old-location: debugger\extremotedata.htm
old-project: debugger
ms.assetid: d645867c-3264-45ae-b0bd-4d21e388fb97
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ExtRemoteData, ExtRemoteData::SetLong, SetLong
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: engextcpp.hpp
req.include-header: Engextcpp.hpp
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ExtRemoteData
req.alt-loc: engextcpp.hpp
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
req.typenames: *PSILO_DRIVER_CAPABILITIES, SILO_DRIVER_CAPABILITIES
---

# ExtRemoteData::SetLong method



## -description
The <b>ExtRemoteData</b> class provides a wrapper around a small section of a target's memory.  <b>ExtRemoteData</b> automatically retrieves the memory and provides a number of convenience methods.

The <b>ExtRemoteData</b> class includes the following constructors and methods:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a>



<a href="https://msdn.microsoft.com/a335f881-7b6f-4069-87fe-c036867b0c77">Set(Typed)</a>



<a href="https://msdn.microsoft.com/50b4bee4-3a8c-45a1-9a3f-b416aa8a19e5">Set(Offset Bytes)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439702">Read</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439706">Write</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn949631">GetData</a>



<a href="https://msdn.microsoft.com/bf916e7c-f03b-4d02-8260-bc90e8957cc9">GetChar</a>



<a href="https://msdn.microsoft.com/2c4b7f40-210a-44fa-b7d4-150355d6b75b">GetUchar</a>



<a href="https://msdn.microsoft.com/7a580683-ae56-4566-95b4-b4d42ae0e1ab">GetBoolean</a>



<a href="https://msdn.microsoft.com/f6a55181-7e1a-4af0-ac45-1991c42cdc87">GetStdBool</a>



<a href="https://msdn.microsoft.com/a17812f5-4e20-4793-9352-3cabed25a6da">GetW32Bool</a>



<a href="https://msdn.microsoft.com/5e364e83-76db-44b0-b5bc-15eed53bbbdf">GetShort</a>



<a href="https://msdn.microsoft.com/e5e2061f-5133-4645-8e07-659f08473a51">GetUshort</a>



<a href="https://msdn.microsoft.com/064f50e7-bae8-4c29-9802-47efdb749652">GetLong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983420">GetUlong</a>



<a href="https://msdn.microsoft.com/dd6f051a-d287-4cb9-8c53-928415e0f152">GetLong64</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983421">GetUlong64</a>



<a href="https://msdn.microsoft.com/f2781f6b-cc3e-427c-8181-908639613270">GetFloat</a>



<a href="https://msdn.microsoft.com/f8645e92-659f-42b8-a850-49a434ec2a67">GetDouble</a>



<a href="https://msdn.microsoft.com/9f796af1-870b-4349-b86a-3c9d868662f6">GetLongPtr</a>



<a href="https://msdn.microsoft.com/1a3a870b-9f50-4430-b4f4-6d877d2fac3e">GetUlongPtr</a>



<a href="https://msdn.microsoft.com/f9778881-9b53-49c5-9fe8-80f9a866b9af">GetPtr</a>



<a href="https://msdn.microsoft.com/1ad13196-a133-4168-9a36-1f7e4ed5c4f1">ReadBuffer</a>



<a href="https://msdn.microsoft.com/b50f0cf3-4cd5-4f9e-9749-49b1c9365a8f">WriteBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983419">GetString</a>




The name given to this instance of <b>ExtRemoteData</b>.  This name is used to provide meaningful error messages and is set by the constructor, <a href="https://msdn.microsoft.com/library/windows/hardware/ff544006">ExtRemoteData::ExtRemoteData</a>.

The location in the target's memory (virtual or physical) of the region of memory represented by this instance of <b>ExtRemoteData</b>.  It can be set by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544006">ExtRemoteData::ExtRemoteData</a> constructor or by the <a href="https://msdn.microsoft.com/a335f881-7b6f-4069-87fe-c036867b0c77">ExtRemoteData::Set(Typed)</a> or <a href="https://msdn.microsoft.com/50b4bee4-3a8c-45a1-9a3f-b416aa8a19e5">ExtRemoteData::Set(Offset Bytes)</a> methods.

Indicates whether the <b>m_Offset</b>location is valid.  If <b>m_ValidOffset</b> is <code>false</code>, the location is not valid and most of the methods for this object will not work. In this case, the <a href="https://msdn.microsoft.com/a335f881-7b6f-4069-87fe-c036867b0c77">ExtRemoteData::Set(Typed)</a> or <a href="https://msdn.microsoft.com/50b4bee4-3a8c-45a1-9a3f-b416aa8a19e5">ExtRemoteData::Set(Offset Bytes)</a> methods can be called to change <b>m_Offset</b> to a valid location.

The size, in bytes, of the region of memory represented by this object.  It can be set by the
	  <a href="https://msdn.microsoft.com/library/windows/hardware/ff544006">ExtRemoteData::ExtRemoteData</a> constructor 
	  or by the <a href="https://msdn.microsoft.com/a335f881-7b6f-4069-87fe-c036867b0c77">ExtRemoteData::Set(Typed)</a> or <a href="https://msdn.microsoft.com/50b4bee4-3a8c-45a1-9a3f-b416aa8a19e5">ExtRemoteData::Set(Offset Bytes)</a> methods.

The cached contents of the region of memory specified by this instance of <b>ExtRemoteData</b>.  Setting this member is optional. If the region of memory is large, it will not be cached.

Indicates whether the <b>m_Data </b>cached data is valid.  If <b>m_ValidData</b> is <code>false</code>, the cached data is not valid and most of the methods for this object will not work. In this case, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544083">ExtRemoteData::Read</a> method can be called to refresh the cached data.

Indicates whether the <b>m_Offset</b> location is in the target's virtual address space or in its physical address space.  If <b>m_Physical</b> is <code>true</code>, the <b>m_Offset</b>location is in the target's physical address space.  If <b>m_Physical</b> is  <code>false</code>, the <b>m_Offset</b> location  is in the target's virtual address space.

The DEBUG_PHYSICAL_<i>XXX</i> flags used for accessing physical memory on the target.  These flags are only used if <b>m_Physical</b> is <code>true</code>.  For a description of these flags, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554311">ReadPhysical2</a> method.



## -parameters


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544006">ExtRemoteData::ExtRemoteData</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544083">ExtRemoteData::Read</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/a335f881-7b6f-4069-87fe-c036867b0c77">ExtRemoteData::Set(Typed)</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/50b4bee4-3a8c-45a1-9a3f-b416aa8a19e5">ExtRemoteData::Set(Offset Bytes)</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554311">ReadPhysical2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteData class%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

