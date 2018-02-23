---
UID: NS:d3dukmdt._D3DDDICB_DESTROYALLOCATION2FLAGS
title: "_D3DDDICB_DESTROYALLOCATION2FLAGS"
author: windows-driver-content
description: The D3DDDICB_DESTROYALLOCATION2FLAGS structure is used with the D3DKMT_DESTROYALLOCATION2 structure to describe parameters for releasing allocations with D3DKMTDestroyAllocation2.D3DDDICB_DESTROYALLOCATION2FLAGS structure is used with the D3DKMT_DESTROYALLOCATION2 structure to describe parameters for releasing allocations with D3DKMTDestroyAllocation2.
old-location: display\d3dddicb_destroyallocation2flags.htm
old-project: display
ms.assetid: 50D4BFB7-B5AC-4202-B426-F152B06C9F46
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.d3dddicb_destroyallocation2flags, D3DDDICB_DESTROYALLOCATION2FLAGS structure [Display Devices], d3dukmdt/D3DDDICB_DESTROYALLOCATION2FLAGS, D3DDDICB_DESTROYALLOCATION2FLAGS, _D3DDDICB_DESTROYALLOCATION2FLAGS
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dukmdt.h
apiname:
-	D3DDDICB_DESTROYALLOCATION2FLAGS
product: Windows
targetos: Windows
req.typenames: D3DDDICB_DESTROYALLOCATION2FLAGS
---

# _D3DDDICB_DESTROYALLOCATION2FLAGS structure


## -description



The <b>D3DDDICB_DESTROYALLOCATION2FLAGS</b> structure is used with the <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_destroyallocation2.md">D3DKMT_DESTROYALLOCATION2</a> structure to describe parameters for releasing allocations with <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtdestroyallocation2.md">D3DKMTDestroyAllocation2</a>.




## -syntax


````
typedef struct _D3DDDICB_DESTROYALLOCATION2FLAGS {
  union {
    struct {
      UINT AssumeNotInUse  :1;
      UINT SynchronousDestroy  :1;
      UINT Reserved  :29;
      UINT SystemUseOnly  :1;
    };
    UINT Value;
  };
} D3DDDICB_DESTROYALLOCATION2FLAGS;
````


## -struct-fields




### -field AssumeNotInUse

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>FALSE</dt>
</dl>
</td>
<td width="60%">
Instructs the video memory manager to assume that commands queued prior to the destruction request may attempt to access the allocation being destroyed and defers the destruction operation until the queued commands finish.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>TRUE</dt>
</dl>
</td>
<td width="60%">
 Instructs the video memory manager to ignore pending commands on the owner device and destroy the allocations immediately.

</td>
</tr>
</table>
 


### -field SynchronousDestroy

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>FALSE</dt>
</dl>
</td>
<td width="60%">
 Instructs the DirectX graphics kernel that the call may return prior to the underlying surface memory being fully reclaimed by the operating system.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>TRUE</dt>
</dl>
</td>
<td width="60%">
 Instructs the DirectX graphics kernel to wait until surface memory is reclaimed by the operating system.

</td>
</tr>
</table>
 


### -field Reserved

This member is reserved and should be set to zero.


### -field SystemUseOnly

This member is reserved and should not be used by the user mode driver.


#### - Value

The consolidated value of the fields in the structure.


## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_destroyallocation2.md">D3DKMT_DESTROYALLOCATION2</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtdestroyallocation2.md">D3DKMTDestroyAllocation2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_DESTROYALLOCATION2FLAGS structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

