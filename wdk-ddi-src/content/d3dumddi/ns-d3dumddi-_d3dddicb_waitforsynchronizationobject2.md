---
UID: NS:d3dumddi._D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT2
title: "_D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT2"
author: windows-driver-content
description: Describes the parameters that are required to set up the wait in a call to the pfnWaitForSynchronizationObject2Cb function.
old-location: display\d3dddicb_waitforsynchronizationobject2.htm
old-project: display
ms.assetid: b5dbd1f3-4475-41d2-879a-34618b28b485
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT2 structure [Display Devices], display.d3dddicb_waitforsynchronizationobject2, D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT2, d3dumddi/D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT2, _D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3dumddi.h
apiname:
-	D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT2
product: Windows
targetos: Windows
req.typenames: D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT2
---

# _D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT2 structure


## -description


Describes the parameters that are required to set up the wait in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobject2cb.md">pfnWaitForSynchronizationObject2Cb</a> function.


## -syntax


````
typedef struct _D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT2 {
  HANDLE        hContext;
  UINT          ObjectCount;
  D3DKMT_HANDLE ObjectHandleArray[D3DDDI_MAX_OBJECT_WAITED_ON];
  UINT64        FenceValue;
} D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT2;
````


## -struct-fields




### -field hContext

[in] A handle to a Direct3D context that waits for the synchronization objects in the array that the <b>ObjectHandleArray</b> member specifies to occur.


### -field ObjectCount

[in] The number of synchronization objects in the <b>ObjectHandleArray</b> array.

<b>ObjectHandleArray</b> must be set to 1 if the GPU synchronization object is of type <b>D3DDDI_FENCE</b>—namely, the <b>Type</b> member of the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_synchronizationobjectinfo2.md">D3DDDI_SYNCHRONIZATIONOBJECTINFO2</a> structure has a value of <b>D3DDDI_FENCE</b>.


### -field ObjectHandleArray

[in] An array of handles to the GPU synchronization objects that are to be signaled. The <b>D3DDDI_MAX_OBJECT_WAITED_ON</b> constant, which is defined as 32, indicates the maximum number of synchronization objects that the context can wait for.

All synchronization objects must be created on a logical adapter that has its context specified by the <b>hContext</b> member.


### -field FenceValue

[in] A 64-bit value that specifies the current fence value of the GPU synchronization object that is to be waited on.

This value applies only if the GPU synchronization object is of type <b>D3DDDI_FENCE</b>—namely, the <b>Type</b> member of the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_synchronizationobjectinfo2.md">D3DDDI_SYNCHRONIZATIONOBJECTINFO2</a> structure has a value of <b>D3DDDI_FENCE</b>.


## -remarks



Synchronization objects of type <b>D3DDDI_CPU_NOTIFICATION</b> cannot be used to wait on calls to <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobject2cb.md">pfnWaitForSynchronizationObject2Cb</a>.




## -see-also

<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_synchronizationobjectinfo2.md">D3DDDI_SYNCHRONIZATIONOBJECTINFO2</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_waitforsynchronizationobject2cb.md">pfnWaitForSynchronizationObject2Cb</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_WAITFORSYNCHRONIZATIONOBJECT2 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

