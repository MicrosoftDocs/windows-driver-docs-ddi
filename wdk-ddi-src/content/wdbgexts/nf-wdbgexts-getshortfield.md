---
UID: NF:wdbgexts.GetShortField
title: GetShortField function
author: windows-driver-content
description: The GetShortField function reads the value of a member in a structure if its size is less than or equal to 8 bytes, or initializes a structure so it can be read later.
old-location: debugger\getshortfield.htm
old-project: debugger
ms.assetid: f5f00e88-b758-4f37-9fe5-5db8f20835b1
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: GetShortField
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GetShortField
req.alt-loc: wdbgexts.h
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
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---

# GetShortField function



## -description
The <b>GetShortField</b> function reads the value of a member in a structure if its size is less than or equal to 8 bytes, or initializes a structure so it can be read later.  This function is not intended to be used directly; <a href="https://msdn.microsoft.com/library/windows/hardware/ff550953">InitTypeRead</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff550957">InitTypeReadPhysical</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff553539">ReadField</a> should be used instead.



## -syntax

````
__inline ULONG64 GetShortField(
  _In_ ULONG64 TypeAddress,
  _In_ LPCSTR  Name,
  _In_ USHORT  StoreAddress
);
````


## -parameters

### -param TypeAddress [in]

The meaning of this parameter depends on the value of <i>StoreAddress</i>.




### -param If StoreAddress is non-zero:

Specifies the address of the structure in the target's memory.  This address is used for subsequent calls when <i>StoreAddress</i> is zero. 


### -param If StoreAddress is zero:

<i>TypeAddress</i> is ignored.  The value of <i>TypeAddress</i> from the last call when <i>StoreAddress</i> was non-zero is used to specify the address of the structure in the target's memory. 

</dd>
</dl>

### -param Name [in]

The meaning of this parameter depends on the value of <i>StoreAddress</i>.




### -param If StoreAddress is non-zero:

Specifies the name of the type of the structure at <i>TypeAddress</i>.


### -param If StoreAddress is zero:

Specifies the name of the member in the structure to read.  The address and type of the structure are remembered from a previous call to this function with <i>StoreAddress</i> not equal to zero.  Submembers can be specified by using a period-separated path, for example, "myfield.mysubfield". 

</dd>
</dl>

### -param StoreAddress [in]

Specifies the mode of this function.




### -param If StoreAddress is non-zero:

Causes this function to initialize a structure for reading its members.  The address and type name for the structure is remembered.

If the bit value 0x2 is set in <i>StoreAddress</i>, the address <i>TypeAddress</i> is considered a physical address; otherwise, it is considered a virtual address. 


### -param If StoreAddress is zero:

Causes this function to read a member from a previously initialized structure. 

</dd>
</dl>

## -returns
<dl>
<dt><b>If <i>StoreAddress</i> is non-zero:</b></dt>
</dl>If the function succeeds, it returns the value zero.  If the function fails because the caller passed a zero value as <i>TypeAddress</i>, it returns the value MEMORY_READ_ERROR (defined in Wdbgexts.h).  If the function fails for any other reason, it returns an <a href="https://msdn.microsoft.com/41d64bbc-cefe-4665-b054-e6bd135ccd20">IG_DUMP_SYMBOL_INFO error code</a>.
<dl>
<dt><b>If <i>StoreAddress</i> is zero:</b></dt>
</dl>If the function succeeds, it returns the value of the specified field in the previously initialized structure.  The structure is the one initialized in a previous call to <b>GetShortField</b>.  The field is the one specified by the <i>Name</i> parameter of the current call to <b>GetShortField</b>. The return value is cast to ULONG64.  If the function fails, it returns the value zero. 

 


## -remarks
When <b>GetShortField</b> is called with a nonzero <i>StoreAddress</i> value, it initializes the structure located at the address specified by <i>TypeAddress</i>. Only one structure can be initialized at a time. If <b>GetShortField</b> is called more than once with a nonzero <i>StoreAddress</i> value, only the structure specified in the most recent call is initialized. When <b>GetShortField</b> is called with <i>StoreAddress</i> equal to zero, it accesses the most recently initialized structure, reads in that structure the field specified by <i>Name</i>, and returns the value of that field. 

This function does not need to be called directly.  The macros <a href="https://msdn.microsoft.com/library/windows/hardware/ff550953">InitTypeRead</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550957">InitTypeReadPhysical</a> call this function with <i>StoreAddress</i> non-zero to prepare a structure for reading its members.  The macro <a href="https://msdn.microsoft.com/library/windows/hardware/ff553539">ReadField</a> calls this function with <i>StoreAddress</i> (and <i>TypeAddress</i>) equal to zero, to read members from the structure.

The <b>ReadField</b> and <b>ReadFieldStr</b> macros read a field whose size is less than 8 bytes from a structure initialized with <a href="https://msdn.microsoft.com/library/windows/hardware/ff550953">InitTypeRead</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff550957">InitTypeReadPhysical</a>. 


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550953">InitTypeRead</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550957">InitTypeReadPhysical</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553539">ReadField</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20GetShortField function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

