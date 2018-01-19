---
UID: NS:d3dkmthk._D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU
title: _D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU
author: windows-driver-content
description: D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU is used with D3DKMTSignalSynchronizationObjectFromCpu to enable a driver to signal a monitored fence.
old-location: display\d3dkmt_signalsynchronizationobjectfromcpu.htm
old-project: display
ms.assetid: 03B822CF-2FB0-412B-9F45-43756D8B4C19
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU, D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU
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
req.alt-api: D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU
req.alt-loc: d3dkmthk.h
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
req.typenames: D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU
---

# _D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU structure



## -description
<b>D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU</b> is used with <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsignalsynchronizationobjectfromcpu.md">D3DKMTSignalSynchronizationObjectFromCpu</a> to enable a driver to signal a monitored fence.



## -syntax

````
typedef struct _D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU {
  D3DKMT_HANDLE       hDevice;
  UINT                ObjectCount;
  const D3DKMT_HANDLE *ObjectHandleArray;
  const UINT64        *FenceValueArray;
} D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU;
````


## -struct-fields

### -field hDevice

[in] The handle to the device.


### -field ObjectCount

[in] The number of synchronization objects in the <b>ObjectHandleArray</b> and fence values in the <b>FenceValueArray</b>. 


### -field ObjectHandleArray

[in] An array of kernel-mode handles to the synchronization events to signal.


### -field FenceValueArray

[in] An array of 64 bit monitored fence values to signal, each corresponding to an object in the <b>ObjectHandleArray</b>.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsignalsynchronizationobjectfromcpu.md">D3DKMTSignalSynchronizationObjectFromCpu</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

