---
UID: NF:engextcpp.ExtRemoteList.Prev
title: ExtRemoteList::Prev (engextcpp.h)
description: The Prev method changes the current item to the previous item in the list.
old-location: debugger\extremotelist_prev.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["ExtRemoteList::Prev"]
ms.keywords: EngExtCpp_Ref_46ab35be-6259-4fe5-95fe-06c99244f6bb.xml, ExtRemoteList class [Windows Debugging],Prev method, ExtRemoteList.Prev, ExtRemoteList::Prev, Prev, Prev method [Windows Debugging], Prev method [Windows Debugging],ExtRemoteList class, debugger.extremotelist_prev
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ExtRemoteList::Prev
 - engextcpp/ExtRemoteList::Prev
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - engextcpp.hpp
api_name:
 - ExtRemoteList.Prev
---

# ExtRemoteList::Prev


## -description

The <b>Prev</b> method changes the current item to the previous item in the list.

## -remarks

This method can only be used when iterating over doubly-linked lists.

If <b>Prev</b> reaches the end of the list, subsequent calls to <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotelist-hasnode">ExtRemoteList::HasNode</a> will return <code>false</code>.

## -see-also

<a href="/windows-hardware/drivers/ddi/engextcpp/nl-engextcpp-extremotelist">ExtRemoteList</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotelist-hasnode">ExtRemoteList::HasNode</a>
