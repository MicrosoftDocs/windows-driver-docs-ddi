---
UID: NS:d3dumddi.D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU
title: D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU
author: windows-driver-content
description: D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU is used with pfnSignalSynchronizationObjectFromCpuCb to enable a driver to signal a monitored fence.
old-location: display\d3dddicb_signalsynchronizationobjectfromcpu.htm
old-project: display
ms.assetid: 14CA5FD1-00CB-474B-A2A3-4264CAFA063A
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dddicb_signalsynchronizationobjectfromcpu, D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU, d3dumddi/D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU, D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU structure [Display Devices]
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
-	D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU
product: Windows
targetos: Windows
req.typenames: D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU
---

# D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU structure


## -description


<b>D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU</b> is used with <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectfromcpucb.md">pfnSignalSynchronizationObjectFromCpuCb</a> to enable a driver to signal a monitored fence.


## -syntax


````
typedef struct D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU {
  UINT                ObjectCount;
  const D3DKMT_HANDLE *ObjectHandleArray;
  const UINT64        *FenceValueArray;
} D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU;
````


## -struct-fields




### -field ObjectCount

[in] The number of synchronization objects in the <b>ObjectHandleArray</b> and fence values in the <b>FenceValueArray</b>. 


### -field ObjectHandleArray

[in] An array of kernel-mode handles to the synchronization events to signal.


### -field FenceValueArray

[in] An array of 64 bit monitored fence values to signal, each corresponding to an object in the <b>ObjectHandleArray</b>.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectfromcpucb.md">pfnSignalSynchronizationObjectFromCpuCb</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMCPU structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

