---
UID: NS:d3dkmthk._D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU
title: "_D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU"
author: windows-driver-content
description: D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU is used with D3DKMTWaitForSynchronizationObjectFromGpu to wait for a monitored fence to reach a certain value.
old-location: display\d3dkmt_waitforsynchronizationobjectfromgpu.htm
old-project: display
ms.assetid: F22149E4-0396-46DE-89FE-9B4321D86605
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU, D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU structure [Display Devices], _D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU, d3dkmthk/D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU, display.d3dkmt_waitforsynchronizationobjectfromgpu
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
-	D3dkmthk.h
api_name:
-	D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU
product: Windows
targetos: Windows
req.typenames: D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU
---

# _D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU structure


## -description


<b>D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU</b> is used with <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtwaitforsynchronizationobjectfromgpu.md">D3DKMTWaitForSynchronizationObjectFromGpu</a> to wait for a monitored fence to reach a certain value.


## -syntax


````
typedef struct _D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU {
  HANDLE              hContext;
  UINT                ObjectCount;
  const D3DKMT_HANDLE *ObjectHandleArray;
  union {
    const UINT64 *MonitoredFenceValueArray;
    UINT64       FenceValue;
    UINT64       Reserved[8];
  };
} D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU;
````


## -struct-fields




### -field hContext

[in] A kernel-mode handle to the context stream in which a wait for the synchronization events in the array that the <b>ObjectHandleArray</b> member specifies is inserted.


### -field ObjectCount

[in] The number of synchronization events in the <b>ObjectHandleArray</b> array and fence values in <b>MonitoredFenceValueArray</b> arrays.


### -field ObjectHandleArray

[in] An array of kernel-mode handles to the synchronization events that the context that is specified by the <b>hContext</b> member waits for.


#### - MonitoredFenceValueArray

[in] An array of 64-bit monitored fence values to wait for, each value corresponding to a synchronization object in <b>ObjectHandleArray</b>.


#### - FenceValue

[in] Fence value to wait for when the input object is of type <b>D3DDDI_FENCE</b>.


#### - Reserved

This member is reserved and should be set to zero.


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtwaitforsynchronizationobjectfromgpu.md">D3DKMTWaitForSynchronizationObjectFromGpu</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

