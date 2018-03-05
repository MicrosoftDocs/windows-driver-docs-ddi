---
UID: NS:d3dukmdt._D3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPU_FLAGS
title: "_D3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPU_FLAGS"
author: windows-driver-content
description: D3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPU_FLAGS describes the type of input synchronization objects to wait for.
old-location: display\d3dddi_waitforsynchronizationobjectfromcpu_flags.htm
old-project: display
ms.assetid: 2283D20F-D256-48E5-BFD2-D3ACACD7BF1C
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPU_FLAGS, D3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPU_FLAGS structure [Display Devices], _D3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPU_FLAGS, d3dukmdt/D3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPU_FLAGS, display.d3dddi_waitforsynchronizationobjectfromcpu_flags
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
-	D3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPU_FLAGS
product: Windows
targetos: Windows
req.typenames: D3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPU_FLAGS
---

# _D3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPU_FLAGS structure


## -description


<b>D3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPU_FLAGS</b> describes the type of input synchronization objects to wait for.


## -syntax


````
typedef struct _D3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPU_FLAGS {
  union {
    struct {
      UINT WaitAny  :1;
      UINT Reserved  :31;
    };
    UINT Value;
  };
} D3DDDI_WAITFORSYNCHRONIZATIONOBJECTFROMCPU_FLAGS;
````


## -struct-fields




### -field WaitAny

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0 (FALSE)</dt>
</dl>
</td>
<td width="60%">
[in] The wait condition is considered to be satisfied when all input synchronization objects are signaled to the corresponding input fence values or greater.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>1 (TRUE)</dt>
</dl>
</td>
<td width="60%">
[in] The wait condition is considered to be satisfied when any of the input synchronization objects is signaled to the corresponding input fence value or greater. 


</td>
</tr>
</table>
 


### -field Reserved

This member is reserved and should be set to zero.


#### - Value

The consolidated value of the bitfields in the nested structure.

