---
UID: NF:engextcpp.ExtRemoteTyped.Set(PCSTR,ULONG64,bool,PULONG64,PCSTR)
title: ExtRemoteTyped::Set(PCSTR,ULONG64,bool,PULONG64,PCSTR) (engextcpp.h)
description: The Set method sets the typed data represented by the ExtRemoteTyped object.
old-location: debugger\extremotetyped_set_pcstr_ulong64_bool.htm
tech.root: debugger
ms.assetid: fc3d8d9c-0b19-42b3-b4d7-90df4667739b
ms.date: 05/03/2018
ms.keywords: ExtRemoteTyped class [Windows Debugging],Set method, ExtRemoteTyped.Set, ExtRemoteTyped.Set(PCSTR,ULONG64,bool,PULONG64,PCSTR), ExtRemoteTyped::Set, ExtRemoteTyped::Set(PCSTR,ULONG64,bool,PULONG64,PCSTR), Set, Set method [Windows Debugging], Set method [Windows Debugging],ExtRemoteTyped class, debugger.extremotetyped_set_pcstr_ulong64_bool
ms.topic: method
req.header: engextcpp.hpp
req.include-header: Engextcpp.hpp
req.target-type: Desktop
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
-	COM
api_location:
-	engextcpp.hpp
api_name:
-	ExtRemoteTyped.Set
product:
-	Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# ExtRemoteTyped::Set(PCSTR,ULONG64,bool,PULONG64,PCSTR)


## -description


The <b>Set</b> method sets the typed data represented by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544162">ExtRemoteTyped</a> object.


## -parameters




### -param Type [in]

The type name of the type.  <i>Type</i> can include a module qualifier--for example, <b>mymodule!mytype</b>.  The module qualifier can be omitted, but it is recommended that it be included if the module is known.


### -param Offset [in]

Specifies the location of the data in the target's memory.


### -param PtrTo [in]

Specifies whether or not to set the <b>ExtRemoteTyped</b> instance to the specified typed data, or to a pointer to the specified typed data.  If <i>PtrTo</i> is <code>true</code>, the <b>ExtRemoteTyped</b> instance will be a pointer to the typed data.


### -param CacheCookie [in, out, optional]

A cache cookie used for caching the type information.  If <i>CacheCookie</i> is <b>NULL</b>, the debugger engine will search for the type information each time.

A <i>cache cookie</i> is a pointer to a ULONG64. It is associated with a particular symbol that is uniquely identified by the symbol's type ID and the address of the module that contains the symbol.  The first time it is used, the ULONG64 that cache cookie points to must be set to 0. In this case, the debugger engine will search for the symbol information and cache it, then it will set the cookie so that the symbol information can be easily retrieved later.  Whenever you use a subsequent method that will need information about the same symbol, use the cache cookie.  The debugger engine will then be able to retrieve the symbol information from the cache instead of searching for it.  Each cache cookie should only be used with a single type.  If a cache cookie is used in conjunction with a different symbol, the cache cookie might be corrupted.


### -param LinkField [in, optional]

The name of a field in the typed data structure which contains the pointer to the next item in a list.  <i>LinkField</i> should be set if <i>CacheCookie</i> is being used for the first time and will later be used with <a href="https://msdn.microsoft.com/library/windows/hardware/ff544181">ExtRemoteTypedList</a>.


## -returns



This method does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544162">ExtRemoteTyped</a>



<a href="https://msdn.microsoft.com/a19d6aff-c4e4-4188-8f27-3689e91023b4">ExtRemoteTyped::Set (PCSTR)</a>



<a href="https://msdn.microsoft.com/acf789f7-781d-4078-90cc-79b0d2709696">ExtRemoteTyped::Set (PCSTR, ULONG64)</a>



<a href="https://msdn.microsoft.com/e75c17d2-fdf7-4dba-9892-74c764956924">ExtRemoteTyped::Set (bool)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544384">ExtRemoteTyped::SetPrint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544181">ExtRemoteTypedList</a>
 

 

