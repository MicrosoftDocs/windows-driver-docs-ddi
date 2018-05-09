---
UID: NS:d3dukmdt._D3DDDICB_LOCK2FLAGS
title: "_D3DDDICB_LOCK2FLAGS"
author: windows-driver-content
description: D3DDDICB_LOCK2FLAGS is used by the Lock2 kernel function to determine how an allocation is locked.
old-location: display\d3dddicb_lock2flags.htm
old-project: display
ms.assetid: 1F802912-F99B-4C04-9ABD-8FCC50FD3859
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DDDICB_LOCK2FLAGS, D3DDDICB_LOCK2FLAGS structure [Display Devices], _D3DDDICB_LOCK2FLAGS, d3dukmdt/D3DDDICB_LOCK2FLAGS, display.d3dddicb_lock2flags
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	HeaderDef
api_location:
-	d3dukmdt.h
api_name:
-	D3DDDICB_LOCK2FLAGS
product:
- Windows
targetos: Windows
req.typenames: D3DDDICB_LOCK2FLAGS
---

# _D3DDDICB_LOCK2FLAGS structure


## -description


<b>D3DDDICB_LOCK2FLAGS</b> is used by the <a href="https://msdn.microsoft.com/033FF321-2617-4AAF-8445-10800411F0B5">Lock2</a> kernel function to determine how an allocation is locked.
   
  Unlike <a href="https://msdn.microsoft.com/d64abd43-edf2-465a-8d99-8fdce1fcd25f">Lock</a>, which supported numerous flags, <a href="https://msdn.microsoft.com/033FF321-2617-4AAF-8445-10800411F0B5">Lock2</a> has none. The <b>Lock2</b> arguments allow flags to be specified using this structure, but currently it only has a reserved field to allow for capabilities to added in the future.


## -struct-fields




### -field Reserved

This member is reserved and must be zero.


### -field Value

This member must be zero.


## -see-also




<a href="https://msdn.microsoft.com/d64abd43-edf2-465a-8d99-8fdce1fcd25f">Lock</a>



<a href="https://msdn.microsoft.com/033FF321-2617-4AAF-8445-10800411F0B5">Lock2</a>
 

 

