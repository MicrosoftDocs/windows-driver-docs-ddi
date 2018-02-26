---
UID: NS:d3dumddi._D3DDDICB_UPDATEGPUVIRTUALADDRESS
title: "_D3DDDICB_UPDATEGPUVIRTUALADDRESS"
author: windows-driver-content
description: D3DDDICB_UPDATEGPUVIRTUALADDRESS is used with pfnUpdateGpuVirtualAddressCb to allow the user mode driver to specify a number of mapping operations to be applied to the process virtual address space in a single batch of page table updates.
old-location: display\d3dddicb_updategpuvirtualaddress.htm
old-project: display
ms.assetid: 6D460EBF-1D5D-4A99-90EE-FCBBC56B8EA4
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, 3, A, B, C, D, D3DDDICB_UPDATEGPUVIRTUALADDRESS, D3DDDICB_UPDATEGPUVIRTUALADDRESS structure [Display Devices], E, G, I, L, P, R, S, T, U, V, _, _D3DDDICB_UPDATEGPUVIRTUALADDRESS, d3dumddi/D3DDDICB_UPDATEGPUVIRTUALADDRESS, display.d3dddicb_updategpuvirtualaddress"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
apiname:
-	D3DDDICB_UPDATEGPUVIRTUALADDRESS
product: Windows
targetos: Windows
req.typenames: D3DDDICB_UPDATEGPUVIRTUALADDRESS
---

# _D3DDDICB_UPDATEGPUVIRTUALADDRESS structure


## -description


<b>D3DDDICB_UPDATEGPUVIRTUALADDRESS</b> is used with <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updategpuvirtualaddresscb.md">pfnUpdateGpuVirtualAddressCb</a> to allow the user mode driver to specify a number of mapping operations to be applied to the process virtual address space in a single batch of page table updates. 



## -syntax


````
typedef struct _D3DDDICB_UPDATEGPUVIRTUALADDRESS {
  HANDLE                                   hContext;
  D3DKMT_HANDLE                            hFenceObject;
  UINT                                     NumOperations;
  D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION *Operations;
  UINT                                     Reserved0;
  UINT64                                   Reserved1;
  UINT64                                   FenceValue;
  union {
    struct {
      UINT DoNotWait  :1;
      UINT Reserved  :31;
    };
    UINT   Value;
  } Flags;
} D3DDDICB_UPDATEGPUVIRTUALADDRESS;
````


## -struct-fields




### -field hContext

Specifies the context against which the map operation will be synchronized against. This also determines which kernel context the map operation will be executed against. In an linked display adapter configuration <b>hContext</b> defines a physical GPU, whose page tables are modified.


### -field hFenceObject

Specifies the monitored fence object to use for synchronization. This should typically be set to the monitored fence used by the user mode driver to track progress of <b>hContext</b>. 


### -field NumOperations

Specifies the number of operations in the <b>Operations</b> array. 


### -field Operations


<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_updategpuvirtualaddress_operation.md">D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION</a> array of operations to perform on the GPU virtual address space.


### -field Reserved0

This member is reserved and should be set to zero.


### -field Reserved1

This member is reserved and should be set to zero.


### -field FenceValue

Specifies the <b>FenceValue</b> for <b>hFenceObject</b> that the <i>Map</i> operation should wait on (unless <b>DoNotWait</b> is 1). When the <i>Map</i> operation completes, the fence object will signal <b>hFenceObject</b> with <b>FenceValue</b>+1.


### -field Flags



#### Value

The consolidated value of the <b>Flags</b> union.


### -field Flags.DoNotWait

When set to 1, there will be no wait for the sync objects before executing the operations.


### -field Flags.Reserved

This member is reserved and should be set to zero.


## -see-also

<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_updategpuvirtualaddress_operation.md">D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updategpuvirtualaddresscb.md">pfnUpdateGpuVirtualAddressCb</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_UPDATEGPUVIRTUALADDRESS structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

