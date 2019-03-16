---
UID: NF:engextcpp.ExtRemoteTyped.ExtRemoteTyped(PCSTR,ULONG64,bool,PULONG64,PCSTR)
title: ExtRemoteTyped::ExtRemoteTyped(PCSTR,ULONG64,bool,PULONG64,PCSTR) (engextcpp.h)
description: The ExtRemoteTyped constructor creates a new instance of the ExtRemoteTyped class.
old-location: debugger\extremotetyped_extremotetyped_pcstr_ulong64_bool.htm
tech.root: debugger
ms.assetid: 824f47da-2a56-4e09-b23a-a9754c1e2063
ms.date: 05/03/2018
ms.keywords: ExtRemoteTyped, ExtRemoteTyped class [Windows Debugging],ExtRemoteTyped constructor, ExtRemoteTyped constructor [Windows Debugging], ExtRemoteTyped constructor [Windows Debugging],ExtRemoteTyped class, ExtRemoteTyped.ExtRemoteTyped, ExtRemoteTyped.ExtRemoteTyped(PCSTR,ULONG64,bool,PULONG64,PCSTR), ExtRemoteTyped::ExtRemoteTyped, ExtRemoteTyped::ExtRemoteTyped(PCSTR,ULONG64,bool,PULONG64,PCSTR), debugger.extremotetyped_extremotetyped_pcstr_ulong64_bool
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- engextcpp.hpp
api_name:
- ExtRemoteTyped.ExtRemoteTyped
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# ExtRemoteTyped::ExtRemoteTyped(PCSTR,ULONG64,bool,PULONG64,PCSTR)


## -description


The <b>ExtRemoteTyped</b> constructor creates a new instance of the <b>ExtRemoteTyped</b> class.


## -parameters




### -param Type [in]

An expression that evaluates to the desired symbol.  This expression is evaluated by the default expression evaluator.


### -param Offset [in]

The location of the data in the target's virtual address space.



### -param PtrTo [in]

Specifies whether or not to set the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544162">ExtRemoteTyped</a> instance to the specified typed data, or to a pointer to the specified typed data. If <i>PtrTo</i> is true, the <b>ExtRemoteTyped</b> instance will contain a pointer to the typed data. 



### -param CacheCookie [in, out, optional]

The cache cookie to use for caching type information. If <i>CacheCookie</i> is <b>NULL</b>, the debugger engine will search for type information each time.


For more information about <i>CacheCookie</i>, see the following methods:

<ul>
<li>

<a href="https://msdn.microsoft.com/e75c17d2-fdf7-4dba-9892-74c764956924">ExtRemoteTyped::Set(bool)</a>


</li>
<li>

<a href="https://msdn.microsoft.com/a19d6aff-c4e4-4188-8f27-3689e91023b4">ExtRemoteTyped::Set(pcstr)</a>


</li>
<li>

<a href="https://msdn.microsoft.com/acf789f7-781d-4078-90cc-79b0d2709696">ExtRemoteTyped::Set(pcstr ulong64)</a>


</li>
<li>

<a href="https://msdn.microsoft.com/fc3d8d9c-0b19-42b3-b4d7-90df4667739b">ExtRemoteTyped::Set(pcstr ulong64 bool)</a>


</li>
</ul>

### -param LinkField [in, optional]

The name of a field in the typed data that contains the pointer to the next item in a list. <i>LinkField</i> should be set if <i>CacheCookie</i> is being used for the first time and will later be used with <a href="https://msdn.microsoft.com/library/windows/hardware/ff544181">ExtRemoteTypedList</a>. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541706">DEBUG_TYPED_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544162">ExtRemoteTyped</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544242">ExtRemoteTyped::ExtRemoteTyped</a>



<a href="https://msdn.microsoft.com/6cfe4258-be66-49fd-b154-124951ed0dd1">ExtRemoteTyped::ExtRemoteTyped (DEBUG_TYPED_DATA)</a>



<a href="https://msdn.microsoft.com/8a5ee124-d5ce-431d-9f7f-ff7894f0c28c">ExtRemoteTyped::ExtRemoteTyped (ExtRemoteTyped)</a>



<a href="https://msdn.microsoft.com/fbf10d5c-0a79-49f2-87e9-af63614e625c">ExtRemoteTyped::ExtRemoteTyped (PCSTR)</a>



<a href="https://msdn.microsoft.com/85b6e625-ad5a-4e11-a39a-418e0aa152c3">ExtRemoteTyped::ExtRemoteTyped (PCSTR, ULONG64)</a>



<a href="https://msdn.microsoft.com/e75c17d2-fdf7-4dba-9892-74c764956924">ExtRemoteTyped::Set(bool)</a>



<a href="https://msdn.microsoft.com/fc3d8d9c-0b19-42b3-b4d7-90df4667739b">ExtRemoteTyped::Set(pcstr ulong64 bool)</a>



<a href="https://msdn.microsoft.com/acf789f7-781d-4078-90cc-79b0d2709696">ExtRemoteTyped::Set(pcstr ulong64)</a>



<a href="https://msdn.microsoft.com/a19d6aff-c4e4-4188-8f27-3689e91023b4">ExtRemoteTyped::Set(pcstr)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544181">ExtRemoteTypedList</a>
 

 

