---
UID: NS:d3dkmthk._D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU
title: "_D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU"
author: windows-driver-content
description: D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU is used with D3DKMTSignalSynchronizationObjectFromGpu to signal a monitored fence.
old-location: display\d3dkmt_signalsynchronizationobjectfromgpu.htm
old-project: display
ms.assetid: 09190DCC-5F88-4C49-89B3-9063707E3F15
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU, D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU structure [Display Devices], display.d3dkmt_signalsynchronizationobjectfromgpu, _D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU, d3dkmthk/D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU
product: Windows
targetos: Windows
req.typenames: D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU
---

# _D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU structure


## -description


<b>D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU</b> is used with <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsignalsynchronizationobjectfromgpu.md">D3DKMTSignalSynchronizationObjectFromGpu</a> to signal a monitored fence.


## -syntax


````
typedef struct _D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU {
  HANDLE              hContext;
  UINT                ObjectCount;
  const D3DKMT_HANDLE *ObjectHandleArray;
  union {
    const UINT64 *MonitoredFenceValueArray;
    UINT64       Reserved[8];
  };
} D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU;
````


## -struct-fields




### -field MonitoredFenceValueArray

[in] An array of 64-bit monitored fence values to signal, each of which correspond to a synchronization object in <b>ObjectHandleArray</b>.


### -field Reserved

This member is reserved and should be set to zero.



### -field hContext

[in] A kernel-mode handle to the context stream.


### -field ObjectCount

[in] The number of synchronization events in the <b>ObjectHandleArray</b> array and fence values in <b>MonitoredFenceValueArray</b> arrays.


### -field ObjectHandleArray

[in] An array of kernel-mode handles to the synchronization events that the <b>hContext</b> member signals.


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsignalsynchronizationobjectfromgpu.md">D3DKMTSignalSynchronizationObjectFromGpu</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

