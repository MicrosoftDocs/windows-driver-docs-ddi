---
UID: NS:d3dumddi.D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU
title: D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU
author: windows-driver-content
description: D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU is used with pfnWaitForSynchronizationObjectFromGpuCb to wait for a monitored fence to reach a certain value.
old-location: display\d3dddicb_waitforsynchronizationobjectfromgpu.htm
old-project: display
ms.assetid: 2A441CEE-C138-4FF0-8865-04ABFB0F029C
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU, D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU structure [Display Devices], display.d3dddicb_waitforsynchronizationobjectfromgpu, d3dumddi/D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU
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
-	D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU
product: Windows
targetos: Windows
req.typenames: D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU
---

# D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU structure


## -description


<b>D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU</b> is used with <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectfromgpucb.md">pfnWaitForSynchronizationObjectFromGpuCb</a> to wait for a monitored fence to reach a certain value.


## -syntax


````
typedef struct D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU {
  HANDLE              hContext;
  UINT                ObjectCount;
  const D3DKMT_HANDLE *ObjectHandleArray;
  union {
    const UINT64 *MonitoredFenceValueArray;
    UINT64       FenceValue;
    UINT64       Reserved[8];
  };
} D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU;
````


## -struct-fields




### -field MonitoredFenceValueArray

[in] An array of 64-bit monitored fence values to wait for, each value corresponding to a synchronization object in <b>ObjectHandleArray</b>.


### -field FenceValue

[in] Fence value to wait for when the input object is of type <b>D3DDDI_FENCE</b>.


### -field Reserved

This member is reserved and should be set to zero.


### -field hContext

[in] A kernel-mode handle to the context stream in which a wait for the synchronization events in the array that the <b>ObjectHandleArray</b> member specifies is inserted.


### -field ObjectCount

[in] The number of synchronization events in the <b>ObjectHandleArray</b> array and fence values in <b>MonitoredFenceValueArray</b> arrays.


### -field ObjectHandleArray

[in] An array of kernel-mode handles to the synchronization events that the context that is specified by the <b>hContext</b> member waits for.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobjectfromgpucb.md">pfnWaitForSynchronizationObjectFromGpuCb</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_WAITFORSYNCHRONIZATIONOBJECTFROMGPU structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

