---
UID: NF:engextcpp.ExtRemoteList.HasNode
title: ExtRemoteList::HasNode (engextcpp.h)
description: The HasNode method determines if there is a current item in the list iteration.
old-location: debugger\extremotelist_hasnode.htm
tech.root: debugger
ms.assetid: 412a77c8-eb10-43c5-bc45-2c61858463a7
ms.date: 05/03/2018
keywords: ["ExtRemoteList::HasNode"]
ms.keywords: EngExtCpp_Ref_c97c7662-0bbc-4458-9b69-34805fe8c451.xml, ExtRemoteList class [Windows Debugging],HasNode method, ExtRemoteList.HasNode, ExtRemoteList::HasNode, HasNode, HasNode method [Windows Debugging], HasNode method [Windows Debugging],ExtRemoteList class, debugger.extremotelist_hasnode
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
 - ExtRemoteList::HasNode
 - engextcpp/ExtRemoteList::HasNode
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - engextcpp.hpp
api_name:
 - ExtRemoteList.HasNode
---

# ExtRemoteList::HasNode


## -description

The <b>HasNode</b> method determines if there is a current item in the list iteration.

## -returns

<b>HasNode</b> returns <code>true</code> if there is a current item in the list iteration, and <code>false</code> otherwise.

## -remarks

Before you call <b>HasNode</b>, you must initialize the list for iteration by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotelist-starthead">StartHead</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotelist-starttail">StartTail</a>.

If this method returns <code>true</code>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotelist-getnodeoffset">ExtRemoteList::GetNodeOffset</a> can be used to return the current item in the list.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nl-engextcpp-extremotelist">ExtRemoteList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotelist-getnodeoffset">ExtRemoteList::GetNodeOffset</a>

